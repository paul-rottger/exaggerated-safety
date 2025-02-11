# XSTest: A Test Suite for Identifying Exaggerated Safety Behaviours in Large Language Models

This repo contains data and code for our NAACL 2024 paper "[XSTest: A Test Suite for Identifying Exaggerated Safety Behaviours in Large Language Models](https://aclanthology.org/2024.naacl-long.301/)".
XSTest is joint work between Paul Röttger, Hannah Rose Kirk, Bertie Vidgen, Giuseppe Attanasio, Federico Bianchi, and Dirk Hovy.


## Repo Structure

`xstest_prompts.csv` contains all test prompts.

```
├── evaluation /            # Scripts for automated evaluation
├── model_completions /     # Model completions on XSTest
```


## Using XSTest

1. Download `xstest_prompts.csv` from this repository.
2. Using the language model you want to test, collect responses on the test prompts listed in the "prompt" column of the csv.
3. Classify your model responses as refusals or compliance. You can either manually label the responses, or use our automated evaluation scripts (`classify_completions.py`) in the `evaluation` folder. See our paper for a taxonomy of model responses.
4. Analyse your labeled model responses. You can use the `analysis.ipynb` notebook to replicate the analyses from our paper.
Your model should ideally comply with safe prompts, and, for most applications, refuse to comply with unsafe prompts, which are those where the "type" starts with "contrast_".

## Citation Information
If you use XSTest, please cite our NAACL 2024 paper:
```bibtex
@inproceedings{rottger-etal-2024-xstest,
    title = "{XST}est: A Test Suite for Identifying Exaggerated Safety Behaviours in Large Language Models",
    author = {R{\"o}ttger, Paul  and
      Kirk, Hannah  and
      Vidgen, Bertie  and
      Attanasio, Giuseppe  and
      Bianchi, Federico  and
      Hovy, Dirk},
    editor = "Duh, Kevin  and
      Gomez, Helena  and
      Bethard, Steven",
    booktitle = "Proceedings of the 2024 Conference of the North American Chapter of the Association for Computational Linguistics: Human Language Technologies (Volume 1: Long Papers)",
    month = jun,
    year = "2024",
    address = "Mexico City, Mexico",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2024.naacl-long.301/",
    doi = "10.18653/v1/2024.naacl-long.301",
    pages = "5377--5400"
}
```


## License
XSTest prompts are subject to Creative Commons Attribution 4.0 International (CC-BY-4.0) license.
The model completions are subject to the original licenses specified by Meta, Mistral and OpenAI.