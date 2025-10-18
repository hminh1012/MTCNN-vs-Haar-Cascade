# MTCNN vs Haar Cascade Face Detection

## Introduction

Face detection is a crucial component in computer vision and image processing applications. This project presents a comprehensive comparison between two prominent face detection methods: MTCNN (Multi-Task Cascaded Convolutional Networks) and Haar Cascade Classifier. By analyzing these two approaches, we aim to provide insights into their strengths, weaknesses, and optimal use cases.

## Project Overview

### What is MTCNN?
MTCNN (Multi-task Cascaded Convolutional Networks) is a deep learning-based face detection method that uses three stages of carefully designed convolutional networks to detect faces and facial landmarks. It is known for:
- High accuracy in face detection
- Ability to detect faces in various poses and orientations
- Facial landmark detection capabilities
- Robust performance under different lighting conditions

### What is Haar Cascade?
Haar Cascade is a machine learning-based approach that uses cascade classifiers trained with positive and negative images. Key characteristics include:
- Fast processing speed
- Lower computational requirements
- Good performance for frontal face detection
- Sensitivity to lighting and face orientation

## Project Objectives

- Compare the accuracy of MTCNN and Haar Cascade in face detection
- Analyze performance under different conditions:
  - Various lighting conditions
  - Different face angles
  - Multiple faces in one image
  - Different image resolutions
- Measure and compare processing speed
- Provide practical insights for choosing between these methods

## Implementation Details

### MTCNN Implementation
- Using deep learning architecture
- Three-stage detection pipeline:
  1. Proposal Network (P-Net)
  2. Refinement Network (R-Net)
  3. Output Network (O-Net)
- Face landmark detection capability

### Haar Cascade Implementation
- Using OpenCV's implementation
- Cascade classifier approach
- Rapid object detection framework
- Pre-trained model utilization

## Project Structure

```
├── data/
│   ├── test_images/
│   └── training_images/
├── notebooks/
│   ├── 1_data_preparation.ipynb
│   ├── 2_haar_cascade_implementation.ipynb
│   ├── 3_mtcnn_implementation.ipynb
│   └── 4_comparison_analysis.ipynb
├── results/
│   ├── haar_cascade_results/
│   └── mtcnn_results/
└── src/
    ├── haar_cascade/
    └── mtcnn/
```



### Prerequisites
```python
# Required packages
opencv-python
tensorflow
mtcnn
numpy
matplotlib
jupyter
```



## Comparison Results

### Performance Metrics
- Detection accuracy
- Processing time
- False positive rate
- False negative rate

### Visual Comparisons
- Side-by-side detection results
- Performance graphs
- Error analysis

## Conclusions

## 🔹 Model MCTNN

**Observations:**
- Both training and validation losses decrease rapidly and stabilize at low values.  
- Validation accuracy increases quickly and remains high, closely following the training accuracy.  
- Minimal gap between train and validation curves indicates strong generalization.  
- No significant overfitting or underfitting observed.  

**Conclusion:**  
Model MCTNN shows stable convergence, balanced learning, and reliable performance on unseen data.

---

## 🔹 Model Haar Cascade

**Observations:**
- Loss curves also drop quickly, suggesting efficient training.  
- Validation accuracy reaches 100% within only a few epochs, while training accuracy rises more slowly.  
- Large gap between training and validation accuracy may indicate **overfitting** or possible **data leakage**.  
- Validation set may not accurately represent the difficulty of the overall dataset.  

**Conclusion:**  
Model Haar Cascade appears to learn faster but may not generalize well. The validation performance seems overly optimistic and requires further verification.

---

## ⚖️ Overall Comparison

| Criteria | Model MCTNN | Model Haar Cascade |
|-----------|----------|----------|
| Convergence Speed | Fast | Very Fast |
| Stability | High | High |
| Train–Val Gap | Small | Large |
| Generalization | Strong | Questionable |
| Reliability | ✅ More Reliable | ⚠️ Needs Verification |

---

## ✅ Final Remark
- Model MCTNN provides a **more balanced and trustworthy performance**.  
- Model Haar Cascade’s unusually high validation accuracy suggests **overfitting or validation leakage**.  
- Further investigation into data splits or additional regularization is recommended before deployment.

## [Reference](https://pyimagesearch.com/2018/02/26/face-detection-with-opencv-and-deep-learning/)
- Face detection with Haar cascades: Extremely fast but prone to false-positives and in general less accurate than deep learning-based face detectors
- Face detection with dlib (HOG and CNN): HOG is more accurate than Haar cascades but computationally more expensive. Dlib’s CNN face detector is the most accurate of the bunch but cannot run in real-time without a GPU.
- Multi-task Cascaded Convolutional Networks (MTCNNs): Very accurate deep learning-based face detector. Easily compatible with both Keras and TensorFlow.


## Cre

**Kaggle** - [@link](https://www.kaggle.com/code/mk98kr/cnn-mtcnn-vs-Haar Cascade-face-detection?fbclid=IwY2xjawNgYe1leHRuA2FlbQIxMABicmlkETFOOElGNXBYQVVJWExIaEFZAR4VV81-vkELKLmkQg8DX1S-H4UVDP1dIQ8iPDhVuvOKt8BOlKNfwicam2ng9Q_aem_A1be-2j7c3x9Zq0DE2XQyw)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Thanks to the OpenCV community
- MTCNN paper authors and implementers
- Contributors to face detection research

