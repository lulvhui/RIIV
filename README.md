# RIIV

Public research subset of **RIIV**: a benchmark for **human personality analysis in multimodal dialogues**.

## Overview

RIIV is a multimodal dialogue personality analysis dataset built from real IELTS-style mock interview videos. The full benchmark contains **218** interview videos and **2,322** turn-level dialogue units with aligned **textual, acoustic, visual, and emotion-related** information, together with continuous **Big Five** personality annotations. This repository releases an **anonymized public subset** for academic research use only. 

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

由于数据集体积较大，本仓库不直接存放完整数据文件，请通过外部链接下载：https://pan.baidu.com/s/1UzmEsbQDJMCMw6xUbcptoQ?pwd=uhq8 提取码: uhq8




