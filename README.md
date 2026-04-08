# RIIV

Public research subset of **RIIV**: a benchmark for **human personality analysis in multimodal dialogues**.

## Overview

RIIV is a multimodal dialogue personality analysis dataset built from real IELTS-style mock interview videos. The full benchmark contains **218** interview videos and **2,322** turn-level dialogue units with aligned **textual, acoustic, visual, and emotion-related** information, together with continuous **Big Five** personality annotations. 
## Repository structure 

```text
RIIV/
├── README.md
├── LICENSE
├── appendix.md
└── subset/
    ├── annotations/
    │   └── ielts_part1_emotion.json
    ├── features/
    │   └── ielts_emotion.pkl
    └── videos/
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

The released feature subset is provided as: subset/features/ielts_emotion_subset.pkl

## Large files

Due to the large size of the dataset, the complete data files are not stored directly in this repository. Please download them via the external link.：https://pan.baidu.com/s/1UzmEsbQDJMCMw6xUbcptoQ?pwd=uhq8 提取码: uhq8




