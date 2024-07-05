# ⚙️ API Reference

#### API Reference

Welcome to the Pics Shade API Reference! This document provides detailed information on the available endpoints, request parameters, and response formats. Use this guide to integrate Pics Shade's image hosting capabilities into your applications seamlessly.

**Authentication**

All API requests must include an `Authorization` header with your API key:

```http
Authorization: Bearer YOUR_API_KEY
```

Get your API key from the [Dashboard](https://pics.shade.cool/dashboard/api-keys).

**Endpoints**

#### Upload Image

**POST** `/api/upload`

**Description:** Upload an image to Pics Shade.

**Request:**

```http
POST /api/upload HTTP/1.1
Host: pics.shade.cool
Authorization: Bearer YOUR_API_KEY
Content-Type: multipart/form-data

{
  "file": "<image-file>",
  "path": "folder1/folder2",
  "tags": "tag1,tag2"
}
```

**Response:**

```json
{
  "id": "image_id",
  "url": "https://cdn.shade.cool/folder1/folder2/image.png"
}
```

**Example in JavaScript:**

```javascript
const formData = new FormData();
formData.append("file", fileInput.files[0]);
formData.append("path", "folder1/folder2");
formData.append("tags", "tag1,tag2");

fetch("https://pics.shade.cool/api/upload", {
  method: "POST",
  headers: {
    "Authorization": `Bearer YOUR_API_KEY`,
  },
  body: formData,
})
.then(response => response.json())
.then(data => console.log(data))
.catch(error => console.error('Error:', error));
```

#### Get Image

**GET** `/api/images/:id`

**Description:** Retrieve details of a specific image.

**Request:**

```http
GET /api/images/:id HTTP/1.1
Host: pics.shade.cool
Authorization: Bearer YOUR_API_KEY
```

**Response:**

```json
{
  "id": "image_id",
  "url": "https://cdn.shade.cool/folder1/folder2/image.png",
  "tags": ["tag1", "tag2"],
  "path": "folder1/folder2",
  "createdAt": "2024-07-05T12:34:56.789Z",
  "updatedAt": "2024-07-05T12:34:56.789Z"
}
```

**Example in JavaScript:**

```javascript
fetch("https://pics.shade.cool/api/images/image_id", {
  method: "GET",
  headers: {
    "Authorization": `Bearer YOUR_API_KEY`,
  },
})
.then(response => response.json())
.then(data => console.log(data))
.catch(error => console.error('Error:', error));
```

#### Delete Image

**DELETE** `/api/images/:id`

**Description:** Delete a specific image.

**Request:**

```http
DELETE /api/images/:id HTTP/1.1
Host: pics.shade.cool
Authorization: Bearer YOUR_API_KEY
```

**Response:**

```json
{
  "success": true,
  "message": "Image deleted successfully."
}
```

**Example in JavaScript:**

```javascript
fetch("https://pics.shade.cool/api/images/image_id", {
  method: "DELETE",
  headers: {
    "Authorization": `Bearer YOUR_API_KEY`,
  },
})
.then(response => response.json())
.then(data => console.log(data))
.catch(error => console.error('Error:', error));
```

#### List Images by Tag

**GET** `/api/tags/:tag/images`

**Description:** List all images associated with a specific tag.

**Request:**

```http
GET /api/tags/:tag/images HTTP/1.1
Host: pics.shade.cool
Authorization: Bearer YOUR_API_KEY
```

**Response:**

```json
[
  {
    "id": "image_id",
    "url": "https://cdn.shade.cool/folder1/folder2/image.png",
    "tags": ["tag1", "tag2"],
    "path": "folder1/folder2",
    "createdAt": "2024-07-05T12:34:56.789Z",
    "updatedAt": "2024-07-05T12:34:56.789Z"
  },
  ...
]
```

**Example in JavaScript:**

```javascript
fetch("https://pics.shade.cool/api/tags/tag_name/images", {
  method: "GET",
  headers: {
    "Authorization": `Bearer YOUR_API_KEY`,
  },
})
.then(response => response.json())
.then(data => console.log(data))
.catch(error => console.error('Error:', error));
```

#### User Quota

**GET** `/api/quota`

**Description:** Retrieve the user's current image quota and usage details.

**Request:**

```http
GET /api/quota HTTP/1.1
Host: pics.shade.cool
Authorization: Bearer YOUR_API_KEY
```

**Response:**

```json
{
  "imageCount": 5000,
  "quota": 10000
}
```

**Example in JavaScript:**

```javascript
fetch("https://pics.shade.cool/api/quota", {
  method: "GET",
  headers: {
    "Authorization": `Bearer YOUR_API_KEY`,
  },
})
.then(response => response.json())
.then(data => console.log(data))
.catch(error => console.error('Error:', error));
```

For more details, visit our [API Documentation](https://pics.shade.cool/docs/api). If you have any questions or need further assistance, please visit our [Support](https://pics.shade.cool/support) page.
