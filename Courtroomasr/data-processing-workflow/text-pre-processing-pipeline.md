---
icon: table
---

# Text Pre-processing pipeline

### Extracting Transcripts

1. The extracted segments from the pdf contains many unnecessary information like date and time of proceedings, speaker information, other documentation metadata which are not part of transcript of speech.
2. Having speaker information in the speech corpus may be helpful, but not considering as part of this assignment.
3. Eventhough the plan is to train an ASR model using Whisper, which contains punctuation and numbers in its decoder tokenizer, the transcript is normalized with Nemo text processing library.&#x20;
   1. But it does not exactly correspond to what was spoken.  (eg: 15 is normalized to fifteen while it was spoken as one-five)
   2. Contractions are retained as such (won't, I'm)
   3. Punctuation are retained.
4. If some ASR training pipelines require fully normalized text, the transcripts with punctuation may be cleaned  during the training process.
5. To get meaningful segments of text, I use Nemo text processing library.&#x20;
6. Since very large sentence segments are not suitable for forced alignment, I split long sentences. Each segment is not more than 15 words in length. (But this would sometimes results in 1-2 word segments)
7. All this process is automated in this python project.

### Source Code

{% embed url="https://github.com/kavyamanohar/pdf-to-transcript" %}
