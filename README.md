# DIPT-02--Image-Acquisition-Using-Web-Camera
## Name: Pavan Kalyan P
## Reg no: 212225240104

## Aim

To write a Python program using OpenCV to capture images from a webcam and perform the following image manipulations:

1. Write the captured frame as a JPG file.
2. Display the video.
3. Display the video by resizing the frame.
4. Rotate and display the video.

## Software Used

- Anaconda
- Python 3.7
- OpenCV
- NumPy

## Algorithm

### Step 1
Import the cv2 and numpy packages.

### Step 2
Read the video frame using cv2.VideoCapture(0).

### Step 3
Write the captured image using cv2.imwrite().

### Step 4
Display the video frame using cv2.imshow().

### Step 5
Divide the frame into four parts, resize the frame, and assign the smaller frame to each part.

### Step 6
Rotate the frame using cv2.rotate() and display the output.

## Program

*Developed By:* SHRIVARSHAN P G

*Register Number:* 212225240146

## i) Write the Frame as a JPG File

python
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()

captured_image = cv2.imread('captured_frame.jpg')

plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()


## ii) Display the Video

python
cap = cv2.VideoCapture(0)

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


## iii) Display the Video by Resizing the Frame

python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()


## iv) Rotate and Display the Video

python
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


## Output

### i) Write the Frame as a JPG Image

<img width="630" height="512" alt="image" src="https://github.com/user-attachments/assets/6ca24350-5957-473f-892a-37b8bc8a0df2" />



### ii) Display the Video

<img width="610" height="466" alt="Screenshot 2026-10-26 140511" src="https://github.com/user-attachments/assets/36186931-24ed-4cc5-a77d-94ce855d2479" />




### iii) Display the Video by Resizing the Frame

<img width="323" height="480" alt="Screenshot 2026-10-26 140526" src="https://github.com/user-attachments/assets/c0d07ebf-b424-4cb5-aeb4-48d57b9fe953" />



### iv) Rotate and Display the Video

<img width="368" height="472" alt="image" src="https://github.com/user-attachments/assets/2d1113e1-ff62-4484-930a-9cc33f946baf" />

## Result

Thus, images were captured from the webcam, saved as JPG files, and displayed using OpenCV. The video frames were resized and rotated successfully.
