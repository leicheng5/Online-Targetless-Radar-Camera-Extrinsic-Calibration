# Online-Targetless-Radar-Camera-Extrinsic-Calibration
Code for our paper: **Online Targetless Radar-Camera Extrinsic Calibration Based on the Common Features of Radar and Camera** 

**Preprint**: [https://arxiv.org/abs/2309.00787]. 

## I. Abstract
Sensor fusion is essential for autonomous driving and autonomous robots, and radar-camera fusion systems have gained popularity due to their complementary sensing capabilities. However, accurate calibration between these two sensors is crucial to ensure effective fusion and improve overall system performance. Calibration involves intrinsic and extrinsic calibration, with the latter being particularly important for achieving accurate sensor fusion. Unfortunately, many target-based calibration methods require complex operating procedures and well-designed experimental conditions, posing challenges for researchers attempting to reproduce the results. To address this issue, we introduce a novel approach that leverages deep learning to extract a common feature from raw radar data (i.e., Range-Doppler-Angle data) and camera images. Instead of explicitly representing these common features, our method implicitly utilizes these common features to match identical objects from both data sources. Specifically, the extracted common feature serves as an example to demonstrate an online targetless calibration method between the radar and camera systems.  The estimation of the extrinsic transformation matrix is achieved through this feature-based approach. To enhance the accuracy and robustness of the calibration, we apply the RANSAC and Levenberg-Marquardt (LM) nonlinear optimization algorithm for deriving the matrix. Our experiments in the real world demonstrate the effectiveness and accuracy of our proposed method.
<p align="center">
  <img src="https://github.com/radar-lab/Online-Targetless-Radar-Camera-Extrinsic-Calibration/blob/main/Figures/online_cali_flow.png" width="45%">
</p>

## II. Steps to Use this Repo
### 1. Train Common Feature Discriminator
Using **`Train_common.py`** in the folder **`Get_Common_Features\common_feats_net_car_person_final`** to train the Common Feature Discriminator model.

**`Test_common.py`** to test the accuracy of the Common Feature Discriminator.

### 2. Perform Calibration based on Common Feature
After training the Common Feature Discriminator, you can now use **`camera_to_radar_calibration.py`** or **`camera_to_radar_calibration_seperate_calib.py`** in the folder **`/Calibration_based_on_Common_Features`** to do the calibration.

Note that you should use the **`calibration.py`** in the folder **`/Calibration_based_on_Common_Features`** first to collect the point pairs between the radar and camera by using common feats, before you can do the calibration.


## III. Architecture of the YOLO-based Common Feature Network
<p align="center">
  <img src="https://github.com/radar-lab/Online-Targetless-Radar-Camera-Extrinsic-Calibration/blob/main/Figures/common_net_arch.png" width="60%">
</p>

## IV. Demo video
<a href="https://www.youtube.com/watch?v=DA0akV_fJ64">
  <img src="https://img.youtube.com/vi/DA0akV_fJ64/0.jpg" width="600">
</a>


## V. Demo video for our another Calibration paper
for our paper: **3D Radar and Camera Co-Calibration: A flexible and Accurate Method for Target-based Extrinsic Calibration** 

**Preprint**: [https://arxiv.org/abs/2307.15264]. 

### 1. Demo video 1
<a href="https://www.youtube.com/watch?v=_WVRrnrLCVU">
  <img src="https://img.youtube.com/vi/_WVRrnrLCVU/0.jpg" width="800">
</a>

### 2. Demo video 2
<a href="https://www.youtube.com/watch?v=FaFU3wxIb5g">
  <img src="https://img.youtube.com/vi/FaFU3wxIb5g/0.jpg" width="800">
</a>



