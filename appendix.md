# Ethics Statement
The dataset in this work is derived from real IELTS-style mock interview videos and is used strictly for academic research. Because the task involves multimodal dialogue understanding with emotion-related cues, it may introduce privacy concerns and subjective annotation bias. The predicted personality traits should therefore be regarded as apparent personality judgments rather than definitive assessments of a person’s true personality. We oppose any misuse of such technology in high-stakes applications that may harm individual privacy, autonomy, or fairness.

# Future Work
A potential limitation of our current setting is that personality is reduced to a set of scalar scores, whose values are largely distributed around the median range. While this formulation is convenient for supervised regression and already yields promising performance, it may not be the best way to model personality in real conversational scenarios. Personality perception is often descriptive, comparative, and context-dependent, rather than naturally expressed as a single fixed score. Therefore, in future work we aim to study personality reasoning with description-based and open-vocabulary outputs, which could avoid some of the constraints of the current annotation scheme and provide more interpretable predictions.



### Figure 1. Case study on Sample 36 for Conscientiousness
<img width="5596" height="3996" alt="Case study on Sample 36 for Conscientiousness" src="https://github.com/user-attachments/assets/5d972dc6-ce6c-47bf-a2f0-4ba2b8866010" />

### Figure 2. Case study on Sample 193 for Openness

<img width="5520" height="3776" alt="Case study on Sample 193 for Openness" src="https://github.com/user-attachments/assets/10cef449-7a25-40ca-b2a5-8cc2b06b193b" />



# Case Study: Validating Turn-Level Modeling and Emotion Injection

To demonstrate the effectiveness of our proposed framework, we present two case studies (Figure 1 and Figure 2) that highlight why personality traits in multimodal dialogues should be inferred from differentiated turn-level evidence rather than global, whole-video representations. In both samples, different dialogue turns exhibit conflicting trait signals. Standard video-level modeling tends to smooth over these local contradictory points when extracting global features, causing the model to compromise and lean towards the "dominant" behavioral tone of the video. In contrast, our model successfully preserves these diagnostically valuable conflict points and utilizes emotion injection to accurately parse local behavioral motivations.

### Figure 1. Case study on Sample 36 for Conscientiousness
In Sample 36, the subject possesses a high ground-truth Conscientiousness (C) score of 82.37. However, the whole-video baseline severely underestimates this trait (74.90). This underperformance occurs because global modeling mixes segments containing hesitant emotions with highly focused segments at the feature level, causing the strong conscientiousness signals to be "diluted" by other unremarkable dialogue turns.

By employing independent turn-level modeling, our framework successfully prevents this feature dilution. In Turn 5, the subject expresses uncertainty about their academic path, yielding a lower local C prediction score. However, the model isolates Turns 10 and 11, where the subject's detailed elaboration on long-term motivation and attention to detail (e.g., *"I really like to find errors"*) is fully preserved, thereby outputting exceptionally high local C scores.

Here, the integration of the emotion modality provides the model with the context to precisely decode psychological states. Emotion injection does not assign attention weights; rather, it clarifies local behavioral motivations. In Turn 5, explicitly identifying "uncertainty and hesitation" enables the model to reasonably justify the low-score performance (the local C prediction is further corrected from 61.40 down to 58.20). In Turn 11, recognizing a sense of "admiration and motivation" solidifies the reliability of this turn as evidence of high conscientiousness (the prediction increases from 84.20 to 88.70). By retaining these local extremes free from the interference of the global tone, the final aggregated score naturally approaches the true high conscientiousness level.

### Figure 2. Case study on Sample 193 for Openness
Sample 193 (target trait: Openness) further illustrates the pitfall of whole-video modeling ignoring key conflict points. The subject's ground-truth Openness (O) score is relatively high (79.35), yet the whole-video prediction suffers from a significant deviation (71.60).

An analysis of the isolated turns reveals the source of this deviation: Turns 6 and 9 establish a dominant "conservative" tone in the video (the subject expresses practical financial concerns and a distaste for live music). If a whole-video prediction is made, the global features are overwhelmed by this dominant emotion, thereby overlooking brief but highly critical exploratory signals.

Our turn-level architecture successfully captures the key "conflict point" in Turn 10. In this turn, the subject exhibits a strong desire for travel and forming new relationships. If not isolated from the preceding conservative turns, this high openness signal would be smoothed over. Through emotion injection, the emotion text explicitly captures "excitement and enthusiasm," allowing the model to confidently output a local O prediction as high as 90.20, unconstrained by the "doubt" or "discomfort" of previous turns. Our framework succeeds precisely because it tolerates and protects the personality tension exhibited by the subject across different turns, relying on highly confident local trait signals to pull the overall profile closer to the ground-truth label.


