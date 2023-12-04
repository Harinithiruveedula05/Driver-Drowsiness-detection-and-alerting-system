# Driver-Drowsiness-detection-and-alerting-system
Driver Drowsiness detection and alerting system detects if a driver is drowsy or not  using their eye moments and alerts them. This Script detects if a person is drowsy or not,using dlib and eye aspect ratio calculations. Uses webcam video feed as input.
## OBJECTIVE :
According to the National Highway Traffic Safety Administration, every year about 100,000 police-reported crashes involve drowsy driving. These crashes result in more than 1,550 fatalities and 71,000 injuries. The real number may be much higher, however, as it is difficult to determine whether a driver was drowsy at the time of a crash. So, we tried to build a system, that detects whether a person is drowsy and alert him.
## HERE 
The program contains 3 files, which are
## Files
**face_and_eye_detector_single_image.py** -Detects face and eye from a single image.
**face_and_eye_detector_webcam_video.py** -Detects face and eye in a webcam feed by user.
**drowsiness_detect.py** - Shows demo ( It detects the driver drowsiness and alert them by producing an alert based on our threshold value 
## Requirements
**IMPORTANT**
Download `shape_predictor_68_face_landmarks.dat.bz2` from [Shape Predictor 68 features](http://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2)                                                       Extract the file in the project folder using ``bzip2 -dk shape_predictor_68_face_landmarks.dat.bz2``
**REQUIREMENTS**
numpy==1.15.2
dlib==19.16.0
pygame==1.9.4
imutils==0.5.1
opencv_python==3.4.3.18
scipy==1.1.0
Use `pip install -r requirements.txt`to install the given requirements.
## Usage

### Detect Face and Eyes in a Single Image
Put your file to be detected in **images** folder with name **test.jpeg** or change the file path in Line : 9 face_and_eye_detector_single_image.py` to your image file. 
Run script using:

    python face_and_eye_detector_single_image.py
### Detect Face and Eyes in a Webcam Feed
Run script using:

    python face_and_eye_detector_webcam_video.py
### Drowsiness Detection
Run script using:

    python drowsiness_detect.py
The algorithm for Eye Aspect Ratio was taken from pyimagesearch.com blog, by Adrian RoseBrock.
**ALGORITHM**
We use dlib for face detection and facial landmarks along with the eye aspect ratio calculation.
1) we use open cv for importing the required libraries
2) we uses the Haar Cascade classifier for face detection
3) The dlib face detector and shape predictor are loaded using the provided files
4) In a main loop of code
   Each frame is read from the webcam and flipped.
   Facial points are detected using both the Haar Cascade classifier and the dlib face detector.
Rectangles are drawn around detected faces.
   For each detected face:
     >Facial landmarks are extracted using the shape predictor.
     >Eye aspect ratio is calculated for both eyes.
     >Convex hulls are used to draw contours around the eyes.
     >If the average eye aspect ratio is below the threshold, the drowsiness counter is incremented.
     >If the counter exceeds the specified consecutive frames threshold, an alarm sound is played, and a warning message is displayed on the frame.
    >If the eye aspect ratio is above the threshold, the counter is reset, and the alarm sound is stopped.
    >The video feed is displayed, and if the 'q' key is pressed, the loop is exited.
This algorithm continuously monitors the eye aspect ratio to determine if a person is drowsy, triggering an alarm when necessary. The dlib library is used for accurate facial landmark detection, and OpenCV is used for video capture and visualization.
**EXECUTION**
**Image for detecting eyes and face**

![web_cam_face_detection](https://github.com/Harinithiruveedula05/Driver-Drowsiness-detection-and-alerting-system/assets/152847148/4f9892c8-4121-4c20-a71b-71c9bbf06194)

**Image for detecting drowsiness**

![drowsiness_detection](https://github.com/Harinithiruveedula05/Driver-Drowsiness-detection-and-alerting-system/assets/152847148/e7eadf57-5825-4bd6-8b2d-6343945b2213)

     
   
