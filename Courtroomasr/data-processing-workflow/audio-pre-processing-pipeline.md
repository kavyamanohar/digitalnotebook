# 🎤 Audio Pre-processing pipeline

## The Audio Data

The Supreme Court Hearings in this assignment contains audios of duration ranging from 10 minutes to 330 minutes. Many of them contain recording artifacts and long silences, which may be removed with voice activity detection after noise filtering. This process is automated.

#### Conversion to mono-channel mp3

Some of the audios are in mp4 format. Audio file type is converted to mono-channel mp3 format.

#### Down-sampling

The audio is is down sampled to 16kHz.&#x20;

#### Band Pass  Filtering

The audio contains many recording artifacts at frequency ranges beyond the normal human speech range.

So doing a band pass filtering suppresses most of the noises. \[200Hz-3000Hz]

#### &#x20;Silence Detection

On the down sampled mon-channel filtered speech, silence intervals are detected (-45dB threshold of atleast 1 s duration). The non-silence intervals are concatenated with a padding of 3ms.\
\
