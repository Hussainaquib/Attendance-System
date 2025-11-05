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

### Project Preview:

