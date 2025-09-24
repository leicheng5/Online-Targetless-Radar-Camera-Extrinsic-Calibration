
<h1 align="center">🚀 Online-Targetless-Radar-Camera-Extrinsic-Calibration</h1>
<p align="center">
  <b>Paper:</b>
  <i>Online Targetless Radar-Camera Extrinsic Calibration Based on the Common Features of Radar and Camera</i>
</p>

<p align="center">
  <img src="https://img.shields.io/github/stars/radar-lab/Online-Targetless-Radar-Camera-Extrinsic-Calibration?style=social" alt="GitHub Repo stars"/>
  <img src="https://img.shields.io/github/forks/radar-lab/Online-Targetless-Radar-Camera-Extrinsic-Calibration?style=social" alt="GitHub forks"/>
  <img src="https://img.shields.io/github/last-commit/radar-lab/Online-Targetless-Radar-Camera-Extrinsic-Calibration" alt="GitHub last commit"/>
  <a href="https://arxiv.org/abs/2309.00787">
    <img src="https://img.shields.io/badge/arXiv-2309.00787-b31b1b.svg" alt="arXiv"/>
  </a>
</p>

---

## 🧑‍🤝‍🧑 Contributors

<a href="https://github.com/radar-lab/Online-Targetless-Radar-Camera-Extrinsic-Calibration/graphs/contributors">
  <img alt="Contributors" src="https://contrib.rocks/image?repo=radar-lab/Online-Targetless-Radar-Camera-Extrinsic-Calibration" />
</a>



## 📧 Contact
- 🧑‍💻 **Author**: [Lei Cheng](https://github.com/leicheng5)  
- 🏫 **Lab**   : [Radar-Lab](https://github.com/radar-lab)  

---
## 🎯 I. Abstract
Sensor fusion is essential for autonomous driving and autonomous robots, and radar-camera fusion systems have gained popularity due to their complementary sensing capabilities. However, accurate calibration between these two sensors is crucial to ensure effective fusion and improve overall system performance. Calibration involves intrinsic and extrinsic calibration, with the latter being particularly important for achieving accurate sensor fusion. Unfortunately, many target-based calibration methods require complex operating procedures and well-designed experimental conditions, posing challenges for researchers attempting to reproduce the results. To address this issue, we introduce a novel approach that leverages deep learning to extract a common feature from raw radar data (i.e., Range-Doppler-Angle data) and camera images. Instead of explicitly representing these common features, our method implicitly utilizes these common features to match identical objects from both data sources. Specifically, the extracted common feature serves as an example to demonstrate an online targetless calibration method between the radar and camera systems.  The estimation of the extrinsic transformation matrix is achieved through this feature-based approach. To enhance the accuracy and robustness of the calibration, we apply the RANSAC and Levenberg-Marquardt (LM) nonlinear optimization algorithm for deriving the matrix. Our experiments in the real world demonstrate the effectiveness and accuracy of our proposed method.
<p align="center">
  <img src="https://github.com/radar-lab/Online-Targetless-Radar-Camera-Extrinsic-Calibration/blob/main/Figures/online_cali_flow.png" width="45%">
</p>



## 📌 II. Steps to Use this Repo

---

### 🔹 1. Train Common Feature Discriminator
- Train the Common Feature Discriminator model:  
  ```bash
  python Get_Common_Features/common_feats_net_car_person_final/Train_common.py
  ```

* Test the accuracy:

  ```bash
  python Get_Common_Features/common_feats_net_car_person_final/Test_common.py
  ```

---

### 🔹 2. Perform Calibration based on Common Feature

After training the Common Feature Discriminator, you can now use:

* **Joint calibration**

  ```bash
  python Calibration_based_on_Common_Features/camera_to_radar_calibration.py
  ```
* **Separate calibration**

  ```bash
  python Calibration_based_on_Common_Features/camera_to_radar_calibration_seperate_calib.py
  ```

⚠️ **Note**:
Before running calibration, you should first collect the point pairs between the radar and camera by using common features:

```bash
python Calibration_based_on_Common_Features/calibration.py
```

## 🖼️ III. Architecture of the YOLO-based Common Feature Network
<p align="center">
  <img src="https://github.com/radar-lab/Online-Targetless-Radar-Camera-Extrinsic-Calibration/blob/main/Figures/common_net_arch.png" width="60%">
</p>

## 🎥 IV. Demo video
<a href="https://www.youtube.com/watch?v=DA0akV_fJ64">
  <img src="https://img.youtube.com/vi/DA0akV_fJ64/0.jpg" width="600">
</a>






---

<h1 align="center">🚀 3D Radar and Camera Co-Calibration</h1>

<p align="center">
  <b>Paper:</b>
  <i>3D Radar and Camera Co-Calibration: A Flexible and Accurate Method for Target-based Extrinsic Calibration</i>
</p>

<p align="center">
  <img src="https://img.shields.io/github/stars/radar-lab/Online-Targetless-Radar-Camera-Extrinsic-Calibration?style=social" alt="GitHub Repo stars"/>
  <img src="https://img.shields.io/github/forks/radar-lab/Online-Targetless-Radar-Camera-Extrinsic-Calibration?style=social" alt="GitHub forks"/>
  <img src="https://img.shields.io/github/last-commit/radar-lab/Online-Targetless-Radar-Camera-Extrinsic-Calibration" alt="GitHub last commit"/>
  <a href="https://arxiv.org/abs/2307.15264">
    <img src="https://img.shields.io/badge/arXiv-2307.15264-b31b1b.svg" alt="arXiv"/>
  </a>
</p>

---
## 🎯 I. Abstract
Advances in autonomous driving are inseparable from sensor fusion. Heterogeneous sensors are widely used for sensor fusion due to their complementary properties, with radar and camera being the most equipped sensors. Intrinsic and extrinsic calibration are essential steps in sensor fusion. The extrinsic calibration, independent of the sensor's own parameters, and performed after the sensors are installed, greatly determines the accuracy of sensor fusion. Many target-based methods require cumbersome operating procedures and well-designed experimental conditions, making them extremely challenging. To this end, we propose a flexible, easy-to-reproduce and accurate method for extrinsic calibration of 3D radar and camera. The proposed method does not require a specially designed calibration environment, and instead places a single corner reflector (CR) on the ground to iteratively collect radar and camera data simultaneously using Robot Operating System (ROS), and obtain radar-camera point correspondences based on their timestamps, and then use these point correspondences as input to solve the perspective-n-point (PnP) problem, and finally get the extrinsic calibration matrix. Also, RANSAC is used for robustness and the Levenberg-Marquardt (LM) nonlinear optimization algorithm is used for accuracy. Multiple controlled environment experiments as well as real-world experiments demonstrate the efficiency and accuracy (AED error is 15.31 pixels and Acc up to 89%) of the proposed method.
<p align="center">
  <img src="https://github.com/radar-lab/Online-Targetless-Radar-Camera-Extrinsic-Calibration/blob/main/Figures/principle3.png" width="55%">
</p>

---

### 🎥 1. Demo video 1
<a href="https://www.youtube.com/watch?v=_WVRrnrLCVU">
  <img src="https://img.youtube.com/vi/_WVRrnrLCVU/0.jpg" width="800">
</a>

### 🎥 2. Demo video 2
<a href="https://www.youtube.com/watch?v=FaFU3wxIb5g">
  <img src="https://img.youtube.com/vi/FaFU3wxIb5g/0.jpg" width="800">
</a>



