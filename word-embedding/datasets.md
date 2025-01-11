# Datasets

1. **Indic Paraphrase**
   1. Released as part of Indic NLG Suite
   2. Contains 782k [Malayalam](https://huggingface.co/datasets/ai4bharat/IndicParaphrase/viewer/ml) samples.&#x20;
   3.  The five data points

       ```
       id (string): Unique identifier.
       pivot (string): English sentence used as the pivot
       input (string): Input sentence
       references (list of strings): Paraphrases of input, ordered according to the least n-gram overlap
       target (string): The first reference (most dissimilar paraphrase)
       ```
2. **Indic X Paraphrase** - AI4Bharat,
   1. Contains 2k [Malayalam](https://huggingface.co/datasets/ai4bharat/IndicXParaphrase/viewer/ml) samples . Good quality adversarial paraphrases translated from English. No related documentation. Adversarial paraphrase datasets have high ngram overlap but dissimilar or even opposite meanings.
3. L3CubePune - describes an Indic Semantic Textual Similarity Corpus created using Google Translate. Not Published as public document.&#x20;
   1. Example: [https://huggingface.co/datasets/PhilipMay/stsb\_multi\_mt/viewer/en](https://huggingface.co/datasets/PhilipMay/stsb_multi_mt/viewer/en)
4. Google Published Adversarial Paraphrase dataset in English using word scrabling, back translation and human involvement: [https://github.com/google-research-datasets/paws](https://github.com/google-research-datasets/paws)
5. An multilingual Version of the same with 6 languages: [https://github.com/google-research-datasets/paws/tree/master/pawsx](https://github.com/google-research-datasets/paws/tree/master/pawsx)
6. **THERE IS A NEED FOR HIGH QUALITY ADVERSERIAL PARAPHRASE DATASET.  It can be created using Mlmorph.**
   1. **Simple paraphrases with same meaning**
      1. ഇന്ത്യയുടെ തലസ്ഥാനം ന്യൂഡൽഹിയാണ
      2. &#x20;ഇന്ത്യയുടെ തലസ്ഥാനം ഡൽഹിയാണ്
      3. &#x20;ഭാരതത്തിന്റെ തലസ്ഥാനം ഡൽഹി ആണ്
      4. ഡൽഹിയാണ് ഭാരതത്തിന്റെ തലസ്ഥാനം
   2. Adversarial Samples with high ngram overlap
      1. &#x20;ഇന്ത്യയുടെ തലസ്ഥാനം ഡാൽഹിയല്ല
      2. ഇന്ത്യയുടെ തലസ്ഥാന ഡൽഹി അല്ല
