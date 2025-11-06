# Attendance Management System using MediaPipe + OpenCV + Streamlit

### Features:
1. Admin Dashboard (View + Export in excel)
2. Multiple department support
3. Multiple Samples per Registration (more accuracy)
4. Proxy handling via eye-blink liveness check

### How it works:
1. Registration: Capture multiple frames per person, extract MediaPipe Face Mesh landmarks (468 points), store normalized landmark vectors as samples
2. Training: Train an SVM classifier on collected landmark vectors (minimum two user registered for the training phase)
3. Live attendance: Detect face, extract normalized landmark vector, predict label, then request a blink in a short time window to confirm liveness before marking attendance
4. Admin Dashboard: View attendance records and export to Excel

### Dependencies:
pip install mediapipe opencv-python streamlit scikit-learn pandas joblib numpy openpyxl

### Pre-requisite:
python version < 3.11

### Pros:
1. High Accuracy & Robustness
- Handles lighting variations, face angles, and expression changes effectively.
- Learns distinct boundaries between different users’ facial patterns.

2. Scalability
- Works efficiently even with large datasets (10–1000+ users).
- Once trained, predictions are very fast.

3. Confidence Scoring
- Provides probability or confidence levels for predictions, making it easy to set reliable thresholds for attendance marking.

### Cons:
1. Retraining Required
- Every time a new user is registered, the model must be retrained,
- which can take additional time.

2. Time-Consuming Training Step
- Initial model training can be slow if dataset size increases.

3. Black Box Nature
- Hard to interpret or explain how the model made a specific decision.

### WorkFlow:

<p align="center">
  <img src="https://github.com/Hussainaquib/Attendance-System/blob/main/Images/WorkFlow.png" alt="WorkFlow">
</p>

### Project Preview:

##### (1.) Register
<p align="center">
  <img src="https://github.com/Hussainaquib/Attendance-System/blob/main/Images/Register.png" alt="Register">
</p>

##### (2.) Train Model
<p align="center">
  <img src="https://github.com/Hussainaquib/Attendance-System/blob/main/Images/Train%20Model.png" alt="TrainModel">
</p>

##### (3.) Live Attendance
<p align="center">
  <img src="https://github.com/Hussainaquib/Attendance-System/blob/main/Images/Live%20Attendance.png" alt="LiveAttendance">
</p>

##### (4.) Admin Dashboard
<p align="center">
  <img src="https://github.com/Hussainaquib/Attendance-System/blob/main/Images/Admin%20Dashboard.png" alt="AdminDashboard">
</p>

