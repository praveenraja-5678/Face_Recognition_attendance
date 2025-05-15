# Face_Recognition_attendance

📄 Project Documentation

Project Title:

Face Recognition Based Attendance System using Python

1. Introduction
   
Attendance is a critical task in educational institutions and workplaces. Traditional methods like manual attendance or biometric systems are time-consuming and prone to errors or misuse. This project presents a Face Recognition Based Attendance System built using Python, OpenCV, Flask, and Machine Learning (KNN), which automates attendance recording using real-time facial recognition via a webcam.

2. Objective

To design and implement a secure, accurate, and efficient attendance system that:

Recognizes faces using a webcam.

Matches faces with stored profiles.

Records the attendance with timestamp and ID.

Allows registration of new users with real-time face capture.

3. Technologies Used

| Technology   | Description                              |
| ------------ | ---------------------------------------- |
| Python       | Core programming language                |
| OpenCV       | For face detection and image processing  |
| Flask        | Web framework for UI and routing         |
| Scikit-learn | Used KNN model for face recognition      |
| Pandas       | Handling CSV data for attendance records |
| HTML/CSS     | Front-end template for user interface    |
| Bootstrap    | Responsive design styling                |


4. System Architecture
   
Modules:

User Registration

Captures 10 face images using webcam.

Saves them in static/faces/<username_userid>/.

Model Training

Extracts and resizes face images.

Trains a KNN classifier to recognize faces.

Saves model to static/face_recognition_model.pkl.

Face Detection & Recognition

Captures live video via webcam.

Detects face using Haar cascade.

Predicts identity using trained model.

Marks attendance in CSV file if user is not already present.

Attendance Record

Stored in Attendance/Attendance-<date>.csv.

Displays Name, ID, and Time in the UI.

Web Interface (Flask + HTML)

Homepage to display attendance records and user count.

Forms to register new users and trigger face recognition.

5. File Structure
   
FaceRecognitionAttendance/
│
├── app.py                       # Main Flask application
├── haarcascade_frontalface.xml # Haarcascade for face detection
├── static/
│   ├── faces/                   # Stores user images
│   └── face_recognition_model.pkl # Trained KNN model
│
├── Attendance/                 # Stores daily CSV attendance
├── templates/
│   └── home.html               # Frontend HTML page

6. How It Works
   
Run the Flask App:

bash

python app.py

Open Web Interface:

Visit http://127.0.0.1:5000/

Add New User:

Enter user name and ID.

Webcam opens to capture 10 images.

Train Model Automatically:

After image capture, the model is retrained.

Take Attendance:

Click on “Take Attendance”.

Webcam opens and identifies faces.

If recognized, logs attendance in Attendance/Attendance-<date>.csv.

7. Sample Attendance Format
   
markdown

Attendance-05_15_25.csv
--------------------------------------
Name      | Roll | Time
--------------------------------------
John      | 101  | 09:15:20
Alice     | 102  | 09:17:03

8. Features
   
✅ Real-time face recognition

✅ Auto attendance marking

✅ New user registration via webcam

✅ Daily attendance CSV generation

✅ Responsive web UI with Bootstrap

9. Limitations

Accuracy depends on lighting and webcam quality.

Faces should be front-facing and clear.

Model needs to retrain every time a new user is added.

Not secure against spoofing (e.g., photos).

10. Future Improvements
    
Add liveness detection to avoid spoofing.

Use deep learning models like FaceNet or Dlib.

Store attendance in a database instead of CSV.

Add admin login and dashboard.

Integrate with student/staff management systems.

11. Conclusion
    
This project demonstrates a working prototype of a Face Recognition Based Attendance System using Python. It provides a contactless, automated, and efficient solution for attendance tracking and is a stepping stone toward smart, AI-powered infrastructure.
