# [**QiVC-Net: Quantum-Inspired Variational Convolutional Network, with Application to Biosignal Classification**](https://arxiv.org/abs/2506.xxxxx)  

**Preprint:** [arXiv:2506.xxxxx](https://arxiv.org/abs/2506.xxxxx)  

---

**Amin Golnari**, **Jamileh Yousefi**, **Reza Moheimani**, **Saeid Sanei**. **"QiVC-Net: Quantum-Inspired Variational Convolutional Network, with Application to Biosignal Classification"**  
Preprint: [https://arxiv.org/abs/2506.xxxxx](https://arxiv.org/abs/2506.xxxxx)

**Amin Golnari**<sup>a</sup>, **Jamileh Yousefi**<sup>b</sup>, **Reza Moheimani**<sup>a</sup>, **Saeid Sanei**<sup>c,d</sup>  
<sup>a</sup> Faculty of Computer Science, Chemnitz University of Technology, Chemnitz, Germany  
<sup>b</sup> Shannon School of Business, Cape Breton University, Sydney, NS, Canada  
<sup>c</sup> Department of Electrical and Electronic Engineering, Imperial College London, London, UK  
<sup>d</sup> College of Engineering and Computer Science, VinUniversity, Hanoi, Vietnam  

**Link to the preprint version:** [Click here](https://arxiv.org/abs/2506.xxxxx)

**Run this implementation on Google Colab (coming soon):**  
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/amingolnari/Demo-QiVC-Net/blob/main/QiVC_Net_Demo.ipynb)

**Compatibility:**
- TensorFlow: 2.17.0  
- Keras: 3.4.1  
- Python: ≥ 3.9

---

## **Framework Overview**

**QiVC-Net** introduces the **Quantum-inspired Variational Convolution (QiVC)** framework, a novel learning paradigm that integrates probabilistic inference, variational optimization, and quantum-inspired transformations into convolutional neural networks.

The core innovation is the **Quantum-inspired Rotated Ensemble (QiRE)** mechanism, which applies differentiable, low-dimensional subspace rotations to convolutional weights, inspired by unitary evolution in quantum systems. This enables **structured, geometry-preserving uncertainty modeling** without adding learnable parameters. The framework is instantiated for **phonocardiogram (PCG) signal classification**, a challenging task marked by noise, inter-subject variability, and class imbalance.

QiVC-Net also features a **Reversal Fusion Residual (RFR)** block that captures bidirectional temporal dynamics by processing both forward and time-reversed inputs, enhancing robustness and temporal coherence.

---

## **Key Features:**

1. **QiVConv Layer**:  
   - A probabilistic convolutional layer that performs norm-preserving subspace rotations of kernel weights.
   - Enables expressive uncertainty-aware representations while maintaining parameter efficiency.

2. **Quantum-Inspired Rotated Ensemble (QiRE)**:  
   - Injects structured stochasticity via unitary-inspired rotations in a learnable low-dimensional subspace (*k = 5*).
   - Preserves weight-space geometry and avoids the instability of isotropic Gaussian noise.

3. **Uncertainty-Aware Dual-Path Architecture (RFR Block)**:  
   - Processes input signals in both forward and reversed temporal directions.
   - Fuses features via LSTM layers and residual refinement for robust temporal modeling.

4. **Robust PCG Classification**:  
   - Evaluated on **PhysioNet/CinC 2016** and **CirCor DigiScope 2022** datasets.
   - Achieves **97.84%** and **97.89%** average accuracy, respectively, with strong calibration (low ECE) and noise robustness.

5. **Clinically Aligned Design**:  
   - Lightweight, interpretable, and efficient, suitable for deployment in safety-critical applications.
   - Uses a **composite loss (CCE + Dice)** with dynamic weighting to handle class imbalance.

---

## **Usage of QiVConv in Practice**

The **QiVConv layer** can be used as a drop-in replacement for standard 1D convolutional layers in any TensorFlow/Keras model. It introduces no additional parameters, only learnable mean and standard deviation per weight (via the reparameterization trick), and supports end-to-end training with standard optimizers. It is particularly well-suited for **time-series and biosignal tasks** where uncertainty quantification, robustness to noise, and temporal symmetry are critical.

---

If our work is helpful to you, please kindly cite our paper as:

```bibtex
@article{golnari2025qivc,
  title={QiVC-Net: Quantum-Inspired Variational Convolutional Network, with Application to Biosignal Classification},
  author={Golnari, Amin and Yousefi, Jamileh and Moheimani, Reza and Sanei, Saeid},
  journal={arXiv preprint arXiv:2506.xxxxx},
  year={2025}
}
```
