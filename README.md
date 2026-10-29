# Image Capture and Video Processing Using OpenCV

---

## Aim

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file  
2. Display the video  
3. Display the video by resizing the window  
4. Rotate and display the video  

---

## 🛠️ Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  

---

## ⚙️ Algorithm

### Step 1:
Import the required libraries and initialize the webcam using `cv2.VideoCapture()`.

### Step 2:
Capture frames continuously from the webcam.

### Step 3:
Save a frame as a JPG image using `cv2.imwrite()`.

### Step 4:
Display the live video stream using `cv2.imshow()`.

### Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

---

## 💻 Program

### Developed By:
**Name:** NARENDRA KRISHNAN KS  

### Register No:
212225240096

---

## PROGRAM:
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
```


### i) Write the frame as JPG image
Captured image is saved as `MY.jpg`
```
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite(r"C:\Users\naren\OneDrive\Pictures\Camera Roll\MY.jpg", frame)
cap.release()
captured_image = cv2.imread(r"C:\Users\naren\OneDrive\Pictures\Camera Roll\MY.jpg")
import matplotlib.pyplot as plt

plt.imshow(captured_image[:, :, ::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
```
OUTPUT:

<img width="591" height="397" alt="image" src="https://github.com/user-attachments/assets/edf55e46-8162-405d-a47f-d93cb18cc119" />

### ii) Display the video
Live webcam video is displayed
```
import cv2
import matplotlib.pyplot as plt
import time
from IPython.display import clear_output

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        print("Failed to capture frame")
        break

    resized_frame = cv2.resize(frame, (100, 150))
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.title('Live Webcam Frame')
    plt.axis('off')
    plt.show()

    time.sleep(0.05)

cap.release()
```
OUTPUT:
<img width="532" height="363" alt="image" src="https://github.com/user-attachments/assets/1a94579b-5271-433a-a92c-cf3335a21666" />


### iii) Display the video by resizing the window
Video is shown in resized resolution (640 × 480)
cap = cv2.VideoCapture(0)
```
for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```
OUTPUT:
<img width="577" height="383" alt="image" src="https://github.com/user-attachments/assets/6001fb69-de0e-489a-9c0f-5aaeabea2e28" />

### iv) Rotate and display the video
Video is displayed after rotation (90° clockwise)
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break

    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()

    time.sleep(0.05)

cap.release()
```
OUTPUT:

<img width="590" height="390" alt="image" src="https://github.com/user-attachments/assets/ea58ce25-b5d9-46cc-8d0b-34704576a216" />

---

## Result

Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
