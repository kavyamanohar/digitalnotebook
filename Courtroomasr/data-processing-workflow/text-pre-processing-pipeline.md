# Text Pre-processing pipeline

### Extracting Transcripts

* The extracted segments from the pdf contains many unnecessary information like date and time of proceedings, speaker information, other documentation metadata which are not part of transcript of speech.
* Having speaker information in the speech corpus may be helpful, but not considering as part of this assignment.
* Real text with punctuation and casing will be helpful to train a model, to produce transcripts in a most human readable form.&#x20;
* If some ASR training pipelines require normalized text, the transcripts with punctuation may be removed and normalized  during the training process.
* To get meaningful segments of text, I use [_sentencex_](https://github.com/wikimedia/sentencex) library.&#x20;
* Since very small sentence segments are not suitable for forced alignment, I combine adjacent sentences. Each segment is at least 7 words in length.
* All this process is automated in this python project.

Source Code: [https://github.com/kavyamanohar/pdf-to-transcript](https://github.com/kavyamanohar/pdf-to-transcript)
