# Text Pre-processing pipeline

### Extracting Transcripts

* The extracted segments from the pdf contains many unnecessary information like date and time of proceedings, speaker information, other documentation metadata which are not part of transcript of speech.
* Having speaker information in the speech corpus may be helpful, but not considering as part of this assignment.
* Real text with punctuation and casing will be helpful to train a model, to produce transcripts in a most human readable form. But inorder for the training data to be compatiable with the training pipeline of diverse ASR systems (Whisper, Wav2Vec2-BERT etc.), the plan is to normalize the text.
* The extracted transcripts contain _newline character_ in the middle of the sentences, which has to be removed.
* To get meaningful segments of text, we use _sentencex_ library.
* All this process is automated in this python project.

Source Code: [https://github.com/kavyamanohar/asr-data-pipeline](https://github.com/kavyamanohar/asr-data-pipeline)
