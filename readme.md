# XSTest: A Test Suite for Identifying Exaggerated Safety Behaviours in Large Language Models

Without proper safeguards, large language models will follow malicious instructions and generate toxic content.
This motivates safety efforts such as red-teaming and large-scale feedback learning, which aim to make models both helpful and harmless.
However, there is a tension between these two objectives, since harmlessness requires models to refuse to comply with unsafe prompts, and thus not be helpful.
Recent anecdotal evidence suggests that some models may have struck a poor balance, so that even clearly safe prompts are refused if they use similar language to unsafe prompts or mention sensitive topics.
With XSTest, we introduce a new test suite to identify such eXaggerated Safety behaviours in a structured and systematic way.
XSTest comprises 250 safe prompts across ten prompt types that well-calibrated models should not refuse to comply with, and 200 unsafe prompts as contrasts that, for most LLM applications, should be refused.
In our paper, we describe XSTest's creation and composition, and use the test suite to highlight systematic failure modes in state-of-the-art language models as well as more general challenges in building safer language models.

XSTest is joint work between Paul Röttger, Hannah Rose Kirk, Bertie Vidgen, Giuseppe Attanasio, Federico Bianchi, and Dirk Hovy.
For more details on XSTest, please refer to our arxiv preprint: [https://arxiv.org/abs/2308.01263](https://arxiv.org/abs/2308.01263)


### Repo Structure

**xstest_prompts_v2.csv** contains all test prompts.

In the **model_completions** folder, you can find model responses on XSTest by five different models.
Please refer to our paper for more details on the models and how we collected model responses.

In **model_evaluation** we share a notebook, **analysis.ipynb** for analysing labelled model responses on XSTest.
We also share two scripts to automatically label model responses (**classify_completions.py**), and their results on all model completions (**automated_evaluation_labels**).


### Using XSTest

1. Download **xstest_prompts_v2.csv**
2. Using the language model you want to test, collect responses on the test prompts listed in the "prompt" column of the csv.
3. Classify your model responses as refusals or compliance. You can either manually label the responses, or use our automated evaluation scripts (**classify_completions.py**) in the **evaluation** folder. See our paper for a taxonomy of model responses.
4. Lastly, analyse your model responses. You can use the **analysis.ipynb** notebook to replicate the analyses from our paper.
Your model should ideally comply with safe prompts, and, for most applications, refuse to comply with unsafe prompts, which are those where the "type" starts with "contrast_".


### License
The test prompts are subject to Creative Commons Attribution 4.0 International license.
The model completions are subject to the original licenses specified by Meta, Mistral and OpenAI.