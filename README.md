# Exp-4- Record-Image Transformations

## Experiment Details

- **Name:** Lorena Avelyn R
- **Register Number:** 212224040174

## Aim

To perform various image transformations such as Translation, Scaling, Shearing, Reflection, Rotation, and Cropping using OpenCV and Python.

## Software Required

- Anaconda
- Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

**Step 1:** Import the necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

**Step 2:** Read the input image using the `cv2.imread()` function and store it in a variable.

**Step 3:** Apply different image transformations using the following methods:

1. **Translation:** Moves the image along the X-axis or Y-axis using a translation matrix.
2. **Scaling:** Resizes the image using scaling factors.
3. **Shearing:** Distorts the image along one or both axes using a shear matrix.
4. **Reflection:** Flips the image horizontally or vertically using `cv2.flip()`.
5. **Rotation:** Rotates the image by a specified angle using `cv2.getRotationMatrix2D()`.
6. **Cropping:** Extracts a specific portion of the image using array slicing.

**Step 4:** Display the original and transformed images using Matplotlib.

**Step 5:** Convert the BGR image into RGB format using `cv2.cvtColor()` to display the correct colors.

## Program

### Developed By: Lorena Avelyn R

### Register Number: 212224040174

### i) Original Image

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread("Ip2.jpg")

# Display the original image
plt.imshow(image[:, :, ::-1])
plt.title("Original Image")
plt.axis("off")
plt.show()
```

**Output:**

<img width="575" height="411" alt="image" src="https://github.com/user-attachments/assets/8cd038ba-2a84-408a-b6bd-eaac8b63b473" />

### ii) Image Translation

```python
tx, ty = 100, 200

M_translation = np.float32([
    [1, 0, tx],
    [0, 1, ty]
])

translated_image = cv2.warpAffine(
    image, M_translation, (673, 419)
)

plt.imshow(translated_image[:, :, ::-1])
plt.title("Translated Image")
plt.axis("on")
plt.show()
```

**Output:**

<img width="546" height="417" alt="image" src="https://github.com/user-attachments/assets/57b074b7-ab0f-497f-9d16-c927e275f0fa" />

### iii) Image Scaling

```python
fx, fy = 5.0, 2.0

scaled_image = cv2.resize(
    image, None, fx=fx, fy=fy,
    interpolation=cv2.INTER_LINEAR
)

plt.imshow(cv2.cvtColor(
    scaled_image, cv2.COLOR_BGR2RGB
))

plt.title("Scaled Image")
plt.axis("off")
plt.show()
```

**Output:**

<img width="630" height="243" alt="image" src="https://github.com/user-attachments/assets/0823ab94-c5fb-4fd3-afce-e072b9d8c33c" />


### iv) Image Shearing

```python
shear_matrix = np.float32([
    [1, 0.5, 0],
    [0.5, 1, 0]
])

sheared_image = cv2.warpAffine(
    image, shear_matrix,
    (image.shape[1], image.shape[0])
)

plt.imshow(cv2.cvtColor(
    sheared_image, cv2.COLOR_BGR2RGB
))

plt.title("Sheared Image")
plt.axis("off")
plt.show()
```

**Output:**

<img width="688" height="417" alt="image" src="https://github.com/user-attachments/assets/48e1491c-b3e6-4ed6-9ece-7a674907b4b7" />


### v) Image Reflection

```python
reflected_image = cv2.flip(image, 2)

plt.imshow(cv2.cvtColor(
    reflected_image, cv2.COLOR_BGR2RGB
))

plt.title("Reflected Image")
plt.axis("off")
plt.show()
```

**Output:**

<img width="685" height="410" alt="image" src="https://github.com/user-attachments/assets/12a624ba-fb34-49f8-9a77-2fa25e408e2e" />

### vi) Image Rotation

```python
(height, width) = image.shape[:2]

angle = 45
center = (width // 2, height // 2)

M_rotation = cv2.getRotationMatrix2D(
    center, angle, 1
)

rotated_image = cv2.warpAffine(
    image, M_rotation, (width, height)
)

plt.imshow(cv2.cvtColor(
    rotated_image, cv2.COLOR_BGR2RGB
))

plt.title("Rotated Image")
plt.axis("off")
plt.show()
```

**Output:**

<img width="620" height="417" alt="image" src="https://github.com/user-attachments/assets/78f0fd6f-cc39-46cb-96bc-7c6302fa9a42" />

### vii) Image Cropping

```python
x, y, w, h = 100, 100, 200, 150

cropped_image = image[y:y+h, x:x+w]

plt.imshow(cv2.cvtColor(
    cropped_image, cv2.COLOR_BGR2RGB
))

plt.title("Cropped Image")
plt.axis("off")
plt.show()
```

**Output:**

<img width="685" height="417" alt="image" src="https://github.com/user-attachments/assets/9305de1c-ca4a-4a8d-8c32-038633969ca2" />


## Result

Thus, the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation, and Cropping were successfully performed using OpenCV and Python programming.

