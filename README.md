# reliablity_framework_for_rag

**News!** I added a new data enrichment and LLM reliability [demo](https://github.com/cgnorthcutt/reliablity_framework_for_rag/blob/main/tlm_demo_new.ipynb). Details:
* Demo showing how Trustworthy Language Model add reliability scores to LLM outputs solving 4 use cases for 4 verticals.
* expect typos and imperfection. For better results and more details, visit [https://help.cleanlab.ai](https://help.cleanlab.ai/tutorials/tlm/)


Hacked this together in a couple hours. Shows how Cleanlab TLM can be used to improve fine-tuning of LLMs, accuracy of LLM outputs, and smart routing for RAG and agents.

<img width="1109" alt="image" src="https://github.com/cgnorthcutt/reliablity_framework_for_rag/assets/27030270/f5d5a0e4-2051-4460-bc04-aff1a7640b02">

Dataset used for this example: [here](https://huggingface.co/datasets/nguha/legalbench/viewer/international_citizenship_questions/test?row=2).

## Base Open AI LLM versus Cleanlab TLM Performance on the public test set

Note these results were run with the fastest version of the TLM (`quality_preset="low"`) for speed reasons (its a hackaathon demo). For improved results, use `quality_preset="best"`.

* Base Acc (Open-AI GPT-3.5): ~65%
* TLM Acc: 65.5%

* TLM Acc (TLM Confidence > 0.3): 66.2%
* TLM Acc (TLM Confidence > 0.5): 69.9%
* TLM Acc (TLM Confidence > 0.8): 74.0%


* Base (Open-AI GPT-3.5) Acc (TLM Confidence < 0.5): 55.1%

If an expert reviews/corrects the 100 samples with lowest TLM confidence score:

* the resulting accuracy will be: 79%
* compared to the original base acc: 65%

## The TLM (Trustworthy Langauge Model) is available in Cleanlab Studio

* How to use the TLM: https://help.cleanlab.ai/tutorials/tlm/

There's also a (reduced functionality) demo version available here running on free servers: https://cleanlab.ai/tlm



