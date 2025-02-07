# Forced Alignment

There are different ways to align the text with audio. I solved it as a text-audio Forced Alignment Problem. &#x20;

#### Forced Alignment with Aeneas

* It is a TTS (espeak) based forced alignment pipeline. But the repo is not in active maintenance. It can give the transcript aligned with time-stamps in srt format of subtitles.
* Ran into multiple issues during local system installation including numpy version mismatch. However installation went well on Google Colab and the alignment was done there.

### Challenges

* Word repetitions that are not in the transcripts affects alignment, and the error propogates to subsequent time stamps.
* Some times, punctuations are exactly spken: eg: "Full-Stop", "Comma". It also affects alignments.

## Source Code:

{% embed url="https://github.com/kavyamanohar/audioslicer/blob/master/forced-alignment.py" %}

