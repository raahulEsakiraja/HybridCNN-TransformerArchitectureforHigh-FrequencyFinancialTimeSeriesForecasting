# HybridCNN-TransformerArchitectureforHigh-FrequencyFinancialTimeSeriesForecasting
Hybrid CNN-Transformer Architecture for High-Frequency Financial Time Series Forecasting

Authors

Raahul Esakiraja Primary Author (Virginia Tech, raahule@vt.edu)

Fernando (Virginia Tech)

Trent (Virginia Tech)

Prathik (Virginia Tech)

Research Group: DLQF (Dataism Lab for Quantitative Finance)

📖 Overview

This repository accompanies our working paper:

"Hybrid CNN-Transformer Architecture for High-Frequency Financial Time Series Forecasting" (2025)

We introduce a hybrid deep learning architecture that integrates:

CNNs for short-term, localized feature extraction

Transformers (with vector-based relative positional encoding, vRPE) for capturing long-range dependencies

Our model aims to forecast whether the price of a stock will rise, fall, or remain flat in high-frequency trading (HFT) settings, while remaining efficient enough for real-time use.

🧠 Model Architecture

CNN Block: multi-layer 1D convolutions with batch normalization + ReLU

Transformer Encoder: multi-head self-attention with vRPE

Classification Head: softmax over {Upswing, Neutral, Downswing}

This hybrid structure captures both short-term volatility and long-term trends.

📊 Dataset & Preprocessing

Universe: 10 S&P 500 stocks across sectors (Tech, Energy, Healthcare, etc.)

Windowing: 60-minute sliding windows

Features: OHLC, RSI, MACD, VWAP, volume + sine/cosine encodings

Normalization: z-score per stock and feature

Augmentation: TA-Lib indicators

⚙️ Training Setup

Optimizer: Adam (lr = 0.001)

Loss: Cross-entropy

Regularization: Dropout + BatchNorm

Metrics: Directional Accuracy, F1 (macro/weighted), Inference Latency

📈 Results

Overall Test Accuracy: 58.2%

Stronger performance on neutral/downswings

Weak on upswings due to class imbalance

Attention maps show the model effectively learns long-term dependencies

📌 Key Contributions

Novel hybrid CNN-Transformer for HFT prediction

Use of vector-based relative positional encoding (vRPE)

Sector-diverse evaluation on 10 S&P 500 stocks

Insights on class imbalance + attention interpretability

🚀 Future Work

Address class imbalance (upswing detection)

Adaptive positional encodings

Cross-asset modeling

Deployment into live IB/trading systems

📄 Citation

If you use this repository, please cite our work:

@article{esakiraja2025hybrid,
  title={Hybrid CNN-Transformer Architecture for High-Frequency Financial Time Series Forecasting},
  author={Esakiraja, Raahul and Fernando, Trent, Prathik},
  journal={Working Paper, DLQF Research Group},
  year={2025}
}

⚖️ License & Legal Notice

License: CC BY-NC-SA 4.0 (Attribution, Non-Commercial, Share-Alike)

Code and documentation provided for academic research only

Not for financial advice or production trading use

🙏 Acknowledgments

Special thanks to Dr. Ali Habibnia and the Dataism Laboratory for Quantitative Finance for their mentorship and support.
