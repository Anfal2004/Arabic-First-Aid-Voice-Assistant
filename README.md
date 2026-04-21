# Arabic-First-Aid-Voice-Assistant
نموذج ذكاء اصطناعي لتقديم إرشادات الإسعافات الأولية بالصوت وباللغة العربية## 📝 Overview
In high-stress medical emergencies, every second counts. This project introduces a specialized **Speech-to-Speech AI system** designed to provide immediate, medically verified first aid instructions in **Arabic**. By integrating **Automatic Speech Recognition (ASR)**, **Natural Language Processing (NLP)**, and **Text-to-Speech (TTS)**, our system offers a hands-free solution to guide users through life-saving procedures.

## ⚙️ Methodology & Proposed Solution
The framework consists of three main components ensuring high accuracy and low latency:

1. **Automatic Speech Recognition (ASR):** Powered by **OpenAI Whisper**, converting spoken Arabic emergency phrases into text, even in noisy environments.
2. **Natural Language Processing (NLP):**
   - **Model:** We utilized **AraBERT**, a transformer-based model specifically designed for the Arabic language.
   - **Feature Enhancement:** Incorporated **TF-IDF word-importance scoring** to highlight influential terms (e.g., "إنجرح", "حرق") before classification.
   - **Task:** Scenario classification into predefined labels (e.g., Burns, Injuries, Choking).
3. **Text-to-Speech (TTS):** Uses **gTTS / ElevenLabs** to translate textual instructions into natural, expressive Arabic voice output.



## 📊 Evaluation & Results
### Model Training
The **AraBERT** model was fine-tuned over 7 epochs. 
- **Learning Curve:** Training loss dropped from 2.14 to **0.26**.
- **Accuracy:** The F1-score rose sharply from 0.15 to **0.85**, demonstrating a strong ability to classify emergency categories correctly.

![Model Performance](images/figure1_results.png)
*Figure 1: Training and Validation loss/F1-score over epochs.*

### System Prototype Demonstration
In real-world testing, the system successfully transcribed complex sentences, identified key medical terms using TF-IDF, and predicted labels with high confidence (e.g., **0.973 confidence** for "Minor Wound").

![System Output](images/figure2_demo.png)
*Figure 2: End-to-end demonstration showing ASR transcription, AraBERT classification, and TTS output.*

## 🛠️ Tech Stack
- **Deep Learning:** `PyTorch`, `Hugging Face Transformers` (AraBERT).
- **Audio Processing:** `OpenAI Whisper`, `gTTS`, `FFmpeg`.
- **Data Analysis:** `Pandas`, `NumPy`, `Scikit-learn` (TF-IDF, Stratified Sampling).
- **Visualization:** `Matplotlib` (Confusion Matrix & Loss Curves).
