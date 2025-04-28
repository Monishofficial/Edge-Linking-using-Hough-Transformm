# Exp-7-Edge-Linking-using-Hough-Transformm

## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.
## Program:
```
# Developed By: MONISH N
# Register Number: 212223240097
import cv2
import matplotlib.pyplot as plt
image = cv2.imread(r'C:\Users\admin\Downloads\eif.jpeg')  # Replace with your image path
# Display Input Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Input Image')
plt.axis('off')
plt.show()
```
![download](https://github.com/user-attachments/assets/f480d966-9dd2-4135-97d2-08d4986113c7)
```
# Developed By: MONISH N
# Register Number: 212223240097

gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Display Grayscale Image
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
plt.show()
```
![download](https://github.com/user-attachments/assets/a22afc37-e376-4f9b-a31e-cb7ba91829cb)



```
# Developed By: MONISH N
# Register Number: 212223240097

edges = cv2.Canny(gray_image, 50, 150, apertureSize=3)
# Display Canny Edge Detection Output   
plt.imshow(edges, cmap='gray')
plt.title('Canny Edge Detector Output')
plt.axis('off')
plt.show()
```
![download](https://github.com/user-attachments/assets/5bc8a797-6566-40df-80b4-5e0ee6303fc7)


```
# Detect lines using the probabilistic Hough transform
lines = cv2.HoughLinesP(edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=50, maxLineGap=10)

# Draw the lines on the original image
output_image = image.copy()

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(output_image, (x1, y1), (x2, y2), (0, 255, 0), 2)

```
```
# Developed By: MONISH N
# Register Number: 212223240097
# Display Hough Transform Result
plt.imshow(cv2.cvtColor(output_image, cv2.COLOR_BGR2RGB))
plt.title('Hough Transform - Line Detection')
plt.axis('off')
plt.show()

```
![download](https://github.com/user-attachments/assets/895bc021-03c8-403e-87a3-b80f95f5220f)


## Result: 
Thus the python program to detect the lines using Hough Transform was successfully completed.
 
