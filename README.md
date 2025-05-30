# OPENING--AND-CLOSING
## Aim
To implement Opening and Closing using Python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Import the necessary packages.

### Step2:
Create the Text using cv2.putText.

### Step3:
Create the structuring element.

### Step4:
Use Opening operation.

### Step5:
Use Closing Operation. 
## Program:
```
DEVELOPED BY: NISHA D
REGISTER NO: 212223230143
```
## OPENING:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline

def load_img():
    blank_img =np.zeros((600,600))
    font = cv2.FONT_HERSHEY_SIMPLEX
    cv2.putText(blank_img,text='NISHA',org=(50,300), fontFace=font,fontScale= 5,color=(255,255,255),thickness=25,lineType=cv2.LINE_AA)
    return blank_img

def display_img(img):
    fig = plt.figure(figsize=(12,10))
    ax = fig.add_subplot(111)
    ax.imshow(img,cmap='gray')
    plt.show()

img = load_img()

display_img(img)

white_noise = np.random.randint(low=0,high=2,size=(600,600))

white_noise

noise_img = white_noise+img

display_img(noise_img)

kernel = np.ones((5,5),np.uint8)
opening = cv2.morphologyEx(noise_img, cv2.MORPH_OPEN, kernel)

display_img(opening)
```

## CLOSING:

```
img = load_img()

black_noise = np.random.randint(low=0,high=2,size=(600,600))

black_noise

black_noise= black_noise * -255

black_noise_img = img + black_noise

black_noise_img

black_noise_img[black_noise_img==-255] = 0

closing = cv2.morphologyEx(black_noise_img, cv2.MORPH_CLOSE, kernel)


display_img(closing)
## Output:

![image](https://github.com/user-attachments/assets/4638ed9b-e5f9-4729-99bc-02d3d5f8dbb6)


### Display the input Image



### Display the result of Opening

![image](https://github.com/user-attachments/assets/949bac72-aa2b-44b9-84b0-e962b413ed4b)


![image](https://github.com/user-attachments/assets/bcb74c43-113a-4ed0-94b8-e6fd9d32cb21)



### Display the result of Closing

![image](https://github.com/user-attachments/assets/94f664aa-d1a8-46fd-8179-a9ec252b1a1a)



![image](https://github.com/user-attachments/assets/943aa9fb-bbae-48a9-be8e-7bc2f3fd4b0d)

## Result
Thus the Opening and Closing operation is used in the image using python and OpenCV.
