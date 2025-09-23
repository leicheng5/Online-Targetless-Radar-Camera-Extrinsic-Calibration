# Online-Targetless-Radar-Camera-Extrinsic-Calibration
Code for our paper: **Online Targetless Radar-Camera Extrinsic Calibration Based on the Common Features of Radar and Camera** 

**Preprint**: [https://arxiv.org/abs/2309.00787]. 

## Abstract
Sensor fusion is essential for autonomous driving and autonomous robots, and radar-camera fusion systems have gained popularity due to their complementary sensing capabilities. However, accurate calibration between these two sensors is crucial to ensure effective fusion and improve overall system performance. Calibration involves intrinsic and extrinsic calibration, with the latter being particularly important for achieving accurate sensor fusion. Unfortunately, many target-based calibration methods require complex operating procedures and well-designed experimental conditions, posing challenges for researchers attempting to reproduce the results. To address this issue, we introduce a novel approach that leverages deep learning to extract a common feature from raw radar data (i.e., Range-Doppler-Angle data) and camera images. Instead of explicitly representing these common features, our method implicitly utilizes these common features to match identical objects from both data sources. Specifically, the extracted common feature serves as an example to demonstrate an online targetless calibration method between the radar and camera systems.  The estimation of the extrinsic transformation matrix is achieved through this feature-based approach. To enhance the accuracy and robustness of the calibration, we apply the RANSAC and Levenberg-Marquardt (LM) nonlinear optimization algorithm for deriving the matrix. Our experiments in the real world demonstrate the effectiveness and accuracy of our proposed method.


