# Code-Switching Speech Recognition (ASR)
This repository contains a project which aims to solve the challenge of Tanglish (Tamil-English code-switched) Automatic Speech Recognition (ASR) by providing a complete English transcription from an uploaded or recorded audio file (WAV or MP3). The core Technical Stack leverages the Whisper Medium model from the Hugging Face Transformers library, running within a Google Colab environment using PyTorch. The Whisper model is critical as it serves a dual role: its multilingual capabilities allow it to perform speech recognition on the code-switched audio and simultaneously translate the content directly into Standard English, a highly effective approach for this specific ASR and translation task. The UI/UX interface is quickly deployed using Gradio, which provides a user-friendly, interactive web application within the Colab notebook. This interface handles the audio input (microphone or file upload) and displays the resulting English transcription, making the complex machine learning pipeline accessible and easy to test.

## Project Highlights
1) Multilingual Support: Trained to recognize transitions between languages (e.g., Hindi-English or Tamil-English) seamlessly.
2) High Accuracy: Achieved a Word Accuracy (Wacc) of 83.33% with real-time microphone input.
3) Real-time Inference: Integrated with microphone support for live speech-to-text processing.
4) Modern Architecture: Built using state-of-the-art transformer-based speech models from Hugging Face.

## Technologies & Libraries
> Deep Learning: PyTorch / Hugging Face Transformers
> Audio Processing: Librosa, SoundFile, PyAudio
> Evaluation: Word Error Rate (WER) and Word Accuracy (Wacc)
> Environment: Google Colab / Jupyter Notebook

## System Pipeline
### Audio Pre-processing:
> Resampling audio input to 16kHz (standard for ASR models).
> Normalization and noise reduction to improve signal-to-noise ratio (SNR).

### Feature Extraction:
> Converting raw waveforms into log-Mel spectrograms or using wav2vec-style feature encoders.

### Inference:
> The model processes the encoded audio to predict tokens across multiple language vocabularies simultaneously.

### Decoding:
> Beam Search decoding is used to determine the most likely transcription in a code-switched context.


## Performance Evaluation
The model was evaluated on custom code-switched datasets and real-world microphone tests:
| Metric | Result |
| :--- | :--- |
| **Word Accuracy (Wacc)** | **83.33%** |
| **Model Size** | ~769M Parameters (Medium) |
| **Input Channels** | Microphone & File Upload |


##  Setup & Usage
1. Open the `Final_ASR_Projectipynb.ipynb` in Google Colab.
2. Install dependencies: `pip install transformers gradio torch librosa`.
3. Run the notebook cells to launch the Gradio web interface.
4. Record or upload your Tanglish audio to receive the English transcription.

## Future Scope
1) Dialect Adaptation: Fine-tuning on specific regional dialects to improve accuracy in informal code-switching.
2) Speaker Diarization: Integrating "who spoke when" functionality for multi-speaker multilingual meetings.
3) Language Identification (LID): Adding a dedicated LID head to better distinguish between languages at the frame level.

## Author
Varshaa T
