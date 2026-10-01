# Real-Time Spoken Digit Recognition via Hidden Markov Models

An end-to-end discrete Hidden Markov Model (HMM) speech recognition pipeline implemented from scratch in C++. The system processes acoustic voice input, extracts cepstral features using Linear Predictive Coding (LPC), quantizes continuous features against a 32-state vector codebook, and classifies spoken digits (0–9) in real time.

## Repository Structure
*   **`src/`**: Contains the core C++ engine (`HMM_DIGIT.cpp`) for HMM training, testing, and live inference.
*   **`data/`**: Contains the 32-state vector quantization codebook and initial probability matrices.

## Key Features
- **Acoustic Pre-Processing:** Dynamically trims silence based on ambient energy thresholds and computes DC-shift offsets.
- **LPC Feature Extraction:** Derives 12 Cepstral Coefficients per frame using Durbin's algorithm with a Raised Sine Window.
- **Vector Quantization:** Maps continuous acoustic vectors into discrete observation symbols against a 32-state LBG codebook.
- **HMM Training (Baum-Welch):** Implements Forward-Backward, $\xi$, and $\gamma$ re-estimation formulas to iteratively converge transition, emission, and initial state matrices.
- **Inference (Viterbi):** Evaluates maximum-likelihood state sequences to recognize live microphone capture and offline test recordings.
