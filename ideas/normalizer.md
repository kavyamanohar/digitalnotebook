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

The normalization in Whisper for Indic languges is buggy. It removes all vowel signs. No good normalizers for Indic languages.\


{% embed url="https://www.linkedin.com/posts/kavya-manohar_indiclanguagenormalization-asr-tts-activity-7163964868541267968-iI2q?utm_medium=member_desktop&utm_source=share" %}
