# Image Resizing and Caching with ImageCDN

## Image Resizing and Caching with ImageCDN

### Overview

The ImageCDN service allows you to resize, cache, and transform images via simple HTTP GET requests. This documentation provides a detailed overview of how to use the service, including endpoint details, query parameters, and example usage.

### Endpoint

**URL:** `https://imagecdn.app/v2/image/{image}`

**Method:** `GET`

### Examples

1.  **Basic Example:**

    ```
    https://imagecdn.app/v2/image/https%3A%2F%2Fimages.unsplash.com%2Fphoto-1540665569139-922f374b8657?width=200&height=400
    ```
2.  **Example with Format and Fit:**

    ```
    https://imagecdn.app/v2/image/https%3A%2F%2Fimages.unsplash.com%2Fphoto-1540665569139-922f374b8657?width=200&height=400&format=jpg&fit=cover
    ```

### Query Parameters

| Parameter | Description                                                                                                                                 |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| `image`   | A URL-encoded link to the image you wish to cache and apply transformations to. The image must be reachable by the image service.           |
| `height`  | Height of the desired image, in pixels.                                                                                                     |
| `width`   | Width of the desired image, in pixels.                                                                                                      |
| `format`  | Override the format output by the service. Options are: `webp`, `jpg`, `png`. Defaults to the best format supported by the current browser. |
| `fit`     | How to fill the space provided by height/width. Options are: `cover`, `contain`, `fill`, `inside`, or `outside`. Defaults to: `cover`.      |

### Parameter Descriptions

#### `image`

The `image` parameter is a URL-encoded link to the image you want to transform. Ensure the image is publicly accessible or whitelisted for the ImageCDN service.

#### `height`

The `height` parameter specifies the desired height of the output image in pixels.

#### `width`

The `width` parameter specifies the desired width of the output image in pixels.

#### `format`

The `format` parameter allows you to override the default output format. Supported formats are:

* `webp`
* `jpg`
* `png`

By default, the service chooses the best format supported by the browser.

#### `fit`

The `fit` parameter determines how the image should fill the space defined by `height` and `width`. Options include:

* `cover`: Scale the image to fill the container. Crops to fit.
* `contain`: Scale the image to fit within the container. May leave empty space.
* `fill`: Stretch the image to fill the container. May distort the image.
* `inside`: Scale the image to fit within the container while preserving aspect ratio.
* `outside`: Scale the image to fill the container while preserving aspect ratio. May overflow.

### Example Usage in JavaScript

Here is a sample JavaScript code snippet to fetch and display a resized image using ImageCDN:

```javascript
const imageUrl = encodeURIComponent('https://images.unsplash.com/photo-1540665569139-922f374b8657');
const width = 200;
const height = 400;
const format = 'jpg';
const fit = 'cover';

const imageCDNUrl = `https://imagecdn.app/v2/image/${imageUrl}?width=${width}&height=${height}&format=${format}&fit=${fit}`;

const img = document.createElement('img');
img.src = imageCDNUrl;
document.body.appendChild(img);
```

### Sample Outputs

1.  **Resized Image:**

    ```json
    {
      "url": "https://imagecdn.app/v2/image/https%3A%2F%2Fimages.unsplash.com%2Fphoto-1540665569139-922f374b8657?width=200&height=400",
      "width": 200,
      "height": 400,
      "format": "webp",
      "fit": "cover"
    }
    ```
2.  **Formatted and Fitted Image:**

    ```json
    {
      "url": "https://imagecdn.app/v2/image/https%3A%2F%2Fimages.unsplash.com%2Fphoto-1540665569139-922f374b8657?width=200&height=400&format=jpg&fit=cover",
      "width": 200,
      "height": 400,
      "format": "jpg",
      "fit": "cover"
    }
    ```

### Notes

* Ensure that the image URL is properly URL-encoded.
* Review the [Getting Started Guide](https://docs.imagecdn.app/getting-started) for additional details and best practices.

For more information, visit the [ImageCDN Documentation](https://docs.imagecdn.app/).

***

This documentation provides a comprehensive guide on using ImageCDN to resize and cache images, including endpoint details, query parameters, example usage, and sample outputs.
