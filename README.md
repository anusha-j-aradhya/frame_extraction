🧩 Step 1: Set up your environment

Make sure you have Python installed.
You can check it by opening a terminal (or command prompt) and typing:

python --version


If you see a version (like Python 3.10.5), you’re good ✅

If not, install Python from https://www.python.org/downloads/

⚙️ Step 2: Install OpenCV

You need the OpenCV library to read the video and extract frames:

pip install opencv-python

📝 Step 3: Create a Python file

Open any text editor or IDE (like VS Code, PyCharm, or even Notepad).

Copy this full code and paste it:

import cv2
import os

# Path to your video file
video_path = "sample_video.mp4"  # <-- Replace with your video file name

# Create a folder to save frames
output_folder = "frames"
os.makedirs(output_folder, exist_ok=True)

# Open the video file
cap = cv2.VideoCapture(video_path)

frame_count = 0

while True:
    ret, frame = cap.read()
    if not ret:
        break  # Stop when video ends

    # Save each frame as an image
    frame_filename = os.path.join(output_folder, f"frame_{frame_count:04d}.jpg")
    cv2.imwrite(frame_filename, frame)
    
    frame_count += 1

print(f"✅ {frame_count} frames extracted and saved to '{output_folder}' folder.")

# Release the video capture object
cap.release()


Save the file with a name — for example:

extract_frames.py

▶️ Step 4: Run the script

Make sure your terminal’s working directory has:

The extract_frames.py file

The sample_video.mp4 (or any video you want to extract frames from)

Then run:

python extract_frames.py

🗂️ Step 5: Check your output

After the script finishes:

You’ll see a folder named frames/

Inside it, there will be images like:

frame_0000.jpg
frame_0001.jpg
frame_0002.jpg
...


Each image is a frame from your video 🎥
