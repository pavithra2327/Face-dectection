# Face-dectection

import cv2
Code language: Python (python)
OpenCV library in python is blessed with many pre-trained classifiers for face, eyes, smile, etc. These XML files are stored in a folder. We will use the face detection model. You can download the pre-trained face detection model from here.


After downloading and saving the file in your directory, let’s load it into the face detection program:

face_cascade = cv2.CascadeClassifier('face_detector.xml')
Code language: Python (python)
The next step is to choose an image on which you want to test your code. Make sure there is at least one face in the image so that the face detection program can find at least one face.

After choosing an image, let’s define it in our program. Make sure the image is in the same directory you are working in:

img = cv2.imread('image.jpg')
Code language: Python (python)
Detect Faces
You will be amazed at how short the face detection code is. Thanks to the people who contribute to OpenCV. Here is the code that detects faces in an image:


faces = face_cascade.detectMultiScale(img, 1.1, 4)
Code language: Python (python)
Now the last step is to draw rectangles around the detected faces, which can be easily done with the following code:

for (x, y, w, h) in faces: 
  cv2.rectangle(img, (x, y), (x+w, y+h), (255, 0, 0), 2)
cv2.imwrite("face_detected.png", img) 
print('Successfully saved')
