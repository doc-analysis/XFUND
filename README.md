# XFUND: A Multilingual Form Understanding Benchmark

## Introduction

XFUND is a multilingual form understanding benchmark dataset that includes human-labeled forms with key-value pairs in 7 languages (Chinese, Japanese, Spanish, French, Italian, German, Portuguese).

## Download

- XFUND v1.0: https://github.com/doc-analysis/XFUND/releases/tag/v1.0

## Statistics

| lang | split    | header | question | answer | other | total  |
| ---- | -------- | ------ | -------- | ------ | ----- | ------ |
| ZH   | training | 441    | 3,266    | 2,808  | 896   | 7,411  |
|      | testing  | 122    | 1,077    | 821    | 312   | 2,332  |
| JA   | training | 229    | 3,692    | 4,641  | 1,666 | 10,228 |
|      | testing  | 58     | 1,253    | 1,732  | 586   | 3,629  |
| ES   | training | 253    | 3,013    | 4,254  | 3,929 | 11,449 |
|      | testing  | 90     | 909      | 1,218  | 1,196 | 3,413  |
| FR   | training | 183    | 2,497    | 3,427  | 2,709 | 8,816  |
|      | testing  | 66     | 1,023    | 1,281  | 1,131 | 3,501  |
| IT   | training | 166    | 3,762    | 4,932  | 3,355 | 12,215 |
|      | testing  | 65     | 1,230    | 1,599  | 1,135 | 4,029  |
| DE   | training | 155    | 2,609    | 3,992  | 1,876 | 8,632  |
|      | testing  | 59     | 858      | 1,322  | 650   | 2,889  |
| PT   | training | 185    | 3,510    | 5,428  | 2,531 | 11,654 |
|      | testing  | 59     | 1,288    | 1,940  | 882   | 4,169  |

## Baselines

