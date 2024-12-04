
# Deepfake Realistic Generation Techniques 

![Deepfake Techniques](https://via.placeholder.com/800x200?text=Deepfake+Generation+Project)

This repository presents a comprehensive study and implementation of advanced **deepfake generation techniques**, combining **audio deepfake tools** (**XTTS** and **RVC**) with **video deepfake tools** (**GeneFace**, **Wave2Lip**, and **DINet**). The objective is to create highly realistic deepfake videos that are difficult to detect, showcase generated outputs, and evaluate their performance using both **quantitative metrics** and **subjective evaluations**.

---

## Table of Contents

1. [Overview](#overview)
2. [Audio Deepfake Generation Techniques](#audio-deepfake-generation-techniques)
   - [XTTS](#xtts)
   - [RVC](#rvc)
   - [XTTS + RVC](#xtts--rvc)
3. [Video Deepfake Generation Techniques](#video-deepfake-generation-techniques)
   - [GeneFace](#geneface)
   - [Wave2Lip](#wave2lip)
   - [DINet](#dinet)
4. [Results](#results)
   - [Audio Results](#audio-results)
   - [Video Results](#video-results)
   - [Evaluation Scores](#evaluation-scores)
5. [Evaluation](#evaluation)
   - [Objective Evaluation](#objective-evaluation)
   - [Subjective Evaluation](#subjective-evaluation)
6. [Conclusion](#conclusion)

---

## Overview

Deepfake technology leverages **Generative AI** to create synthetic media that mimics real-world visuals and sounds. This project implements a pipeline combining **audio deepfake generation** with **video synthesis** to produce highly realistic videos. The techniques utilized include state-of-the-art tools for **audio synthesis** and **lip-syncing**, enabling seamless alignment of generated audio with facial movements.

### Key Objectives:
- Explore and compare multiple **deepfake generation tools**.
- Combine audio and video tools to generate seamless deepfake videos.
- Evaluate the performance of these techniques using:
  - **Objective metrics** (quantitative evaluations such as fidelity scores).
  - **Subjective metrics** (user feedback and detector robustness).

---

## Audio Deepfake Generation Techniques

### XTTS
**XTTS** (Extended Text-to-Speech) is an end-to-end TTS system that utilizes a VQ-VAE model [81] to discretize audio into tokens, which are then predicted by a GPT model based on the input text and speaker latent vectors. The output of the GPT model is passed to a decoding model to generate the audio signal. For audio generation, we used **XTTS-webui** [82].

[XTTS Repository Link](https://github.com/xtts-repository)

### RVC
**RVC** (Retrieval-based Voice Conversion) is a powerful open-source voice-to-voice conversion tool. Unlike traditional programs that rely on training, RVC operates by replacing input source characteristics with those from a training dataset using a top-1 retrieval approach.

[RVC Repository Link](https://github.com/rvc-repository)

### XTTS + RVC
The combination of **XTTS** and **RVC** enhances the realism and personalization of generated audio, aligning perfectly with the video synthesis.

---

## Video Deepfake Generation Techniques

### GeneFace
**GeneFace** is a talking face generation system based on Neural Radiance Fields (NeRF). Compared to GAN-based techniques, NeRF generators preserve more details and provide better 3D realism, modeling a continuous 3D scene in the latent space.

[GeneFace Repository Link](https://github.com/geneface-repository)

### Wave2Lip
**Wave2Lip** is a lip-sync generation method that uses a 2D-based GAN approach. Although this method may yield lower-quality results compared to others, it enables the model to generalize effectively across different individuals.

[Wave2Lip Repository Link](https://github.com/wave2lip-repository)

### DINet
**DINet** is a lip-sync generation method that also uses GANs to enhance the realism of deepfake videos by improving lip synchronization and facial dynamics.

[DINet Repository Link](https://github.com/dinet-repository)

---

## Results

### Audio Results
Audio samples generated using **XTTS** and **RVC** for one subject are provided in the repository. These showcase the tools' ability to generate realistic and natural-sounding audio. Below are links to the generated audio outputs:

| Sample ID | Description                   | Audio File                                   |
|-----------|-------------------------------|---------------------------------------------|
| 1         | Original Audio                | [Original Audio](results/audio/sample_1.mp3)  |
| 2         | XTTS-Generated Audio          | [XTTS](results/audio/xtts_sample_1.mp3)  |
| 3         | RVC-Transformed Audio         | [RVC](results/audio/rvc_sample_1.mp3)   |
| 4         | XTTS + RVC Combined Audio     | [XTTS+RVC](results/audio/xtts_rvc_sample.mp3)|

### Video Results
The repository contains video samples created using **GeneFace**, **Wave2Lip**, and **DINet**. Below are links to videos for one subject:

| Sample ID | Description                   | Video File                                   |
|-----------|-------------------------------|---------------------------------------------|
| 1         | Original Video                | [Original Video](results/video/sample.mp4)|
| 2         | Wave2Lip-Synced Video         | [Wave2Lip-Video](results/video/wave2lip_sample.mp4)|
| 3         | DINet-Enhanced Video          | [DINet-Video](results/video/dinet_sample.mp4)   |
| 4         | GeneFace-Generated Video      | [GeneFace-Generated Video](results/video/geneface_sample.mp4)|

To see more videos, click this link: [Video Results](#)

### Evaluation Scores

Quantitative and subjective evaluation results are presented below:

#### Quantitative Evaluation

In this evaluation, we use three metrics (PSNR, SSIM, and VMAF) to assess the performance of the three tools on five videos. To conduct this analysis, we utilize **FFmetric**, an open-source software designed to compute these metrics.

![Quantitative Evaluation Image](image1.png)

#### Subjective Evaluation

To complement the objective quality assessment, we conducted a subjective evaluation involving real users to assess the perceived quality of deepfake content. The evaluation consisted of the following steps:

**Video Preparation**: We used the same videos from the objective evaluation, keeping the individuals, audio recordings, and duration consistent.

**Recruitment of Evaluators**: Ten evaluators, familiar with the individuals in the videos, were selected to ensure relevant feedback.

**Evaluation Criteria**:
- Audio: Evaluators rated audio based on clarity, intelligibility, and emotional expression, scoring from 1 (poor) to 5 (excellent).
- Video: Evaluators rated video realism, quality, and lip-sync accuracy using the same 1-5 scale.

**Process**: Evaluators first rated audio clips. The top-rated audios were then used to generate lip-synced deepfake videos, which were subsequently rated based on video criteria. The final scores were averaged and used for comparison.

This subjective evaluation provided additional insights into the quality and realism of the deepfake content generated, alongside the objective metrics.

![Subjective Evaluation Image](image2.png)

To evaluate further, we performed a detector test using two open-source detectors to evaluate LipFD and SBI+RECCE.

![Detector Test Image](image3.png)

---

## Conclusion

This project highlights the potential of combining state-of-the-art **audio** and **video deepfake techniques** to create synthetic media with unparalleled realism. By leveraging complementary tools like **XTTS**, **RVC**, **GeneFace**, **Wave2Lip**, and **DINet**, the generated content achieves:
- High scores in both objective and subjective evaluations.
- A significant step forward in seamless deepfake synthesis.


