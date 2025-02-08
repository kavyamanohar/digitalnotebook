# ASR for Supreme Court Hearing

Used Whisper Small architecture to train the ASR model using the data created using the pipeline described. Only a subset of the dataset (\~3 hours) was used for training the ASR model. The plan is to iteratively improve the model with additional data.&#x20;

### MODEL

{% embed url="https://huggingface.co/kavyamanohar/whisper-supreme-court-asr" %}

### Rationale of Model Choice

* The dataset was prepared with  punctuation retained to the maximum extent possible. This was to ensure model output to be best suited for human consumption, with little additional post processing. Whisper is designed to be trained on such text.
* The second reason for the choice of Whisper was its reasonably good performance on English speech.&#x20;

### Initial Results

The model is expected to perform reasonably well, since it is already pretrained on English. But the WER on the validation data does not seem to converge. It is oscillating in the rage \~60%. Since the model did not converge well, I did not work on an extensive evaluation.

