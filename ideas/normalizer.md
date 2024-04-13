# Normalizer

## Why do you need a normalizer?

There are multiple valid ways to represent same text. You may need to have a unified form for easy processing by machines. There are multiple projects to perform normalizations

1. Whisper Normalizer
   1. OpenAI: [https://github.com/openai/whisper/tree/main/whisper/normalizers](https://github.com/openai/whisper/tree/main/whisper/normalizers)
   2. Huggingface: [https://github.com/huggingface/transformers/blob/7319850902ba9b2a44c36ccddd044f98abd9b597/src/transformers/models/whisper/english\_normalizer.py](https://github.com/huggingface/transformers/blob/7319850902ba9b2a44c36ccddd044f98abd9b597/src/transformers/models/whisper/english\_normalizer.py)
   3. Kurian Binoy: [https://github.com/kurianbenoy/whisper\_normalizer](https://github.com/kurianbenoy/whisper\_normalizer)
2. Indic NLP Library Normalizer:
   1. [https://github.com/anoopkunchukuttan/indic\_nlp\_library/tree/master/indicnlp/normalize](https://github.com/anoopkunchukuttan/indic\_nlp\_library/tree/master/indicnlp/normalize)
3. LibIndic Normalizer:
   1. [https://github.com/libindic/normalizer](https://github.com/libindic/normalizer)

The depth and breadth of English Language normalization in Whisper gives it a much higher ground on evaluating it on benchmark datasets.

The normalization in Whisper for Indic languges is buggy. It removes all vowel signs. No good normalizers for Indic languages.

Some observations:\
\
Sharing insights from my recent exploration into Indic Language Normalizers!\
\
Evaluating WER without normalization can unfairly penalize ASR model performance. Thus, effective normalization is essential, taking care of valid alternate spellings, equivalent Unicode characters, punctuation, and more.\
\
My interest in this area was kindled when I discovered that [OpenAI](https://www.linkedin.com/company/openai/) Whisper's evaluation strategy removes many relevant characters from Indian language scripts, rendering the evaluation meaningless. A sample image attached.\
\
There's a lack of proper normalization routines defined in Indian languages. Existing Indic normalizers do not address abbreviations, currency symbols, fractions, and numbers for ASR and TTS tasks.\
\
[Santhosh Thottingal](https://www.linkedin.com/in/santhoshthottingal/) in LibIndic and [Anoop Kunchukuttan](https://www.linkedin.com/in/anoopkunchukuttan/) in IndicNLP Library cover some use cases, including some corpora cleanups. Clean-up is crucial because online Indic language content often contains spurious or swapped characters. Malayalam characters like ഃ, ർ, ൻ are frequently misrepresented, even in government databases and curated corpora as :, ൪, ൯.\
\
Effective Indic text normalization requires a pre-normalizer for cleanup before actual normalization. I emphasize the importance of applying cleanup to training corpora to prevent ASRs, LLMs, and MT systems from producing erroneous characters in output, especially considering the rise of generative content on the web.\
\


{% embed url="https://www.linkedin.com/posts/kavya-manohar_indiclanguagenormalization-asr-tts-activity-7163964868541267968-iI2q?utm_medium=member_desktop&utm_source=share" %}
