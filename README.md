## Proposal: Detecting Racial Microaggressions in Text

The term **“microaggression”** was coined by African American psychiatrist and Harvard professor **Chester Pierce in 1978** to describe “subtle” and “often automatic” offenses directed against people of color. Since then, the concept has been extended to other marginalized groups.

When racial, they are, according to one prominent group of scholars, **“brief and commonplace daily verbal, behavioral, or environmental indignities, whether intentional or unintentional, that communicate hostile, derogatory, or negative racial slights and insults towards people of color”** (D.W. Sue, Capodilupo, et. al., 2007). Because microaggressions often perpetuate subtle forms of bias, they can often be difficult to identify accurately, particularly in text.

---

## Project Aim and Approach

Therefore, our aim is to use **natural language processing** techniques to help us identify these phenomena when they are articulated in text. Our approach involves **fine-tuning a DeBERTa-v3 or RoBERTa encoder** into a classifier trained on two families of signals:

1.  **Sarcasm**
2.  **Racist Content** (including, more specifically, implicit hatred, social bias, and toxicity directed toward racial identity)

Our goal is to build a classifier which can detect sarcastic, racially biased remarks, i.e., one form of racial microaggression.

---

## Datasets for Training

We will use public datasets, referenced by existing literature, to train on these signals:

| Signal Type | Dataset | Reference |
| :--- | :--- | :--- |
| **Implicit Hate** | ToxiGen | Hartvigsen et al., 2022 |
| **Social Bias** | Social Bias Inference Corpus (SBIC) | |
| **Identity-Aware Toxicity** | Jigsaw | Sahoo et al., 2022 |
| **Sarcasm** | Self-Annotated Reddit Corpus (SARC) and/or iSarcasmEval | Abu Farha et al., 2022 |

---

## Validation Strategy

While labeled microaggressions datasets are challenging to find, prior work on detecting microaggressions with NLP, such as Breitfeller et al., EMNLP-IJCNLP 2019, commonly references a compiled source of microaggressive comments from Tumblr: **www.microaggressions.com**.

We plan to **scrape racially microaggressive comments from this website** (specifically those tagged with “race”) and then **test the extent to which our algorithm is able to positively label these statements as microaggressions.**
