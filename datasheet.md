# Datasheet, Simulated Oncology DMPK 

## Dataset name
Simulated translational oncology DMPK

## Motivation
The dataset was created to support a proof-of-concept workflow demonstrating how DMPK, translational pharmacology, and machine learning can be integrated for oncology candidate evaluation. The aim was to provide a coherent portfolio of compounds with realistic-looking variability across physicochemical properties, ADME measurements, safety proxies, potency variables, and translational PK outputs.

## Composition
The dataset contains 320 simulated compounds. Each row corresponds to one synthetic compound entry. The dataset includes continuous variables, categorical annotations, derived translational metrics, and rule-based developability labels.

## Data collection process
No laboratory experiments, animals, or human participants were involved. The dataset was generated computationally using simulated values informed by broad ranges commonly encountered in peer-reviewed DMPK and pharmacology literature. The dataset is therefore synthetic.

## Preprocessing
The notebook includes basic preprocessing steps for:
- Variable inspection.
- Feature selection for classification and regression.
- Standardisation where appropriate for certain models.
- Train-test splitting for supervised learning tasks.

## Variables
Representative variables include:
- Compound identifier.
- Putative mechanism or class.
- Molecular weight.
- cLogP.
- Topological polar surface area.
- Hydrogen-bond donor count.
- Hydrogen-bond acceptor count.
- Rotatable bond count.
- pKa.
- Aromatic ring count.
- Solubility.
- Plasma free fraction.
- Human liver microsomal intrinsic clearance.
- Hepatocyte intrinsic clearance.
- Caco-2 apparent permeability.
- Efflux ratio.
- CYP3A4 inhibition proxy.
- CYP2D6 inhibition proxy.
- hERG liability proxy.
- Biochemical IC50.
- Cellular EC50.
- Mouse clearance.
- Oral bioavailability.
- Tumor-plasma ratio.
- Projected human clearance.
- Projected human half-life.
- Predicted effective human dose.
- Coverage ratio.
- DDI burden score.
- Safety margin score.
- Developability tier.

## Label generation
The developability tier is a simulated label. It is not experimentally annotated. It was assigned using internal decision rules designed to reflect intuitive trade-offs among exposure, clearance, safety, permeability, potency, and dose feasibility.

## Uses
Appropriate uses:
- Demonstrating exploratory data analysis in DMPK.
- Demonstrating clustering and portfolio segmentation.
- Demonstrating supervised machine learning for developability classification and translational endpoint prediction.
- Demonstrating candidate ranking logic.
- Building presentations, teaching materials, or portfolio examples.

Inappropriate uses:
- Any real drug discovery programme decision.
- Benchmarking commercial drug candidates.
- Regulatory or clinical use.
- Claims about actual compounds or modalities.

## Distributional characteristics
The dataset was designed to include:
- A broad clearance range from favorable to high-clearance compounds.
- A wide exposure range across oral bioavailability and half-life.
- Meaningful tension between lipophilicity and solubility.
- Variable tumor distribution and free exposure.
- A balanced spread across low, medium, and high developability groups.

## Known limitations
- Because the dataset is simulated, it cannot capture all measurement noise, assay artefacts, inter-laboratory variability, species differences, or mechanistic edge cases seen in real drug discovery.
- Some variables are generated with intentional correlation structure, which may make machine learning tasks easier than they would be with real-world noisy data.
- Safety variables are simplified.
- No longitudinal or repeated-measures design is included.
- No true uncertainty intervals are attached to individual compound values.

## Relationships to other files
This datasheet describes the dataset used in:
- `principal_scientist_dmpk_oncology_proof_of_concept.ipynb`

## Recommended interpretation
Users should interpret the dataset as a synthetic systems-level teaching and demonstration resource. It is useful for showing how assay outputs can be integrated into a translational DMPK narrative, but it should not be mistaken for validated preclinical evidence.

## Version
Version 1.0, created for the proof-of-concept translational oncology DMPK notebook.

