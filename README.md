Purpose
This project is focused on understanding and implementing the core pipeline of an ASR system. It’s an educational, research-oriented implementation that demonstrates how real-world ASR systems function under the hood.

a. Custom Speech-to-Text Model :

This project implements a speech-to-text (automatic speech recognition, ASR) system built from scratch using MFCC audio features, LSTM networks, and CTC loss without any pre-trained models or external APIs.

---

b. Features:

- Preprocessing pipeline with MFCC extraction using librosa
- Calculate MFCC lengths to decide padding size
- Character-level tokenizer for transcription
- Deep learning model using LSTM + CTC loss
- Custom decoding with beam search
- Achieves ~80% accuracy on clean audio samples


c. Tech Stack:

- Python
- TensorFlow / Keras
- Librosa
- NumPy
- Pandas
- Scikit-learn

---

d. Dataset:

The model uses 24 hrs audio data and custom-labeled audio clips stored in `metadata.csv` with the following structure:

sentence			
Printing, in the only sense with which we are at present concerned, differs from most if not from all the arts and crafts represented in the Exhibition
in being comparatively modern.	

audio_path
F:/Audio/wavs/LJ001-0001.wav
F:/Audio/wavs/LJ001-0002.wav

Note: Change the path according to your file.


e. Model Architecture:

Input (MFCCs) → Masking → LSTM → LSTM → TimeDistributed(Dense) → CTC Loss


f. How it Works:

1. Audio Preprocessing:

	Audio is loaded and converted to MFCCs (13 coefficients)

	MFCCs are normalized and padded/truncated to a fixed length

2. Text Preprocessing:

	Text is cleaned and tokenized character-wise

	Sequences are padded and used as ground truth

3. Model Training:

	Model learns alignment-free mapping using CTC loss

	Inputs: MFCCs, Transcripts, Sequence lengths

4. Decoding:

	Model predictions are decoded using beam search for better transcription accuracy


e. Results:

- Tested on a small dataset of 24 hrs audio files (~80% transcription accuracy)
- Works well on short, clean audio samples
- Can be improved with more data and noise-robust features

Note: This is a from-scratch implementation focused on understanding the core pipeline of ASR systems. It serves as a great educational or research-oriented project.
