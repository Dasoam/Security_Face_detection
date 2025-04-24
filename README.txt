

# Security_Face_detection

**Security_Face_detection** is a Python-based security system that uses face detection and recognition to monitor video streams, identify authorized individuals, and trigger real-time alerts (audio and visual) when unknown faces are detected. The project integrates machine learning, database management, and user notification features for enhanced security applications.

---

## Features

- **Real-Time Face Detection:**  
  Utilizes `dlib` and a custom-trained (encrypted) PyTorch model to detect faces from a live camera or video feed.

- **Face Recognition:**  
  Compares detected faces against a database of known embeddings to identify individuals.

- **Database Integration:**  
  Stores and retrieves face data using database scripts for efficient management and logging.

- **Security Alerts:**  
  - **Audio Alert:** Plays a warning sound (`AU.mp3`) when an unauthorized face is detected.
  - **Visual Warning:** Pops up a GUI warning window using `Show_Warning.py`.

- **Model Security:**  
  The face recognition model is stored in an encrypted format (`face-model.pt.gpg`) to protect sensitive data and intellectual property.

- **Testing Utilities:**  
  Includes scripts for testing face embeddings and the recognition model.

---

## Project Structure

```
Security_Face_detection/
├── main.py                   # Main entry point for the security system
├── face_fetch.py             # Face detection and recognition logic
├── face_embeddings_test.py   # Test/generate face embeddings
├── model_test.py             # Test the recognition model
├── data_fetch_db.py          # Fetch face data from the database
├── push_data.py              # Push new data to the database
├── Show_Warning.py           # Display GUI warning on unauthorized access
├── PlayAU.py                 # Play audio alert
├── AU.mp3                    # Audio file for alerts
├── face-model.pt.gpg         # Encrypted face recognition model (PyTorch)
├── dlib-19.24.1-cp311-cp311-win_amd64.whl # Prebuilt dlib wheel for Windows
├── requirements.txt          # Python dependencies
├── README.txt                # Basic usage or setup instructions (legacy)
├── .gitignore                # Files/folders to ignore in version control
└── (other IDE/cache files)
```

---

## Requirements

- Python 3.11+
- Windows OS (recommended, due to provided dlib wheel)
- Webcam or video input device

### Python Dependencies

Install dependencies via:

```bash
pip install -r requirements.txt
```

If dlib installation fails, use the provided wheel:

```bash
pip install dlib-19.24.1-cp311-cp311-win_amd64.whl
```

---

## Setup & Usage

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Dasoam/Security_Face_detection.git
   cd Security_Face_detection
   ```

2. **Install dependencies:**  
   See above.

3. **Decrypt the face recognition model (if required):**  
   The model file (`face-model.pt.gpg`) is encrypted.  
   - Use GPG to decrypt (if you have the key):
     ```bash
     gpg --output face-model.pt --decrypt face-model.pt.gpg
     ```

4. **Run the main application:**
   ```bash
   python main.py
   ```

---

## How It Works

- The system captures frames from a webcam or video source.
- Faces are detected using `dlib`.
- Detected faces are processed through the encrypted PyTorch model to generate embeddings.
- Embeddings are compared to those stored in the database:
  - **Known face:** No action or logs access.
  - **Unknown face:** Triggers `Show_Warning.py` (visual alert) and `PlayAU.py` (audio alert).
- All events can be logged or pushed to a database for record-keeping.

---

## Scripts & Utilities

- **face_fetch.py:**  
  Core face detection and recognition functions.

- **face_embeddings_test.py:**  
  Generate or test face embeddings for new users.

- **model_test.py:**  
  Test the accuracy and performance of the face recognition model.

- **data_fetch_db.py / push_data.py:**  
  Interact with the database to fetch or insert face data.

- **Show_Warning.py:**  
  Pops up a warning window if an unauthorized face is detected.

- **PlayAU.py:**  
  Plays the `AU.mp3` audio alert.

---

## Security & Privacy

- **Encrypted Model:**  
  The face recognition model is encrypted to safeguard sensitive data and intellectual property.
- **No License:**  
  This repository does not include an open source license.  
  **All rights reserved. You may not use, copy, modify, or distribute this code without explicit permission from the author.**

---

## Disclaimer

This project is provided for educational and research purposes only.  
For commercial or production use, please contact the repository owner for permission.

---

## Contact

For questions, collaborations, or access requests, please contact the repository owner via GitHub.

