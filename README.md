# End-to-End DeepFake Video Generation


[![forthebadge](https://forthebadge.com/images/badges/made-with-python.svg)](https://www.python.org/)
[![forthebadge](https://forthebadge.com/images/badges/uses-badges.svg)](https://forthebadge.com)

<!-- [![License: MIT](https://img.shields.io/badge/License-MIT-brightgreen.svg)](https://opensource.org/licenses/MIT) -->
[![Maintenance](https://img.shields.io/badge/Maintained%3F-no-red.svg)]( https://github.com/nsourlos/semi-automated_installation_exe_msi_files-Windows_10)


## Overview

This [Colab](./Deepfake_end_to_end_tortoise_wav2lip_Colab.ipynb) notebook provides a step-by-step guide to generate a deepfake video by cloning a voice onto a video. The process involves uploading video and voice files, renaming them, extracting audio, creating audio chunks, and finally using Wav2Lip for deepfake generation.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/nsourlos/end-to-end_deepfake_colab]

## Steps

**Before executing this notebook we need to have a folder in our Google Drive named ```deepfake``` with at least a video file (mp4 format). It is strongly recommended to also include an audio (mp3 format) file to clone the voice from. Especially for cases of non-English language in the video, it is essential to upload an English audio file as well.**

### 1. Upload Video and Voice Files

- Mount Google Drive to access files.
- Change directory to the specified path.

```python
from google.colab import drive
drive.mount('/content/gdrive')

cd gdrive/MyDrive/deepfake
```

### 2. Set Base Path

Specify the base path for video and audio files.

```python
base_path='/content/gdrive/MyDrive/deepfake'
```

### 3. Install Dependencies

Install TTS, pydub, and moviepy libraries.

```python
!pip install -q pydub==0.25.1 TTS==0.22.0 moviepy==1.0.3
```

### 4. Set Text to Read

Set the English text that will be read with the cloned voice.

```python
text_to_read="Joining two modalities results in a surprising increase in generalization! \\\n What would happen if we combined them all?\" 
```

### 5. Rename Audio and Video Files
Rename the uploaded audio and video files to ```input_voice.mp3``` and ```video_full.mp4```, respectively.

### 6. Extract Audio from Video (if needed)
If only a video is provided, extract audio from it to be used to clone the individual.

### 7. Create Audio Chunks
Create a folder with 10-second chunks of audio to be used as input in Tortoise.

### 8. Confirm Audio and Video Duration
Ensure audio and video have the same duration. If not, trim the longer one to match the shorter one or cut both to 20 seconds.

### 9. Clone Wav2Lip Repository and Download Models
Clone Wav2Lip GitHub repository, download pre-trained models, and install dependencies.

### 10. Generate Deepfake
Run the Wav2Lip inference script to generate the deepfake video.

### 11. Cleanup
Remove temporary files and folders.
