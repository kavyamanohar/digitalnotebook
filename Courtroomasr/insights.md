# INSIGHTS



## What went well?

1. Pattern matching based text cleanup for good quality transcript was obtained from the PDF.  Text was segmented such that each segment is <15 words.
2. Audio preprocessing with noise cancellation followed by silence based trimming resulted in good quality audio.
3. Given a clean audio and corresponding time stamped text (In the form of a srt file of subtitles),  slicing the audio to create speech corpus cam out well. However very small segments < 0.5s corresponding to small words like "yes", "no" etc. was found to be unsuitable.&#x20;

### What was Challenging?

1. Forced alignment (FA)  between audio and text was the challenging part.
2. The light weight aeneas library performs FA fast (\~20 seconds for a 2 hour audio on Google Colab CPU.) and gives timestamps in srt format.
3. The FA works better on small text segments. So made sure every text segments is <15 words.
4. Forced alignment result was good and it generated good quality srt files.

### What went wrong?

1. The validation WER seems to be oscillating (50-60% WER), indicating poor model training.
2. This could be due to multiple reasons worth exploring:
   1. The numbers in training data are pronounced differently in different occasions. eg: 19 as one nine or nineteen.
   2. The brackets and punctuation (eg: period) are sometimes pronounced as such, while sometimes ignored.
3. Whisper allows for 30s inputs. However having a large number of speech samples of duration <5s, with lot of zero padding might have had a bad impact on training.
4. Evaluation was performed without any normalization. This could also have affected the validation WER metric. Whisper in infamous for hallucinations, especially on very short audios.

## FUTURE DIRECTIONS

1. Having small text segments is good for forced alignment, but bad for training. Consider combining adjacent small segments after forced alignment.
2. Normalize the text transcripts before training.
3. Drop very small duration audios from training.
4. Evaluate the results after normalization.
5. Use alternate ASR models, like Wav2Vec2-BER (SeamlessM4T). Having a separate language model on legal domain text should ideally improve the ASR accuracy.
6. Introduce ASR post processing and smart suggestions based on legal LM, for human in the loop editing of ASR output.

\
\
