###### CURRENT VERSION

# Noise-Robust Speech Enhancement Using SEGAN

## 🎯 Objective

To develop a deep learning-based speech enhancement system that can effectively denoise real-world noisy speech using SEGAN (Speech Enhancement Generative Adversarial Network). The system improves speech clarity and performance of downstream tasks like ASR (Automatic Speech Recognition).

## 👥 Team Members

- Shyam Vyas (m23csa545)
- Om Prakash Solanki (m23csa521)

## 📂 Dataset

We use the _VoiceBank-DEMAND_ dataset:

- 28 speakers for training, 2 unseen speakers for testing
- 40 different noise conditions including traffic, street, cafe, etc.

## 🧠 Methodology

- _SEGAN Architecture_: GAN-based end-to-end model operating on raw waveforms
- _Generator_: Encoder-decoder with skip connections
- _Discriminator_: Learns to distinguish real (clean) vs fake (enhanced) audio
- _Loss_: Adversarial + L1 loss
- _Virtual Batch Normalization_ for stable training

## 📊 Results

--- Evaluation Metrics ---
| Noisy | Enhanced
PESQ | 2.818 | 1.050
STOI | 0.923 | 0.481
SSNR | -0.93 dB | -0.99 dB
SI-SDR | 6.73 dB | -10.06 dB

## 🛠️ How to Run

### 🔧 Setup

```bash
pip install -r requirements.txt


## TRAINING
run training cell


## TESTING
python test_single_audio.py --file_name /kaggle/input/valentini-dataset-16000hz/Valentini_16000Hz/clean_testset_wav/p232_003.wav --epoch_name generator-5.pkl
```
