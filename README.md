# Image-Handling-and-Pixel-Transformations-Using-OpenCV 

## AIM:
Write a Python program using OpenCV that performs the following tasks:

1) Read and Display an Image.  
2) Adjust the brightness of an image.  
3) Modify the image contrast.  
4) Generate a third image using bitwise operations.

## Software Required:
- Anaconda - Python 3.7
- Jupyter Notebook (for interactive development and execution)

## Algorithm:
### Step 1:
Load an image from your local directory and display it.

### Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

### Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image.  
Display the original, brighter, and darker images.

### Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).  
Display the original, lower contrast, and higher contrast images.

### Step 5:
Split the image (boy.jpg) into B, G, R components and display the channels


## Program Developed By:
- **Name:** JANANI S
- **Register Number:** 212224230103



```python
import cv2
import matplotlib.pyplot as plt
img = cv2.imread('q1.jpg', cv2.IMREAD_COLOR)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
plt.imshow(img_rgb, cmap='viridis')
plt.title("Original Image")
plt.axis('off') 
plt.show() 
```
<img width="761" height="495" alt="image" src="https://github.com/user-attachments/assets/885d7d63-130b-405c-8e02-5b795c864b4d" />


```python
image = cv2.imread('q1.jpg')
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2) 
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()
```
<img width="700" height="487" alt="image" src="https://github.com/user-attachments/assets/d81e2c57-b6c4-4b7e-b3b2-3a456578a629" />


```python
import cv2
import matplotlib.pyplot as plt


image = cv2.imread('q1.jpg')


img_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)


h, w, _ = img_rgb.shape


cv2.line(img_rgb, (0, 0), (w-1, h-1), (255, 0, 0), 2)


cv2.line(img_rgb, (w-1, 0), (0, h-1), (255, 0, 0), 2)


plt.figure(figsize=(8,6))
plt.imshow(img_rgb)
plt.title("Image with Line")
plt.axis("off")
plt.show()
```
<img width="861" height="490" alt="image" src="https://github.com/user-attachments/assets/d9d877a5-e0e6-4f3c-96d1-5b60244832e4" />



```python
import cv2
import matplotlib.pyplot as plt


img = cv2.imread("q1.jpg")


img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)


square_img = cv2.rectangle(img_rgb, (100, 80), (300, 280), (255, 0, 0), 7)


plt.imshow(square_img)
plt.title("Image with Square")
plt.axis("off")
plt.show()
```
<img width="797" height="407" alt="image" src="https://github.com/user-attachments/assets/5b5c2c55-b3c5-4075-b800-d781120d5268" />


```python
import cv2
import matplotlib.pyplot as plt


img = cv2.imread('q1.jpg')
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)


height, width, _ = img_rgb.shape   


rectangle_img = cv2.rectangle(img_rgb, (0, 0), (width, height), (0, 0, 255), 10)


plt.imshow(rectangle_img)
plt.title("Image with Rectangle in All Corners")
plt.axis('off')
plt.show()
```
<img width="767" height="400" alt="image" src="https://github.com/user-attachments/assets/c8ffc297-cd93-42dd-bd2d-83e77e83aeec" />


```python
image = cv2.imread('Qno. 1.jpg')
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
text_img = cv2.putText(img_rgb, "flowers", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 10) 
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
```
<img width="741" height="407" alt="image" src="https://github.com/user-attachments/assets/08f681fd-b067-4d88-be0c-0cddd76acce9" />


```python
image = cv2.imread('q1.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
```
<img width="747" height="441" alt="image" src="https://github.com/user-attachments/assets/6b46c92c-acc4-49c1-bbf7-29033f8e11f9" />


```python
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
```
<img width="827" height="406" alt="image" src="https://github.com/user-attachments/assets/ac74f1d7-12e7-40ef-9a52-41644d84a921" />



```python
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
```
<img width="717" height="405" alt="image" src="https://github.com/user-attachments/assets/ee7da9b2-5940-4ca7-9ccb-80ff680ab577" />


```python
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
```
<img width="741" height="412" alt="image" src="https://github.com/user-attachments/assets/95cecfee-0875-4d7c-959c-2521885976f8" />


```python
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
```
<img width="711" height="417" alt="image" src="https://github.com/user-attachments/assets/32b9fbed-d8e8-458c-9e60-81dd5d7dea90" />


```python
image = cv2.imread('q1.jpg') 
image.shape
resized_image = cv2.resize(image, (768 // 2, 600 // 2)) 
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
resized_image_rgb.shape
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
```
<img width="812" height="541" alt="image" src="https://github.com/user-attachments/assets/7f4e3c57-fe0f-4e4e-89f0-ce8f6134e9c4" />


```python
image = cv2.imread('q1.jpg')
image.shape
roi = image[50:350, 50:350] 
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()

```
<img width="675" height="595" alt="image" src="https://github.com/user-attachments/assets/d321ca8e-1822-477c-b35b-80e9336bf34c" />

```
image = cv2.imread('q1.jpg')
flipped_horizontally = cv2.flip(image, 1)
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)

plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
```
<img width="792" height="460" alt="image" src="https://github.com/user-attachments/assets/4ef9b086-6cd9-468f-9975-bc8f9d9671fb" />


```python
flipped_vertically = cv2.flip(image, 0)
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")

```
<img width="916" height="461" alt="image" src="https://github.com/user-attachments/assets/8fc293e0-7246-4df0-a0c8-9d0321288ad5" />







## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.

