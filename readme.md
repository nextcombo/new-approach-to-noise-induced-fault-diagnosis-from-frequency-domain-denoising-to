# New Approach to Noise-Induced Fault Diagnosis! From Frequency Domain Denoising to Fault Classification: FusADFaultClassifier - An Overview of the Adaptive Spectral Denoising and Classification Model

Introduction\tIn this issue, we update an innovative model for strong noise fault diagnosis tasks: FusADFaultClassifier.\tBased on the adaptive time-frequency fusion idea in FusAD, combined with the spectral features, impact characteristics, and noise interference characteristics of mechanical fault signals, a novel adaptive spectral denoising classification network is constructed for one-dimensional vibration signal classification tasks.\tCompared to common models such as VGG1d and DRSN, FusADFaultClassifier no longer solely relies on time-domain convolutional features but explicitly introduces FFT frequency domain modeling, adaptive spectral filtering, local convolutional branch enhancement, and interactive information fusion mechanisms within the model, thereby enhancing its fault recognition capability under different noise conditions.\tParticularly in medium noise environments, FusADFaultClassifier demonstrates good robustness and classification performance on both CWRU West Storage University bearing dataset and University of Ottawa bearing dataset, validating its application potential in industrial fault diagnosis scenarios under strong noise conditions. 
●Datasets: CWRU West Storage University bearing dataset, University of Ottawa bearing dataset●Environmental framework: Python 3.11, PyTorch 2.1 and above versions are all compatible●Accuracy: Test set achieves 99.9%●Usage: Beginners, paper requirements, graduation design requirements●Code guarantee: Code comments are detailed and ready to run without modification.\tNote: We also provide accompanying models explanation (for learning network structure) and instruction videos! For those who need a graduation project or a small paper, this is essential. The modules are rich, the innovation is high, and the performance is excellent!!
\t1.1 Signal Noise Background
\tDirectly input the original one-dimensional vibration signal into CNN;
Or input the signal to a two-dimensional visual model after converting it into a time-frequency plot.
Alternatively, feature extraction can be performed using structures such as ResNet, VGG, DRSN, etc.
Although these methods are effective, there are several issues: (1) Traditional CNNs focus more on local temporal waveforms and lack explicit frequency domain modeling capabilities. Bearing faults often manifest as specific frequencies, harmonics, sidebands, and impulse modulation structures, which may not be fully exploited by simple time-domain convolution. (2) Traditional convolutional networks do not have an adaptive noise reduction mechanism. Under low signal-to-noise ratio conditions, noise can significantly interfere with the local waveform structure, leading to models learning a large amount of irrelevant perturbations. (3) Although DRSN has soft threshold denoising capabilities, it mainly acts on deep feature responses. It does not directly filter fault-related components from the frequency domain perspective, thus there is still room for further improvement in fault signals with clear frequency structures. (4) Fault signals require simultaneous modeling of both global frequency structure and local impact characteristics. Single branch models often struggle to balance these two types of information. Based on these issues, we designed \u003CFusADFaultClassifier\u003E: a \u003CAdaptive Spectral Denoising Fusion Classification Model\u003E for fault diagnosis tasks.
1.2 Model Introduction
Among them, F represents the frequency domain features, and M is the adaptive spectral mask. This mechanism can automatically highlight the frequency components related to faults, suppress irrelevant noise interference, thereby enhancing the model's robustness under different noise conditions.
Innovation Point 2: Time-frequency joint feature enhancement. FusADFaultClassifier does not rely solely on the FFT branch but introduces a wavelet-like integral branch to extract local transient features. This can be understood as:
\tFFT branch: capturing fault frequency, multiplier frequency, and spectral energy changes;
\tIntegral Integration: Capturing local impacts, short-term abrupt changes, and transient responses.
Two types of features complement each other, enabling the model to simultaneously focus on both the global frequency domain structure and the local time domain impact patterns.
Innovation Point 3: Interactive Information Fusion Module. The model introduces an Information Fusion Module, which integrates fault features at different levels through gate-controlled interaction, feature modulation, and one-dimensional convolution. Compared to simple concatenations or additions, the IFM can further enhance the nonlinear correlation between effective features, thereby improving the ability to distinguish between different fault categories.
4. Innovation Point: End-to-End Noise Reduction Classification Integration
Signal preprocessing → feature extraction → classification
\tFusADFaultClassifier unifies frequency domain noise reduction, feature enhancement and fault classification into an end-to-end network:
\tInput vibration signal → Adaptive spectral noise reduction → Information fusion → Fault classification
This design reduces the reliance on manual feature engineering, enabling the model to automatically learn optimal noise-resistant feature representations based on classification objectives.
2 Experimental Design
2.1 Import Data
\tWe compared three models: VGG1d, DRSN, and FusADFaultClassifier under different noise conditions. \tFollowing the previous article, we preprocessed the fault classification for 10 categories. \tCase Western Reserve University bearing data \t10-category dataset:
\ttrain_set, val_set, test_set are all divided into training set, validation set and test set according to the ratio of 7:2:1, and finally save the data.
2.2 Datasets for Different Noise Conditions
3. Fault Diagnosis Model Based on FusADFaultClassifier
\t3.1 Define the network model,
3.2 Set parameters, train the model
\t50 epochs, accuracy 99.9%, FusADFaultClassifier network classification effect is significant, can extract important features from fault signal characteristics for model recognition, the effect is obvious!
3.2 Model Evaluation
(1) Accuracy, Precision, Recall, F1 Score
(2) Fault Classification Confusion Matrix
(3) Classification Label Visualization
(4) Original Data t-SNE Feature Visualization
(5) Post-Training t-SNE Feature Visualization:
3.3 Model Comparison
(1) Training Visualization Comparison
(2) Model Accuracy Comparison
CWRU West University Bearing Dataset:
Ottawa University Bearing Dataset:
Experimental results show that FusADFaultClassifier achieves good overall performance in various noise conditions of the CWRU and Ottawa University bearing datasets, especially showing its advantages in medium noise environments such as 5 dB and 10 dB. This indicates that the model has good frequency domain modeling capabilities and noise resistance classification abilities, suitable for bearing fault diagnosis tasks in complex industrial environments.
Note: Due to the large workload of model and data tuning, we only provide a set of examples for reference. Especially under high noise conditions, further tuning or trying other datasets may yield different results!
The core innovation of FusADFaultClassifier is: using adaptive frequency domain noise reduction to filter out fault-related frequencies, enhancing local impact expression with time-frequency complementary branches, and then improving fault feature discrimination ability through an interactive fusion module, thus achieving robust fault classification of one-dimensional vibration signal under strong noise environments.
Click Download: Full original data, Python code
2. Friends who like this can click to follow, give the article a "like", share on WeChat Moments or discuss groups.
Previously interesting content:
Rapid Paper | Based on 2D-SWinTransformer+1D-CNN-SENet Parallel Fault Diagnosis Model
Significant update on bearing life prediction! New ensemble of CNN-BiGRU-Attention models + enriched visualization charts.
Multimodal - Fault Diagnosis | Big Kernel Convolutions Open a New Era in Visualization!
Superior! Direct writing in Area One! Fault diagnosis model based on SSA+Informer-SENet.
Multi-source Information Fusion: Data layer fusion + feature layer fusion fault diagnosis models!

## Images

<!-- PAYMENT_BLOCK -->

## Get this dataset

- Payment link (Stripe): [Buy now](https://buy.stripe.com/3cs8yP7sY87d0vu9AB)
- Payment QR code: ![Payment QR code](pay.png)

<!-- /PAYMENT_BLOCK -->
