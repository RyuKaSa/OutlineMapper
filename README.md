# OutlineMapper

Simple outline mapper for images, using color clustering.

## Installation

You can install the package using pip:

```bash
pip install OutlineMapper
```

## Usage

```python
from outline_mapper import process_image
import matplotlib.pyplot as plt

image_path = 'path/to/your/image.png'
threshold = 0.04
min_pixels = 100
n_clusters = 5

# Get the image with black outlines
outlined_image = process_image(image_path, threshold, min_pixels, n_clusters, return_format="outlined_image")

# Get the mask
mask = process_image(image_path, threshold, min_pixels, n_clusters, return_format="mask")

# Get the image with colored zones
colored_zones = process_image(image_path, threshold, min_pixels, n_clusters, return_format="colored_zones")

# Get the image with colored zones and black outlines
colored_zones_with_outlines = process_image(image_path, threshold, min_pixels, n_clusters, return_format="colored_zones_with_outlines")

# Display the results
plt.figure(figsize=(24, 6))

plt.subplot(1, 4, 1)
plt.imshow(outlined_image)
plt.title('Original Image with Outlines')
plt.axis('off')

plt.subplot(1, 4, 2)
plt.imshow(mask)
plt.title('Mask with Outlines')
plt.axis('off')

plt.subplot(1, 4, 3)
plt.imshow(colored_zones)
plt.title('Colored Zones')
plt.axis('off')

plt.subplot(1, 4, 4)
plt.imshow(colored_zones_with_outlines)
plt.title('Colored Zones with Outlines')
plt.axis('off')

plt.show()
```

## parameters

Parameters:

 - image_path (str): Path to the image file.
 - threshold (float): Threshold for color similarity.
 - min_pixels (int): Minimum number of pixels for a zone.
 - n_clusters (int): Number of clusters for K-means.
 - return_format (str): Format of the returned image. Options are "outlined_image", "mask", "colored_zones", and "colored_zones_with_outlines".