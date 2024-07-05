# 🧑‍🏫 Guides

#### Guides

Welcome to the Pics Shade Guides! Here, you will find step-by-step instructions and best practices for utilizing Pics Shade's image hosting services to their full potential. Whether you're just getting started or looking to integrate advanced features, these guides will help you every step of the way.

**Getting Started**

1.  **Create an Account**

    Start by creating an account on Pics Shade. Follow our [Getting Started Guide](https://pics.shade.cool/docs/getting-started) for detailed instructions on signing up and generating your API key.
2.  **Uploading Images**

    * **Web Interface**: Use our user-friendly web interface to upload and manage your images.
    * **API**: Integrate Pics Shade into your application by following our [API Reference](https://pics.shade.cool/docs/api).

    For a detailed walkthrough, refer to our [Uploading Images Guide](https://pics.shade.cool/docs/guides/uploading-images).

**Advanced Features**

1.  **Organizing Images**

    * **Folders**: Learn how to create and manage folders to keep your images organized.
    * **Tags**: Add tags to your images for easier searching and filtering.

    Check out our [Organizing Images with Folders and Tags Guide](https://pics.shade.cool/docs/guides/organizing-images).
2.  **Image Resizing**

    Resize your images on-the-fly by appending query parameters to the image URL. This allows you to optimize images for different devices and display requirements.

    Follow the steps in our [Image Resizing and Optimization Guide](https://pics.shade.cool/docs/guides/image-resizing).
3.  **Quota Management**

    Monitor your image usage and manage your quota efficiently. Understand how to keep track of your uploads and ensure you stay within your limits.

    Detailed instructions are available in our [Managing Your Image Quota Guide](https://pics.shade.cool/docs/guides/quota-management).

**Integration Examples**

1.  **Using Pics Shade with Next.js**

    Learn how to integrate Pics Shade's API with a Next.js application. Upload images, manage them, and display them on your website seamlessly.

    Step-by-step instructions can be found in our [Next.js Integration Guide](https://pics.shade.cool/docs/guides/nextjs-integration).
2.  **Building an Image Gallery**

    Create a dynamic image gallery using Pics Shade. This guide will walk you through setting up a gallery, organizing images, and adding interactive features.

    Get started with our [Building an Image Gallery Guide](https://pics.shade.cool/docs/guides/image-gallery).

**Troubleshooting**

1.  **Common Issues**

    Encountering problems? Check out our [Troubleshooting Guide](https://pics.shade.cool/docs/guides/troubleshooting) for solutions to common issues and errors.
2.  **Best Practices**

    Ensure optimal performance and security by following our best practices for using Pics Shade.

    Learn more in our [Best Practices Guide](https://pics.shade.cool/docs/guides/best-practices).

**API Usage Examples**

1.  **Uploading Images via API**

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

    For more API usage examples, refer to our [API Reference](https://pics.shade.cool/docs/api).

We hope these guides help you make the most of Pics Shade's features and services. If you have any questions or need further assistance, please visit our [Support](https://pics.shade.cool/support) page.
