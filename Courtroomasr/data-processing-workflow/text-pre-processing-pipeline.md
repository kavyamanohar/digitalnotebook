# Text Pre-processing pipeline

### Extracting Transcripts

1. The extracted segments from the pdf contains many unnecessary information like date and time of proceedings, speaker information, other documentation metadata which are not part of transcript of speech.
2. Having speaker information in the speech corpus may be helpful, but not considering as part of this assignment.
3. As the plan is to train an ASR model using Whisper, which contains punctuation and numbers in its decoder token, the text is not normalized to remove them.
4. Real text with punctuation and casing will be helpful  to produce transcripts in a most human readable form.&#x20;
5. If some ASR training pipelines require normalized text, the transcripts with punctuation may be removed and normalized  during the training process.
6. To get meaningful segments of text, I use [_sentencex_](https://github.com/wikimedia/sentencex) library.&#x20;
7. Very small segments (<7 words) are combined with previous segments.
8. Since very large sentence segments are not suitable for forced alignment, I split long sentences. Each segment is not more than 15 words in length. (But this would sometimes results in 1-6 word segments)
9. All this process is automated in this python project.
10. The processed text from each pdf is here: [https://github.com/kavyamanohar/pdf-to-transcript/tree/main/data/processed/text](https://github.com/kavyamanohar/pdf-to-transcript/tree/main/data/processed/text).

### Source Code

{% embed url="https://github.com/kavyamanohar/pdf-to-transcript" %}
