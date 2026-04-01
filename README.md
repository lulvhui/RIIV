# RIIV

Public research subset of **RIIV**: a benchmark for **human personality analysis in multimodal dialogues**.

## Overview

RIIV is a multimodal dialogue personality analysis dataset built from real IELTS-style mock interview videos. The full benchmark contains **218** interview videos and **2,322** turn-level dialogue units with aligned **textual, acoustic, visual, and emotion-related** information, together with continuous **Big Five** personality annotations. This repository releases an **anonymized public subset** for academic research use only. 

The original benchmark and methodology are introduced in our paper:

> **A Benchmark for Human Personality Analysis in Multimodal Dialogues**  
> Lvhui Lu, Dan Wu, Dong Zhang, Yue Zhang, Yu Hong, Shoushan Li

## What is included in this repository

This public subset contains:

- **Blurred Part 1 interview videos** from the selected subset
- **Turn-level annotations** in JSON format
- **Authoritative personality labels** derived from the released subset
- **Multimodal feature subset** extracted from the full feature package
- **Metadata files** describing the selected public subset
- **Ethics statement** and supplementary notes

## Repository structure 

```text
RIIV/
├── README.md
├── LICENSE
├── ethics_statement.md
└── subset/
    ├── annotations/
    │   └── ielts_part1_emotion_subset.json
    ├── features/
    │   └── pinet_emotion_subset.pkl
    ├── metadata/
    └── videos_blurred/
```

## Annotation format

Each subject is indexed by a person ID. For each subject, the released turn-level JSON contains:

label: subject-level Big Five scores
turns: turn-level dialogue units
Q: interviewer question
A: candidate response
time_q: question timestamp
time_a: answer timestamp
emotion_response: emotion reasoning text aligned with the response
Feature file

The released feature subset is provided as:

subset/features/pinet_emotion_subset.pkl

This file is filtered from the full feature package and only contains the selected public subset. It follows the split structure used in our experiments (e.g., train, valid, test) and keeps the multimodal features associated with the released subset.

## Large files

Large files of the RIIV public subset are distributed via the GitHub Releases page rather than the main repository.

If a file is split into multiple parts, please download all parts and merge them locally before use.

## Ethics

This dataset is released for academic research only.

Users must not:

attempt to identify any individual in the released data,
redistribute the data for commercial purposes,
use the dataset in high-stakes decision-making scenarios such as hiring, screening, diagnosis, or other sensitive applications.



