# repairmet-explorer-oncology-apps
Explainable oncology decision-support software that integrates DNA repair, replication stress, and metabolic vulnerability into ranked mechanistic hypotheses and next-step assay recommendations.
<img width="1511" height="1053" alt="Screenshot 2026-04-16 at 14 39 16" src="https://github.com/user-attachments/assets/f031a69b-64f8-47d7-b0a6-1c8090d0f333" />
# RepairMet Explorer

RepairMet Explorer is an explainable scientific software platform for oncology decision support. It integrates DNA repair, replication stress, and metabolic vulnerability into a structured workflow that ranks mechanistic hypotheses and suggests practical next-step assays.

## Overview

Cancer samples often show multiple overlapping biological features at the same time, including homologous recombination deficiency, unstable replication forks, checkpoint dependence, glycolytic rewiring, oxidative stress, and mitochondrial plasticity. These signals are frequently examined in separate spreadsheets, pathway outputs, and notes, making it difficult to decide which liability is most worth testing first.

RepairMet Explorer addresses that problem by converting a compact, human-readable feature set into:

- composite biological state variables
- ranked vulnerability hypotheses
- top contributing features
- evidence-adjusted prioritization
- cohort summaries
- exportable sample and cohort reports

The platform is designed as an explainable reasoning layer, rather than a black-box prediction system.

## Core idea

The app assumes that tumours are adaptive, stress-laden, dependency-driven systems whose vulnerabilities emerge from the interaction of DNA repair, replication stress, and metabolic state.

The workflow:

1. accept interpretable tumour-state features
2. normalize values to a common scale
3. compress them into composite biological states
4. compare the sample against a curated vulnerability library
5. apply bounded evidence weighting
6. return ranked hypotheses and suggested next assays

## Feature set

The platform currently uses ten input features scored on a 0 to 100 scale:

- hrd
- fork
- repStress
- atr
- glycolysis
- oxphos
- glutamine
- ros
- redox
- lactate

These correspond to:

- homologous recombination deficiency
- fork instability
- replication stress
- ATR-CHK1 signaling
- glycolysis reliance
- oxidative phosphorylation competence
- glutamine dependence
- reactive oxygen species pressure
- redox buffering
- lactate handling

## Current hypothesis library

The current release includes six mechanistic hypotheses:

- POLQ / PARP synthetic lethality axis
- ATR / WEE1 / CHK1 checkpoint dependence
- LDHA / lactate export vulnerability
- GLS / glutamine anaplerosis dependence
- SLC7A11 / GPX4 redox defense
- OXPHOS overload and mitochondrial stress

## Main outputs

For each sample, the platform returns:

- normalized feature vector
- composite state scores
- ranked hypotheses
- base mechanistic score
- evidence multiplier
- final priority score
- top contributors
- recommended next-step assay ideas

## Frontend features

The web application currently supports:

- interactive single-sample scoring
- evidence weighting sliders
- output reactive graph
- state map bar chart
- feature geometry radar chart
- explanation of analysis
- ranked hypotheses display
- cohort CSV upload
- cohort table export
- current output export
- sample HTML report export

## Technology stack

Frontend:
- React
- Vite
- Recharts
- Framer Motion

Backend:
- FastAPI
- Pydantic
- Uvicorn

## Local project structure

```text
RepairMetExplorer/
  backend/
    main.py
    models.py
    scoring.py
    requirements.txt
  frontend/
    src/
      App.jsx
      api.js
      main.jsx
      styles.css
    package.json
```
## Intended use

RepairMet Explorer is intended for:
	•	translational hypothesis generation
	•	wet-lab planning
	•	interdisciplinary scientific discussion
	•	cohort triage
	•	report generation
	•	explainable systems-oncology prototyping

Not intended for clinical use

This software is not a diagnostic device and is not intended for direct clinical treatment selection. It is a mechanistically curated research decision-support prototype.

## Current limitations
	•	not trained on patient outcome labels
	•	not clinically calibrated
	•	depends on upstream biological interpretation of feature values
	•	uses a curated hypothesis library rather than autonomous discovery
	•	not tumour-type specific in the current release

## Future directions

Potential extensions include:
	•	tumour-type-specific priors
	•	uncertainty estimation
	•	expanded vulnerability ontology
	•	standardized assay-to-feature mapping
	•	data-driven parameter refinement
	•	cohort clustering and subgroup analysis
	•	richer export formats
	•	integration with multi-omics pipelines
  
## Citation
**Petalcorin, M.I.R. (2026). RepairMet Explorer: An explainable decision-support workflow linking DNA repair, 
replication stress, and metabolic vulnerability in oncology. https://github.com/mpetalcorin/repairmet-explorer-oncology-apps
