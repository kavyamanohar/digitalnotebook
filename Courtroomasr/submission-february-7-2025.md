# SUBMISSION (February 7, 2025)

## DATASET

Created a small subset of the full speech, by randomly selecting some of the given  Court Hearings.

#### Subset Corpus

{% embed url="https://huggingface.co/datasets/kavyamanohar/supreme-court-speech" %}
Supreme Court Speech - Subset
{% endembed %}

The Court ASR model is trained on this subset.

#### Full Corpus

[https://huggingface.co/datasets/kavyamanohar/court-speech-full](https://huggingface.co/datasets/kavyamanohar/court-speech-full)

## SOURCE CODE

### TRANSCRIPT TEXT EXTRACTION FROM PDF

{% embed url="https://github.com/kavyamanohar/pdf-to-transcript" %}

### AUDIO PROCESSING PIPELINE

{% embed url="https://github.com/kavyamanohar/audioslicer" %}

## MODEL

{% embed url="https://huggingface.co/kavyamanohar/whisper-supreme-court-asr" %}

This dataset is trained on a subset of the shared dataset.&#x20;

### WHY SUBSET OF DATA WAS USED?

I had to experiment the best strategy to align the audio and text. So started working on a subset. Even though the alignment problem and the corpus creation went well, the ASR model did not turn out to be good. Also I had GPU compute limits.So I decided to submit the model trained on the subset.

\
&#xNAN;_&#x54;he problem is interesting and challenging. I might continue working on this. Any updates in the model and dataset will be added in the_ [_POSTSCRIPT_](https://app.gitbook.com/o/VnQ9RL8nQMN36Bamm2hZ/s/lRUi8Jpx8HrreCmmXG5o/~/changes/8/post-script) _Section._\
\
