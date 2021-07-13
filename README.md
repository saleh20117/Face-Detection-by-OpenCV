# Face-Detection-by-OpenCV
I used OpenCV to identify faces.
The steps were from https://towardsdatascience.com/face-detection-in-2-minutes-using-opencv-python-90f89d7c0f81

## Writing Python code
I used PYCharm in Windows to write Python code and imported the necessary libraries
import cv2

# Load the cascade
face_cascade = cv2.CascadeClassifier('haarcascade_frontalface_default.xml')
# Read the input image
img = cv2.imread('test.jpg')
# Convert into grayscale
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
# Detect faces
faces = face_cascade.detectMultiScale(gray, 1.1, 4)
# Draw rectangle around the faces
for (x, y, w, h) in faces:
    cv2.rectangle(img, (x, y), (x+w, y+h), (255, 0, 0), 2)
# Display the output
cv2.imshow('img', img)
cv2.waitKey()
