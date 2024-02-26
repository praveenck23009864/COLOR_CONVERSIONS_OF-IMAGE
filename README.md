# COLOR_CONVERSIONS_OF-IMAGE
## AIM
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Choose an image and save it as a filename.jpg ,
### Step2:
Use imread(filename, flags) to read the file.
### Step3:
Use imshow(window_name, image) to display the image.
### Step4:
Use imwrite(filename, image) to write the image.
### Step5:
End the program and close the output image windows.
### Step6:
Convert BGR and RGB to HSV and GRAY
### Step7:
Convert HSV to RGB and BGR
### Step8:
Convert RGB and BGR to YCrCb
### Step9:
Split and Merge RGB Image
### Step10:
Split and merge HSV Image

##### Program:
```o
Developed by :praveen ck
Register no : 212222243003
```
<table>
  <tr>
    <td width=50%>

### i) Read and display the image
```Python
    import cv2
    image=cv2.imread('space1.jpg',1)
    image=cv2.resize(image,(400,300))
    cv2.imshow('Abishek Xavier A',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
``` 
  </td>
  <td>

### OUTPUT:
![Screenshot 2024-02-26 214333](https://github.com/praveenck23009864/COLOR_CONVERSIONS_OF-IMAGE/assets/141472050/1bc4f156-9ac0-42fa-b0fa-6f2d602a34a3)



  </td>
  </tr>

   <tr>
    <td width=50%>

### ii)Write the image
```Python
    import cv2
    image=cv2.imread('space1.jpg',0)
    cv2.imwrite('d.jpg',image)
```
  </td>
  <td>

### OUTPUT:

![304784358-d5dfd19a-6adb-4c43-b42f-661c48f9f8ec](https://github.com/praveenck23009864/COLOR_CONVERSIONS_OF-IMAGE/assets/141472050/d2ba29d1-4649-43a4-9a48-6eb75b32121e)



  </td>
  </tr>
  <tr>
    <td width=50%>

### iii)Shape of the Image
```Python
    import cv2
    image=cv2.imread('space1.jpg',1)
    print(image.shape)
```
  </td>
  <td>

### OUTPUT:
![Screenshot 2024-02-14 200045](https://github.com/AbishekAnand15/COLOR_CONVERSIONS_OF-IMAGE/assets/118706942/0ff2f0f6-4e04-451b-b7b2-d8306692dffa)

  </td>
  </tr>
  <tr>
    <td>
      
### iv)Access rows and columns
```Python
    import random
    import cv2
    image=cv2.imread('space1.jpg',1)
    image=cv2.resize(image,(400,400))
    for i in range (150,200):
      for j in range(image.shape[1]):
          image[i][j]=[random.randint(0,255),
                       random.randint(0,255),
                       random.randint(0,255)] 
    cv2.imshow('part image',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
  </td>
  <td width="50%">

### OUTPUT:


![Screenshot 2024-02-26 215037](https://github.com/praveenck23009864/COLOR_CONVERSIONS_OF-IMAGE/assets/141472050/19021a0b-cc4c-4fcd-9bfa-28611d3781fe)

  </td>
  </tr>
  <tr>
    <td width=50%>
      
### v)Cut and paste portion of image

 ```Python
    import cv2
    image=cv2.imread('space1.jpg',1)
    image=cv2.resize(image,(400,400))
    tag =image[130:200,110:190]
    image[110:180,120:200] = tag
    cv2.imshow('partimage1',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
  </td>
  <td>
    
### OUTPUT:


![Screenshot 2024-02-26 220001](https://github.com/praveenck23009864/COLOR_CONVERSIONS_OF-IMAGE/assets/141472050/5b6b4aea-a6dc-4c50-8e29-585577580140)

  </td>
  </tr>
</table>

### vi) BGR and RGB to HSV and GRAY
```Python
import cv2
img = cv2.imread('space1.jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)
hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('BGR2HSV',hsv1)
hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv2)
gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow('BGR2GRAY',gray1)
gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### OUTPUT:

![Screenshot 2024-02-26 220731](https://github.com/praveenck23009864/COLOR_CONVERSIONS_OF-IMAGE/assets/141472050/e50f42a9-467e-471f-8c86-557cbf63fdac)




### vii) HSV to RGB and BGR
```Python
import cv2
img = cv2.imread('space1.jpg')
img = cv2.resize(img,(300,200))
img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)
RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)
BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### OUTPUT:


![Screenshot 2024-02-26 221225](https://github.com/praveenck23009864/COLOR_CONVERSIONS_OF-IMAGE/assets/141472050/48c45f64-d309-4b46-adb2-0bf9febdc13d)

### viii) RGB and BGR to YCrCb
```Python
import cv2
img = cv2.imread('space1.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)
YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)
YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### OUTPUT:

![Screenshot 2024-02-26 222810](https://github.com/praveenck23009864/COLOR_CONVERSIONS_OF-IMAGE/assets/141472050/c715c6ce-5d11-4466-b40d-e9eaa93b0d56)


### ix) Split and merge RGB Image
```Python
import cv2
img = cv2.imread('space1.jpg',1)
img = cv2.resize(img,(300,200))
R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]
cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)
merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### OUTPUT:



![Screenshot 2024-02-26 223947](https://github.com/praveenck23009864/COLOR_CONVERSIONS_OF-IMAGE/assets/141472050/fdf74a3f-555e-41a0-a53f-93bef700c436)


### x) Split and merge HSV Image
```Python
import cv2
img = cv2.imread("space1.jpg",1)
img = cv2.resize(img,(300,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
H,S,V=cv2.split(img)
cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)
merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### OUTPUT:

![Screenshot 2024-02-26 224135](https://github.com/praveenck23009864/COLOR_CONVERSIONS_OF-IMAGE/assets/141472050/3b7db875-3259-4149-a034-4eca37935e34)



## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.






