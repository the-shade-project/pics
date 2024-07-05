# 💪 Getting Started

### Getting Started with Pics Shade

Welcome to **Pics Shade**! This guide will help you get started with hosting and managing your images on our platform. Follow the steps below to set up your account, upload images, and integrate our services into your website.

#### 1. Creating an Account

To begin, create an account on [Pics Shade](https://pics.shade.cool/):

1. Visit the [Pics Shade signup page](https://pics.shade.cool/signup).
2. Fill in your details (name, email, password) and click **Sign Up**.
3. Verify your email address by clicking the verification link sent to your email.

#### 2. Generating an API Key

To upload and manage images programmatically, you need an API key:

1. Log in to your account.
2. Navigate to the **API Keys** section in your dashboard.
3. Click **Generate API Key**.
4. Save your API key securely. You will use this key to authenticate your requests.

#### 3. Uploading Images

You can upload images using our web interface or via our API.

**Uploading via Web Interface**

1. Log in to your account.
2. Go to the **Upload** section.
3. Select the images you want to upload.
4. Optionally, add tags and choose folders for better organization.
5. Click **Upload**.

**Uploading via API**

Use the following example to upload images programmatically:

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

Replace `YOUR_API_KEY` with the API key you generated earlier.

#### 4. Managing Images

You can easily manage your images using our web interface or API.

**Organizing Images**

* **Folders**: Create folders to organize your images.
* **Tags**: Add tags to images for easy searching and filtering.

**Example: Creating a Folder**

```javascript
fetch("https://pics.shade.cool/api/folders", {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
    "Authorization": `Bearer YOUR_API_KEY`,
  },
  body: JSON.stringify({
    name: "New Folder",
    parent: "Parent Folder ID" // Optional
  })
})
.then(response => response.json())
.then(data => console.log(data))
.catch(error => console.error('Error:', error));
```

#### 5. Integrating Pics Shade with Your Website

**Accessing Images**

Images uploaded to Pics Shade can be accessed via their URLs. Use the following format to access an image:

```
https://cdn.shade.cool/{path}/{imageName}
```

**Example: Displaying an Image in HTML**

```html
<img src="https://cdn.shade.cool/folder1/folder2/image.png" alt="My Image">
```

#### 6. Additional Features

* **Free Image Resizing**: Resize your images on-the-fly by appending query parameters to the URL.
* **CDN Delivery**: Fast and reliable delivery of your images through Cloudinary CDN.
* **Quota Management**: Free up to 10,000 images. Additional images are charged at $10 per 10,000 images.

#### 7. Monitoring Usage

Monitor your image usage and API key activities from your dashboard:

1. Log in to your account.
2. Navigate to the **Usage** section.
3. View your current quota, usage statistics, and recent activities.

#### 8. Getting Help

If you encounter any issues or have questions, visit our [support page](https://pics.shade.cool/support) or contact us at support@shade.cool.

***

We hope this guide helps you get started with Pics Shade. Enjoy seamless image hosting and management with our platform!
