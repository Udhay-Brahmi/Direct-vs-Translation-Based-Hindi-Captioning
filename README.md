# Direct-vs-Translation-Based-Hindi-Captioning

**CS 772 Final Project** | *Lavinia Nongbri, Prateek Jain, Udhay Brahmi, Hasmita Kurre*

## 📋 Overview

Comparison of two approaches for generating Hindi image captions using BLEU score evaluation.

- **Method 1:** Direct Hindi captioning with Inception v3 + LSTM
- **Method 2:** English captioning → Google Translate to Hindi

## 📊 Dataset

- **Hindi-Vision-Genome:** 29,000 images with Hindi/English captions
- **Evaluation scales:** 1k, 5k, 10k, 15k, 20k images

## 🏗️ Architecture

- **Encoder:** Pre-trained Inception v3 for feature extraction
- **Decoder:** LSTM for caption generation
- **Training:** 12 epochs, batch size 64, learning rate 0.001

## 📈 Results

### BLEU Scores Performance

| Method | BLEU-1 | BLEU-2 | BLEU-3 | BLEU-4 |
|--------|--------|--------|--------|--------|
| **Direct Hindi** | 0.35-0.40 | 0.15-0.20 | 0.08-0.12 | 0.04-0.08 |
| **English→Hindi** | 0.30-0.35 | 0.12-0.18 | 0.06-0.10 | 0.03-0.06 |

## 🔍 Key Findings

- ✅ **BLEU-1 scores highest:** Good single-word vocabulary capture
- ❌ **Sharp decline in higher n-grams:** Difficulty generating coherent phrases
- 🎯 **Direct method slightly outperforms translation:** Better linguistic structure
- 📊 **Dataset size impact minimal:** No linear improvement with more data

## 💬 Qualitative Analysis Examples

```hindi
Generated: "एक छोटा कुत्ता एक बड़ी छड़ी के साथ खेलता है।"
Adequacy: Bad (object misidentification)
Fluency: Excellent (grammatically correct)
```

## 🎯 Conclusions

1. **Single-word accuracy** is reasonable but **phrase coherence** remains challenging
2. **Direct Hindi captioning** performs marginally better than translation-based approach
3. **Model struggles** with complex scene understanding and object identification
4. **Increasing dataset size** alone doesn't solve linguistic complexity issues

## 🛠️ Technical Stack

- `PyTorch` | `Inception v3` | `LSTM`
- `Hindi-Vision-Genome dataset`
- `BLEU evaluation metrics`
