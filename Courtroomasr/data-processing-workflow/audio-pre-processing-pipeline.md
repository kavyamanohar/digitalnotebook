# Audio Pre-processing pipeline

## Silence Trimming

The Supreme Court Hearings in this assignment contains audio of durations ranging from 10 minutes to 330 minutes. Many of them contain breaks, which may be removed with voice activity detection. This process is automated.\
\
This is implemented as an ffmpeg based silence detection (-50dB threshold of atleast 2s duration is trimmed off).\
\
It accepts both mp3 and mp4 files (given as part of this assignment) and converts them into silence trimmed mp3 files.\
\
Source Code: [https://github.com/kavyamanohar/audioslicer/blob/master/vad-trimming.py](https://github.com/kavyamanohar/audioslicer/blob/master/vad-trimming.py)
