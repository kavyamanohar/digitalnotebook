# Data Processing Workflow

We are provided with the video (Youtube links) and audio (in mp3 format) extracted from the video.  The transcript of courtroom proceedings, prepared by [TERES](https://teres.ai/) is provided in a pdf format. The transcript has proper speaker annotation, but no timestamps.

The task is to preprocess the speech and audio data into a format suitable for ASR training. This involves aligning the speech data with the transcript so that the audio can be sliced into smaller chunks <= 20s with associated transcripts.

The minimal requirement is to have a dataset in the following format



<table><thead><tr><th>Audio Filepath</th><th>Transcript</th><th data-type="number">Duration (s)</th></tr></thead><tbody><tr><td>audio1.wav</td><td>That can be postponed, their putting it up on the website.</td><td>2.34</td></tr><tr><td>audio2.wav</td><td>Fair enough. No objection</td><td>1.7</td></tr></tbody></table>

A better processing pipeline would be to include some additional information like speaker and duration information. Duration info helps to drop very small and very large audio segments during training nd evaluation.\
\


<figure><img src="../.gitbook/assets/data-processing-pipeline.drawio (3).png" alt=""><figcaption><p>Data Processing Pipeline</p></figcaption></figure>

## Audio Slicing

The ultimate aim is to slice the audio with matching transcripts. This involves a [Forced Alignment](./#text-processing-pipeline) (FA) step where audio and transcript are aligned with time stamps. Slicing the audio can be done once you have proper time stamps.

#### Audio Slicer

Once you have the time stamps it can be easily converted to SRT format of subtitles. I had a 5 year old [side-project](https://github.com/kavyamanohar/audioslicer) that created audio chunks based on information from the srt files. It works out-of-the box. But modernized it with functionalities like pushing to huggingface hub.

### Challenges

1. The CTC-Forced-Aligner provides timestamps at different granularity (characters, words and sentences). For our use case it would be the best to use sentences. The tool uses NLTK  for sentence splitting, but the splitting happens after abbreviations like Mr.&#x20;
2. Unlike popular read speech datasets, real court-room conversations contain very small spoken sentences like 'That's right' which takes less than 1s duration. Such small audio slices are not suitable for ASR training \[citation to be added]. Such small audios may be dropped from training.

