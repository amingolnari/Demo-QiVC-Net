# [**QiVC-Net: Quantum-Inspired Variational Convolutional Network, with Application to Biosignal Classification**](https://arxiv.org/abs/2506.xxxxx)  

**Preprint:** [arXiv:2506.xxxxx](https://arxiv.org/abs/2506.xxxxx)  

---

**Amin Golnari**<sup>a</sup>, **Jamileh Yousefi**<sup>b</sup>, **Reza Moheimani**<sup>a</sup>, **Saeid Sanei**<sup>c,d</sup>  
<sup>a</sup> Faculty of Computer Science, Chemnitz University of Technology, Chemnitz, Germany  
<sup>b</sup> Shannon School of Business, Cape Breton University, Sydney, NS, Canada  
<sup>c</sup> Department of Electrical and Electronic Engineering, Imperial College London, London, UK  
<sup>d</sup> College of Engineering and Computer Science, VinUniversity, Hanoi, Vietnam  

**Link to arXiv preprint version:** [Click here](https://arxiv.org/abs/2506.xxxxx)

**Run this implementation on Google Colab (coming soon):**  
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/amingolnari/QiVC-Net/blob/main/QiVC_Net_Demo.ipynb)

**Compatibility:**
- TensorFlow: 2.17.0  
- Keras: 3.4.1  
- Python: ≥3.9

---

## **Framework Overview**

**QiVC-Net** introduces a novel **quantum-inspired variational convolution (QiVC)** framework that integrates principles from probabilistic inference, variational optimization, and quantum-inspired transformations into convolutional neural networks.  

At its core is the **Quantum-inspired Rotated Ensemble (QiRE)** mechanism—a structured, differentiable, low-dimensional subspace rotation of convolutional weights that mimics unitary evolution in quantum systems. This enables **geometry-preserving uncertainty modeling** without introducing additional learnable parameters, leading to more expressive, stable, and uncertainty-aware representations.

The architecture is instantiated for **phonocardiogram (PCG) signal classification**, a challenging domain marked by noise, inter-subject variability, and class imbalance. QiVC-Net further incorporates a **Reversal Fusion Residual (RFR) block** to model bidirectional temporal dynamics, enhancing robustness in real-world biomedical signal analysis.

---

## **Key Features**

1. **QiVConv Layer**  
   - A probabilistic convolutional layer that performs **norm-preserving subspace rotations** of kernel weights.
   - No extra parameters are added—uncertainty is modeled via structured reparameterization of existing weights.

2. **Quantum-Inspired Rotated Ensemble (QiRE)**  
   - Injects structured stochasticity through **differentiable unitary-inspired rotations** in a learnable low-dimensional subspace (default: *k=5*).
   - Preserves weight space geometry while enabling richer posterior distributions than isotropic noise.

3. **Uncertainty-Aware Dual-Path Architecture**  
   - Combines forward and time-reversed signal processing paths.
   - Features **LSTM-based fusion** and **residual refinement** to capture bidirectional temporal coherence in heart sounds.

4. **Robust PCG Classification**  
   - Evaluated on **PhysioNet/CinC 2016** and **CirCor DigiScope 2022** datasets.
   - Achieves **97.84%** and **97.89%** average accuracy, respectively, with strong calibration (low ECE) and noise robustness.

5. **Clinically Aligned Design**  
   - Lightweight, interpretable, and efficient—suitable for deployment in safety-critical medical applications.
   - Uses **composite loss (CCE + Dice)** with dynamic weighting to handle class imbalance.

---

## **Reproducibility & Open Science**

- Full implementation of the **QiVConv layer** is provided in this repository.
- Code supports **stratified 5-fold cross-validation**, **dynamic loss fusion**, and **SNR-based robustness testing**.
- Preprocessing pipeline follows established PCG best practices (25–400 Hz bandpass, 4s segmentation, amplitude normalization).

---

If you find this work useful, please cite our paper:

```bibtex
@article{golnari2025qivc,
  title={QiVC-Net: Quantum-Inspired Variational Convolutional Network, with Application to Biosignal Classification},
  author={Golnari, Amin and Yousefi, Jamileh and Moheimani, Reza and Sanei, Saeid},
  journal={arXiv preprint arXiv:2506.xxxxx},
  year={2025}
}
```

