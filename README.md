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


## Data Access & Large Files
Due to the large size of the full dataset and privacy considerations, we provide a sample subset via the link below.

1. Sample 
The external link contains a sample of the RIIV dataset. For privacy protection, the faces of the subjects in these sample videos have been blurred.

Link:  https://pan.baidu.com/s/1EFU_pA1j8CBNcxuGeeFQjQ?pwd=bi2s 

Password:  bi2s 

2. Feature file
   
The released feature subset is provided as: https://pan.baidu.com/s/1b0IXsUzn3K6KuZncXKGmJA?pwd=mh3s 

Password:mh3s

3. Full Dataset Request
If you need the complete RIIV dataset (including all 218 videos and unmasked visual data) for academic research purposes, please contact us via email:

Email: 20255227052@stu.suda.edu.cn



