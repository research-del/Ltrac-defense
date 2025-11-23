
LTRAC 
This repository contains the full implementation of LT-RAC, a learned website fingerprinting defense based on: - Supervised Contrastive Autoencoder (SupCon-AE)
- Hybrid Adaptive Clustering (HDBSCAN + Agglomerative)
- Zero-bandwidth-overhead trace reconstruction
- Closed-world and open-world WF attack evaluation (DF, Var-CNN, TikTok, RF)
 
________________________________________
 Project Structure
wf-defense/
├── src/
│   ├── training/
│   │   ├── train_supcon_hybrid.py
│   │   ├── train_attackers.py
│   │   └── _autoencoder_train.py
│   ├── evaluation/
│   │   ├── supcon_ae_cw_eval.py
│   │   ├── attack_evaluate.py
│   │   └── openworld_precision_recall.py
│   ├── analysis/
│   │   └── overhead_analysis.py
│   └── utils/      (optional utilities)
│       ├── data_loader.py
│       ├── preprocess.py
│       └── visualization.py
├── README.md
├── requirements.txt
└── .gitignore
________________________________________

 		Features

1. Supervised Contrastive Autoencoder (SupCon-AE)
	Learns privacy-preserving traffic representations

	Optimized for class separation + reconstruction

2. Hybrid Adaptive Clustering
	HDBSCAN removes noisy open-world traces

	Agglomerative refines structure of closed-world sets

	Enables adaptive anonymity sets like Palette, but learned from data

3. Website Fingerprinting Attack Evaluation
Supports four SOTA attackers: - Deep Fingerprinting (DF) - Var-CNN - TikTok CNN - Random Forest (RF)
Includes closed-world accuracy and open-world precision–recall.

4. Zero Overhead Trace Reconstruction
	Reconstructed traces maintain original burst count

	No bandwidth overhead

	Zero time overhead
________________________________________
🔧 Setup & Installation
Install dependencies:
pip install -r requirements.txt
(Optional) Install GPU-enabled PyTorch from https://pytorch.org.
________________________________________
 How to Run Training
Train SupCon-AE + Hybrid Clustering
python src/training/train_supcon_hybrid.py
Train Attack Models (DF, Var-CNN, etc.)
python src/training/train_attackers.py
________________________________________
🧪 Run Evaluation
Closed-world Evaluation
python src/evaluation/supcon_ae_cw_eval.py
Open-world Precision–Recall
python src/evaluation/openworld_precision_recall.py
________________________________________
📊 Overhead Analysis
python src/analysis/overhead_analysis.py
Generates latency & bandwidth overhead analysis.
________________________________________
 
________________________________________
 Contact
 
This research was conducted at the School of Computer Science and Technology, Jiangsu University.

**For research collaboration and academic inquiries:**
- Please contact our research group through official university channels

**For code-related questions and technical issues:**
- Please contact (5103240323@stmail.ujs.edu.cn)
- Check the documentation and existing issues first
________________________________________


 System Requirements

- **CPU:** Intel i5/i7 or AMD Ryzen 5/7 (4+ cores)
- **RAM:** 16 GB minimum (32 GB recommended)
- **GPU:** NVIDIA with CUDA support (optional, recommended for training)
- **Storage:** 50+ GB free space (SSD recommended)
- **OS:** Windows 10/11, Linux (Ubuntu 20.04+), macOS
- **Python:** 3.8+
 
