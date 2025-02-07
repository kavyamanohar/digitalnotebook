# 💡 INSIGHTS



## What went well?

1. Pattern matching based text cleanup for good quality transcript was obtained from the PDF.  Text was segmented such that each segment is <15 words.
2. Audio preprocessing with band pass filtering resulted in food noise cancellation.
3. It was then followed by silence based trimming resulted in good quality audio.
4. Given a clean audio and corresponding time stamped text (In the form of a srt file of subtitles),  slicing the audio to create speech corpus came out well. However very small segments < 0.5s corresponding to small words like "yes", "no" etc. was found to be unsuitable.&#x20;

### What was Challenging?

1. Forced alignment (FA)  between audio and text was the challenging part.
2. The light weight aeneas library performs FA fast (\~20 seconds for a 2 hour audio on Google Colab CPU.) and gives timestamps in srt format.
3. The FA works better on small text segments. So made sure every text segments is <15 words.
4. Forced alignment result was good in general and it generated good quality srt files.
5. But there are some unsolved catches:
   * Word repetitions that are not in the transcripts affects alignment, and the error propogates to subsequent time stamps.
   * Some times, punctuations are literally spoken: eg: "Full-Stop", "Comma". It also affects alignments.

### What could be improved?

1. The audio pre-processing pipeline is computationally heavy. ~~This `ffmpeg` based code needs optimization.~~  Pydub based implementation of preprocessing, made it much faster.
2. The validation WER seems to be oscillating (50-60% WER), indicating poor model training. This could be due to multiple reasons worth exploring:
   1. The numerals in training data are pronounced differently in different occasions. eg: 19 as one nine or nineteen.
   2. The brackets and punctuation are sometimes pronounced as such  (eg: period), while sometimes ignored.
3. Whisper allows for 30s inputs. However having a large number of speech samples of duration <5s, with lot of zero padding might have had a bad impact on training.
4. Evaluation was performed without any normalization. This could also have affected the validation WER metric. Whisper in infamous for hallucinations, especially on very short audios.

## FUTURE DIRECTIONS

1. Train the Supreme Court ASR on larger dataset.
2. Having small text segments is good for forced alignment, but does not seem to be good for training. I am yet to confirm this. Consider combining adjacent small segments after forced alignment.
3. Experiment with other Forced Alignment toolkits for better results.
4. Drop very small duration audios from training.
5. Evaluate the results after normalization.
6. Use alternate ASR models, like Wav2Vec2-BER (SeamlessM4T). Having a separate language model on legal domain text should ideally improve the ASR accuracy.
7. Introduce ASR post processing and smart suggestions based on legal LM, for human in the loop editing of ASR output.

#### Scaling to Multilingual Contexts

1. Scaling this strategy to multilingual context would be a further challenging problem.
2. Forced alignment quality for Indic languages need further analysis.
3. Whisper tokens for Indic languages are byte-sized, and hence the output generated one token at a time would be very slow, when compared to English ASR. Strategies for expanding the token set should be used to mitigate this. But this would require continued pretraining.
4. Alternately wav2vec like architectures should be explored for non-English  Indian languages.
5. Better text normalization and inverse text normalization strategies should also be explored for proper training and evaluation of Indic language ASRs.

\
\