For the code example, please refer to the [LayoutXLM repository](https://github.com/microsoft/unilm/tree/master/layoutxlm). 

## Results

###  Language-specific Finetuning

|                             | Model              | FUNSD      | ZH         | JA         | ES         | FR         | IT         | DE         | PT         | Avg.       |
| --------------------------- | ------------------ | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- |
| Semantic Entity Recognition | `xlm-roberta-base` | 0.667      | 0.8774     | 0.7761     | 0.6105     | 0.6743     | 0.6687     | 0.6814     | 0.6818     | 0.7047     |
|                             | `infoxlm-base`     | 0.6852     | 0.8868     | 0.7865     | 0.6230     | 0.7015     | 0.6751     | 0.7063     | 0.7008     | 0.7207     |
|                             | `layoutxlm-base`   | **0.794**  | **0.8924** | **0.7921** | **0.7550** | **0.7902** | **0.8082** | **0.8222** | **0.7903** | **0.8056** |
| Relation Extraction         | `xlm-roberta-base` | 0.2659     | 0.5105     | 0.5800     | 0.5295     | 0.4965     | 0.5305     | 0.5041     | 0.3982     | 0.4769     |
|                             | `infoxlm-base`     | 0.2920     | 0.5214     | 0.6000     | 0.5516     | 0.4913     | 0.5281     | 0.5262     | 0.4170     | 0.4910     |
|                             | `layoutxlm-base`   | **0.5483** | **0.7073** | **0.6963** | **0.6896** | **0.6353** | **0.6415** | **0.6551** | **0.5718** | **0.6432** |

### Zero-shot Transfer Learning

|     | Model              | FUNSD      | ZH         | JA         | ES         | FR         | IT         | DE         | PT         | Avg.       |
| --- | ------------------ | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- |
| SER | `xlm-roberta-base` | 0.667      | 0.4144     | 0.3023     | 0.3055     | 0.371      | 0.2767     | 0.3286     | 0.3936     | 0.3824     |
|     | `infoxlm-base`     | 0.6852     | 0.4408     | 0.3603     | 0.3102     | 0.4021     | 0.2880     | 0.3587     | 0.4502     | 0.4119     |
|     | `layoutxlm-base`   | **0.794**  | **0.6019** | **0.4715** | **0.4565** | **0.5757** | **0.4846** | **0.5252** | **0.539**  | **0.5561** |
| RE  | `xlm-roberta-base` | 0.2659     | 0.1601     | 0.2611     | 0.2440     | 0.2240     | 0.2374     | 0.2288     | 0.1996     | 0.2276     |
|     | `infoxlm-base`     | 0.2920     | 0.2405     | 0.2851     | 0.2481     | 0.2454     | 0.2193     | 0.2027     | 0.2049     | 0.2423     |
|     | `layoutxlm-base`   | **0.5483** | **0.4494** | **0.4408** | **0.4708** | **0.4416** | **0.4090** | **0.3820** | **0.3685** | **0.4388** |

### Multitask Fine-tuning

|     | Model              | FUNSD      | ZH         | JA         | ES         | FR         | IT         | DE         | PT         | Avg.       |
| --- | ------------------ | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- |
| SER | `xlm-roberta-base` | 0.6633     | 0.883      | 0.7786     | 0.6223     | 0.7035     | 0.6814     | 0.7146     | 0.6726     | 0.7149     |
|     | `infoxlm-base`     | 0.6538     | 0.8741     | 0.7855     | 0.5979     | 0.7057     | 0.6826     | 0.7055     | 0.6796     | 0.7106     |
|     | `layoutxlm-base`   | **0.7924** | **0.8973** | **0.7964** | **0.7798** | **0.8173** | **0.821**  | **0.8322** | **0.8241** | **0.8201** |
| RE  | `xlm-roberta-base` | 0.3638     | 0.6797     | 0.6829     | 0.6828     | 0.6727     | 0.6937     | 0.6887     | 0.6082     | 0.6341     |
|     | `infoxlm-base`     | 0.3699     | 0.6493     | 0.6473     | 0.6828     | 0.6831     | 0.6690     | 0.6384     | 0.5763     | 0.6145     |
|     | `layoutxlm-base`   | **0.6671** | **0.8241** | **0.8142** | **0.8104** | **0.8221** | **0.8310** | **0.7854** | **0.7044** | **0.7823** |

## Citation

If you find XFUND useful in your research, please cite the following paper:

``` latex
@inproceedings{xu-etal-2022-xfund,
    title = "{XFUND}: A Benchmark Dataset for Multilingual Visually Rich Form Understanding",
    author = "Xu, Yiheng  and
      Lv, Tengchao  and
      Cui, Lei  and
      Wang, Guoxin  and
      Lu, Yijuan  and
      Florencio, Dinei  and
      Zhang, Cha  and
      Wei, Furu",
    booktitle = "Findings of the Association for Computational Linguistics: ACL 2022",
    month = may,
    year = "2022",
    address = "Dublin, Ireland",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2022.findings-acl.253",
    doi = "10.18653/v1/2022.findings-acl.253",
    pages = "3214--3224",
    abstract = "Multimodal pre-training with text, layout, and image has achieved SOTA performance for visually rich document understanding tasks recently, which demonstrates the great potential for joint learning across different modalities. However, the existed research work has focused only on the English domain while neglecting the importance of multilingual generalization. In this paper, we introduce a human-annotated multilingual form understanding benchmark dataset named XFUND, which includes form understanding samples in 7 languages (Chinese, Japanese, Spanish, French, Italian, German, Portuguese). Meanwhile, we present LayoutXLM, a multimodal pre-trained model for multilingual document understanding, which aims to bridge the language barriers for visually rich document understanding. Experimental results show that the LayoutXLM model has significantly outperformed the existing SOTA cross-lingual pre-trained models on the XFUND dataset. The XFUND dataset and the pre-trained LayoutXLM model have been publicly available at https://aka.ms/layoutxlm.",
}
```

## License

The content of this project itself is licensed under the [Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0)](https://creativecommons.org/licenses/by-nc-sa/4.0/)
Portions of the source code are based on the [transformers](https://github.com/huggingface/transformers) project.
[Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct)

### Contact Information

For help or issues using XFUND, please submit a GitHub issue.

For other communications related to XFUND, please contact Lei Cui (`lecu@microsoft.com`), Furu Wei (`fuwei@microsoft.com`).

