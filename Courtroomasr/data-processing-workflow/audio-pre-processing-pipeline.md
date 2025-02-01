# Audio Pre-processing pipeline

## The Audio Data

The Supreme Court Hearings in this assignment contains audios of duration ranging from 10 minutes to 330 minutes. Many of them contain recording artifacts and long silences, which may be removed with voice activity detection after noise filtering. This process is automated.

### Noise Filtering

The audio contains many recording artifacts, which are suppressed by noise cancellation and high pass and low pass filtering to retain only speech frequencies using ffmpeg.

{% code lineNumbers="true" %}
```bash
ffmpeg -i input.mp3 -af "highpass=f=200, anlmdn=s=2, afftdn=nf=-25,lowpass=f=3000" test5.mp3
```
{% endcode %}

### Silence Trimming

This is implemented as an ffmpeg based silence detection (-45dB threshold of atleast 2s duration is trimmed off).  It accepts both mp3 and mp4 files  and converts them into silence trimmed mp3 files.\
\
