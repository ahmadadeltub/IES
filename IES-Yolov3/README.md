# YOLOV3 IES SYSTEM PROJECT - QSTSS SCHOOL

## Real-Time Video Monitoring and Analysis System

### Code Number 1:

```python
# Real-Time Webcam Monitoring
import cv2

cap = cv2.VideoCapture(0)

# Check if the webcam is opened correctly
if not cap.isOpened():
    raise IOError("Cannot open webcam")

while True:
    ret, frame = cap.read()
    frame = cv2.resize(frame, None, fx=0.5, fy=0.5, interpolation=cv2.INTER_AREA)
    cv2.imshow('Input', frame)

    c = cv2.waitKey(1)
    if c == 27:
        break

cap.release()
cv2.destroyAllWindows()
```

### Code Number 2:

```python
# Real-Time People Counter and Monitoring
from mylib.centroidtracker import CentroidTracker
from mylib.trackableobject import TrackableObject
from imutils.video import VideoStream
from imutils.video import FPS
from mylib.mailer import Mailer
from mylib import config, thread
import time, schedule, csv
import numpy as np
import argparse, imutils
import dlib, cv2, datetime
from itertools import zip_longest

# ... (continued)

# Close any open windows
cv2.destroyAllWindows()
```

### Usage Instructions:

1. **Webcam Monitoring:**
   - Ensure Python and OpenCV are installed.
   - Run the provided code (`Code Number 1`) to initiate real-time webcam monitoring.
   - Press `Esc` key to exit.

2. **People Counter and Monitoring:**
   - Install the required libraries mentioned in `Code Number 2`.
   - Run the provided code (`Code Number 2`) to initiate real-time people counting and monitoring.
   - Press `q` to exit the monitoring window.
   - The system will log the data in `Log.csv` if logging is enabled.

### Important Notes:
- Ensure all dependencies are installed, including the libraries specified in `Code Number 2`.
- Adjust configurations in `config.py` based on your requirements.
- The people counter system includes features like automatic email alerts and logging.

For any issues or inquiries, please refer to the code documentation or contact the project team.

**Note:** The provided code is for educational purposes, and additional setup and configurations may be required based on specific use cases.