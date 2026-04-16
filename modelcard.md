# Model Card, Simulated Translational Oncology DMPK Workflow

## Model summary
This project contains several statistical and machine learning models trained on a simulated oncology DMPK portfolio. The models are intended to demonstrate how early ADME, safety, potency, and translational variables can be integrated for developability classification, human PK prediction, and candidate ranking.

## Models included
### 1. Developability classification
Binary classification models are used to predict whether a compound belongs to the high-developability tier.
Included models:
- Logistic regression.
- Random forest classifier.

### 2. Human PK regression
Regression models are used to estimate projected human pharmacokinetic properties.
Included models:
- Ridge regression.
- Gradient boosting regressor.
- Multilayer perceptron regressor.

### 3. Composite ranking model
A transparent weighted multi-objective score is used to prioritise compounds based on coverage, exposure, safety, and dose-related variables. This is a decision-support ranking framework, not a machine learning model in the strict sense.

## Intended use
These models are intended for:
- Educational demonstration of translational DMPK workflows.
- Portfolio-style illustration of candidate triage and prioritisation.
- Interview, presentation, or skills demonstration in quantitative pharmacology and drug discovery.

These models are not intended for:
- Real medicinal chemistry decisions.
- IND-enabling package generation.
- Clinical dose selection.
- Regulatory submission.
- Patient-level prediction or clinical risk estimation.

## Inputs
Typical model inputs include:
- Molecular descriptors, such as molecular weight, cLogP, topological polar surface area, hydrogen-bond counts, rotatable bonds, pKa, and aromatic ring count.
- ADME variables, such as solubility, plasma free fraction, HLM intrinsic clearance, hepatocyte intrinsic clearance, Caco-2 permeability, and efflux ratio.
- Safety variables, such as CYP inhibition proxies and hERG liability proxy.
- Pharmacology variables, such as biochemical potency, cellular potency, tumor-plasma ratio, and coverage-related quantities.

## Outputs
The workflow produces:
- Probability of high developability.
- Predicted human clearance.
- Predicted oral bioavailability.
- Feature-importance estimates.
- Composite candidate rank.

## Training data
All models were trained on a simulated dataset of 320 compounds. The data were generated to mimic broad literature-style ranges for oncology drug discovery variables. The dataset was not derived from experimental measurements of real candidate molecules.

## Performance summary
### Developability classification
In the executed notebook, the random forest classifier achieved strong performance relative to logistic regression, showing that nonlinear interactions among DMPK features improved prediction of the simulated high-tier class.

### Human PK regression
Oral bioavailability was predicted substantially better than projected human clearance. This suggests that the synthetic data structure encoded oral exposure more directly, while clearance remained a harder endpoint because of its multidimensional determinants.

## Interpretation
Feature-importance results suggested that solubility, intrinsic clearance, hERG margin, lipophilicity, and cellular potency were among the major drivers of high-tier classification in this simulated environment. These findings are qualitatively consistent with how developability is often viewed in translational DMPK.

## Assumptions
- The dataset is synthetic and rule-informed.
- Labels partly reflect the simulation logic used to generate compound quality tiers.
- Relationships among variables are simplified and may not capture full biological or pharmacokinetic complexity.
- The PK/PD component is a simplified scenario model, not a full PBPK or QSP framework.

## Limitations
- No real experimental compounds are represented.
- The models may overstate performance because the simulation embeds coherent structure.
- External validity is unknown.
- Safety and DDI variables are simplified proxies.
- Tumor exposure is represented by reduced-form surrogates rather than full tissue distribution modelling.

## Ethical and practical considerations
This workflow should not be used to make real scientific, clinical, or regulatory decisions. It is best viewed as a transparent computational demonstration of how DMPK data, modelling, and machine learning can be combined in a candidate-selection framework.

## Maintenance
This model card applies to the current proof-of-concept notebook and associated simulated dataset. Any future expansion to real data would require substantial revision of the model description, validation framework, performance metrics, and risk statement.
