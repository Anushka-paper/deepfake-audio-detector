# deepfake-audio-detector

# Deepfake Audio Detector

Detect AI-generated (TTS / voice-conversion) speech, and integrate it into my
Audio Forensics Platform for evidence analysis.

## Problem
Given one audio clip, output a score: bona fide (real) vs spoof (synthetic).

## Dataset: ASVspoof 2019 Logical Access (LA)
- Source: VCTK speakers; 16 kHz FLAC
- Train/dev: attacks A01–A06 (known); Eval: A07–A19 (mostly unseen)
- Labels from protocol files: speaker, file, attack ID, bonafide/spoof

## Metric
- Equal Error Rate (EER), lower is better; also report per-attack EER
- Reference points: LFCC-GMM baseline 8.09% EER, AASIST ~0.83% EER (LA eval)

## Plan
1. [ ] Explore data: waveforms, spectrograms, listen to real vs fake
2. [ ] Features: log-mel spectrogram, LFCC, MFCC
3. [ ] Baseline 1: MFCC/LFCC + GMM or logistic regression
4. [ ] Baseline 2: small CNN on log-mel
5. [ ] Evaluate: overall + per-attack EER on eval set
6. [ ] Compare with pretrained AASIST
7. [ ] Robustness: noise + MP3 compression; In-the-Wild dataset
8. [ ] Integrate: FastAPI /detect endpoint in Audio Forensics Platform

## Results
| Model | Dev EER | Eval EER |
|-------|---------|----------|
| (fill in) | | |

## References
- Todisco et al., "ASVspoof 2019: Future Horizons in Spoofed and Fake Audio Detection", Interspeech 2019
- ASVspoof 2019 evaluation plan
