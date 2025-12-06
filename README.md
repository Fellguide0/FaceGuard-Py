##  How it Works

This project implements a secure biometric authentication system using **computer vision**. Unlike standard detection scripts, this solution focuses on strict identity verification.

### The Core Logic
1.  **Reference Loading:** The system loads a verified reference image (`yo.jpg`) and converts it into a **128-dimensional face encoding** (a mathematical vector representation of facial features).
2.  **Real-Time Capture:** It initializes the webcam using `OpenCV` to process video frames in real-time.
3.  **Face Encoding & Comparison:**
    * For every face detected in the video stream, the system calculates its vector embedding.
    * It computes the **Euclidean distance** between the live face and the reference face.
4.  **Strict Tolerance Threshold:**
    * Standard recognition libraries usually set a tolerance of `0.6`.
    * **This system uses a strict tolerance of `0.45`**.
    * **Result:** If the user wears sunglasses, a mask, or if an impostor tries to authenticate, the mathematical distance increases beyond `0.45`, triggering a **"Desconocido" (Unknown)** state.

### Tech Stack
* **Python 3.11** (Optimized for compatibility)
* **OpenCV** (Image processing)
* **Face_Recognition** (Dlib wrapper for embedding generation)
* **Numpy** (Linear algebra operations)
