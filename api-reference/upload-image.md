# 🖼️ Upload Image

## Image Upload API Documentation

### Overview

The Pics Shade API allows users to upload images using an API key. This guide provides detailed instructions on how to use the API with JavaScript, including code examples and sample outputs.

### Endpoint

**URL:** `https://pics.shade.cool/api/upload`

**Method:** `POST`

### Authentication

To use the API, you need an API key. You can obtain your API key from the [Pics Shade Dashboard](https://pics.shade.cool/dashboard/api-keys).

### Request Headers

* `Authorization: Bearer <your_api_key>`
* `Content-Type: multipart/form-data`

### Request Body

The request body should be a `FormData` object containing the following fields:

* `file`: The image file to be uploaded.
* `path`: The path where the image should be stored (e.g., `folder1/folder2`).
* `tags`: A comma-separated list of tags associated with the image (optional).

### Sample JavaScript Code

Here's a sample JavaScript code snippet for uploading an image using the Fetch API:

```javascript
async function uploadImage(file, path, tags, apiKey) {
  const formData = new FormData();
  formData.append('file', file);
  formData.append('path', path);
  formData.append('tags', tags);

  try {
    const response = await fetch('https://pics.shade.cool/api/upload', {
      method: 'POST',
      headers: {
        'Authorization': `Bearer ${apiKey}`
      },
      body: formData
    });

    if (!response.ok) {
      throw new Error(`Error: ${response.statusText}`);
    }

    const result = await response.json();
    console.log('Upload successful!', result);
  } catch (error) {
    console.error('Error uploading image:', error);
  }
}

// Example usage:
const fileInput = document.querySelector('#fileInput');
const apiKey = 'your_api_key_here';

fileInput.addEventListener('change', () => {
  const file = fileInput.files[0];
  const path = 'folder1/folder2';
  const tags = 'tag1,tag2';
  uploadImage(file, path, tags, apiKey);
});
```

### Sample Output

Successful Response:

```json
{
  "url": "https://cdn.pics.shade.cool/folder1/folder2/image.png",
  "path": "folder1/folder2",
  "tags": ["tag1", "tag2"],
  "createdAt": "2024-07-05T12:34:56.789Z",
  "updatedAt": "2024-07-05T12:34:56.789Z"
}
```

Error Response:

```json
{
  "error": "Invalid API key."
}
```

### Error Handling

Ensure you handle errors appropriately in your code. Common errors include:

* Invalid API key
* File upload errors
* Network issues

### Notes

* The `file` field is required. Ensure you are uploading a valid image file.
* The `path` field is required. This specifies where the image will be stored.
* The `tags` field is optional but recommended for easier image management.

For more details, visit the [Pics Shade API Documentation](https://docs.pics.shade.cool/).

***

This guide provides a comprehensive overview of how to use the Pics Shade API for image uploads, including necessary headers, request body format, and sample JavaScript code for integration.
