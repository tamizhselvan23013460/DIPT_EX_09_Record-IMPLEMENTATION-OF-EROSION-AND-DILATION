#  Exp : 9 (Record-IMPLEMENTATION-OF-EROSION-AND-DILATION)

# Name : Tamizhselvan B

# Reg.No : 212223230225


# Aim
To perform morphological image processing on an image containing text using erosion and dilation operations with a 3*3 kernel in OpenCV.



# Algorithms :

## Step - 1
Create a blank image: Initialize a 500*500 black image and add the text “Tamizhselvan B” using cv2.putText().

## Step - 2

Define the kernel: Create a 3*3 square structuring element using np.ones().

## Step - 3
Apply erosion: Use cv2.erode() with the kernel to shrink the text and reduce the thickness of its characters.

## Step - 4

Apply dilation: Use cv2.dilate() with the same kernel to expand the text and increase the thickness of its characters.

## Step - 5
Display the results: Convert the images from BGR to RGB and display the original, eroded, and dilated images using Matplotlib.


# Program :

```py


import cv2
import numpy as np
import matplotlib.pyplot as plt

# Create a blank image
image = np.zeros((500, 500, 3), dtype=np.uint8)

# Add text on the image using cv2.putText
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, 'Tamizhselvan B', (100, 250), font, 1, (215, 165, 255), 2, cv2.LINE_AA)

# Display the input image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for displaying
plt.title("Input Image with Text")
plt.axis('off')

# Create a simple square kernel (3x3)
kernel = np.ones((3, 3), np.uint8)

# Apply erosion (shrinking effect)
eroded_image = cv2.erode(image, kernel, iterations=1)

# Display the eroded image
plt.imshow(cv2.cvtColor(eroded_image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB
plt.title("Eroded Image")
plt.axis('off')

# Apply dilation (expanding effect)
dilated_image = cv2.dilate(image, kernel, iterations=1)

# Display the dilated image
plt.imshow(cv2.cvtColor(dilated_image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB
plt.title("Dilated Image")
plt.axis('off')



```


# Output :


## Input Image with Text :


<img width="633" height="515" alt="image" src="https://github.com/user-attachments/assets/66e8f4be-024b-45c4-b710-cb0619c85633" />


## Eroded Image :


<img width="639" height="517" alt="image" src="https://github.com/user-attachments/assets/f569efdb-b396-4e6b-a4f6-469b620435a9" />



## Dilated Image :


<img width="651" height="504" alt="image" src="https://github.com/user-attachments/assets/ae72d6a0-04dd-4894-ad97-061cb0487fc3" />


# Result :
The morphological operations were successfully performed on the text image. Erosion shrunk/thinned the text, while dilation expanded/thickened the text. Thus, the effects of erosion and dilation using a 3*3 kernel were successfully observed.

