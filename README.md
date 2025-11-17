**KidMedia Guardian**

Project: KidMedia Guardian — an agent to help parents detect and manage problematic kids’ videos

**Overview**

KidMedia Guardian is an agent that analyzes short children’s videos (YouTube Kids or uploaded clips) and automatically flags high-arousal content. The agent provides a parent-friendly summary highlighting visually or audibly intense moments. This project demonstrates the use of video and audio feature extraction combined with a simple human-centered summary.

**What It Does?**

Extracts visual features from videos: motion and brightness.

Extracts audio features from videos: tempo (BPM) and volume.

Flags videos if they exceed thresholds for motion, brightness, tempo, or volume.

Generates a parent-friendly summary describing why a video is flagged.

Processes multiple .mp4 or .mov files in a folder automatically.

**How It Works**

Video Feature Extraction

Uses OpenCV to compute average brightness and frame-to-frame motion.

Audio Feature Extraction

Uses FFmpeg to convert video to WAV and librosa to compute tempo and RMS volume.

Flagging and Summarization

Flags videos based on thresholds:

Motion > 18

Brightness > 200

BPM > 140

Volume > 0.12

Generates a simple summary like "High visual motion, Fast-paced audio, Loud volume".

**Project Structure**
working/
  .virtual_documents/
  data/
  results/
    analysis.json
  demo/
    sample_clips/
  src/
    __init__.py
    tools/
      __init__.py
      feature_extractor.py
  main.ipynb
requirements.txt
README.md

**How to Run**

Clone the repository.

Install dependencies:

pip install -r requirements.txt


**Run the main notebook or script:**

from src.tools.feature_extractor import extract_visual_features, extract_audio_features
from src.coordinator_agent import CoordinatorAgent

agent = CoordinatorAgent()
results = agent.analyze_videos_in_folder("/path/to/video/folder")
print(results)


Results are automatically saved in results/analysis.json.

**Current Status**

Core pipeline implemented for video and audio analysis.

Parent-friendly summaries generated.

Multiple videos can be analyzed in a folder.

Optional Features Not Implemented Yet

Suggesting calmer alternative clips or activities.

Small demo interface or notebook visualization for parents.

Quantitative evaluation metrics or human-in-the-loop testing.

**Dependencies**

numpy

pandas

opencv-python

librosa

soundfile

ffmpeg-python
