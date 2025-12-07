# Detecting Microaggressions Using LLM-Generated Counterfactuals: Transformer Cross-Domain Evaluation and LLM Classification

**Authors:** Nura Hossainzadeh, Neeha Kotte, Carlos Schrupp  

---

## Abstract

Microaggressions are subtle forms of hate speech. Because they are not directly or explicitly offensive in nature, they require a nuanced approach to identify accurately, particularly in text. Our study presents both transformer and LLM (GPT-5.1) models that are able to detect microaggressive speech with a high degree of accuracy. The key to achieving this result was the development of a novel dataset, used to train our transformer models and evaluate our LLM model, consisting of microaggressive statements from a well-known corpus paired with LLM-generated non-microaggressive counterparts that matched their linguistic and stylistic properties while differing in semantic meaning. We found that our LLM model achieved a 90% accuracy on a 100-entry sample of our generated dataset. Of the transformer models we tested, DeBERTa exhibited the best performance, achieving high accuracy (81.87%) even when cross-evaluated on a previously unseen workplace microaggressions dataset on which it had not been trained.

---

## Introduction

The term “microaggression” was coined by African American psychiatrist and Harvard professor Chester Pierce in 1970 to describe “subtle” and “often automatic” offenses directed against people of color. Since then, the concept has been extended to other marginalized groups. Microaggressions often implicitly demean or stereotype a person’s heritage or identity (for example, by telling a person of color “you are a credit to your race”), or they may exclude or minimize the thoughts and experiences of a marginalized person (for example, telling a stay-at-home mother “life must be breeze when you don’t have to work”) (Sue and Spanierman, 2020). Because they are so subtle, the responsibility of raising awareness about microaggressions often falls on the shoulders of marginalized groups. Having to experience and simultaneously prove the existence of microaggressions has been found to have long-term adverse physical and emotional effects on victims; in fact, this double burden can have a more debilitating effect than explicitly aggressive acts (Sue, 2010; Nadal et al., 2014).

With the explosive growth of social media and online communication, hate speech and microaggressions have become pervasive in digital text. Therefore, it has become increasingly important to develop methods of identifying microaggressions, a task modern natural language processing models can be leveraged for. Previous work has mostly focused on explicit hate (see, for example, Miqdadi et al., 2024; Benítez-Andrades et al., 2022; and Lee et al., 2022), but much less research has been completed on how and whether natural language processing can be used to classify microaggressions. While hate speech is overtly violent, microaggressions are linguistically softer, and violent meaning emerges from non-violent words. The difficulty of classifying microaggressions is compounded by the fact that contextual factors, such as cultural knowledge, body language, and tone, may not be accessible to the model. For instance, a seemingly innocuous joke about "turning someone in" may be deeply offensive given recent instances of police violence and brutality. Therefore, these complex subtleties, combined with the quick, implicit cadences of microaggressions, present fundamental challenges for machine learning algorithms.

Our work addresses this challenge by composing BERT and LLM model-based classifiers, trained on a novel microaggressions dataset, that have learned to effectively differentiate microaggressions and non-microaggressions. We confirm this with strong cross-evaluation performance on a second smaller dataset composed of microaggressions expressed in a workplace context unseen during training.

Our second contribution is an engineered, balanced dataset composed of, first, microaggressions drawn from a well known microaggression corpus, and second, LLM-generated non-microaggressions that mirror the syntax and style of the microaggression. This larger, balanced corpus of microaggressive and non-microaggressive statements differ primarily in meaning rather than in surface-level linguistic or stylistic features, allowing models trained on this dataset to focus on learning what distinguishes microaggressions semantically.

Beyond its scholarly and scientific relevance, our work has practical relevance. Hate speech–microaggressive or not–is an impediment to social justice, insofar as it mutes and intimidates minority voices and undermines their well-being. Our hope is that these models can be used to detect microaggressive speech in online fora to moderate content and create safer spaces for minorities to exist and express themselves. We consider our approach successful if, first, our performance on the evaluation datasets yields an overall accuracy of at least ten percentage points above our baseline, and second, if we observe high precision on the microaggressions class (and consequently a high F1-score); this would indicate that our classifier has learned what fundamentally characterizes microaggressive statements.

---

## Key Contributions

- **LLM-generated counterfactual dataset**: A balanced corpus where each microaggressive statement is paired with a non-microaggressive rewrite that preserves topic and style while changing semantic content.
- **Transformer cross-domain evaluation**: BERT-family models (including DeBERTa) trained on the counterfactual dataset and evaluated both in-domain and on an out-of-domain workplace microaggressions corpus.
- **LLM classification**: GPT-5.1 used as a zero-shot classifier with a carefully engineered prompt, achieving 90% accuracy on a 100-example sample of the generated dataset.
- **Proxy audits and readability checks**: Readability metrics and unsupervised clustering analyses to verify that models cannot rely solely on superficial stylistic differences between classes.

---

## Repository Structure

- `Notebooks/`  
  - `1_*.ipynb` — Main pipeline (counterfactual generation, CNN baseline, BERT/DeBERTa training, LLM evaluation, readability metrics, proxy audit).  
  - `2_*.ipynb`–`9_*.ipynb` — Additional experiments (scraping, EDA, SBIC/Toxigen balancing attempts, sequential transfer learning, extended readability analysis).
- `Datasets/` (paths / loaders for external datasets; see paper for details)
- `paper/` (final write-up, if included in the repo)
- `presentation/` (final presentation)

---

## How to Cite

If you use this work, please cite the project as:

> Hossainzadeh, N., Kotte, N., & Schrupp, C. (2025). *Detecting Microaggressions Using LLM-Generated Counterfactuals: Transformer Cross-Domain Evaluation and LLM Classification*. W266 Final Project, UC Berkeley MIDS.

