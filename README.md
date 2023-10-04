# Museum
## 1. [ROS noetic](http://wiki.ros.org/noetic)
OS: ubuntu 20.04 LTS

## 2. Opencv
### Version >= 4.6.0(c++/python aruco api changed in 4.6.0)
### **USAGE**
1. undistorted the images and videos

## 3. [Kalibr](https://github.com/ethz-asl/kalibr)
### **USAGE**: 
1. Calibration board: [Target](https://drive.google.com/file/d/1DqKWgePodCpAKJCd_Bz-hfiEQOSnn_k0/view), [Config](https://drive.google.com/file/d/1rAe_O8eFD3nR06SzhoGIUrq4BUhuaekn/view)
1. [Multiple camera calibration](https://github.com/ethz-asl/kalibr/wiki/multiple-camera-calibration): support monocular 
camera calibration
2. [Camera-IMU calibration](https://github.com/ethz-asl/kalibr/wiki/camera-imu-calibration): get transformation from camera to imu (body frame)
3. [Multi-IMU and IMU intrinsic calibration](https://github.com/ethz-asl/kalibr/wiki/Multi-IMU-and-IMU-intrinsic-calibration): get IMU intrinsic(accelerometer_noise_density, accelerometer_random_walk, gyroscope_noise_density, gyroscope_random_walk)
1. bag_extractor: extract gray images and imu from bag
```bash
# example
rosrun kalibr kalibr_bagextractor --image-topics /camera/color/image_raw --imu-topics /camera/imu --bag t1.bag
```   

## 4. Realsense

## 5. SLAM
### 5.1 [ORB_SLAM3](https://github.com/UZ-SLAMLab/ORB_SLAM3)  
original version of ORB_SLAM3
**INPUT(images) => OUTPUT(6D Pose + trajectory + map(feature points))**
### 5.2 [ORB_SLAM3_GO_PRO](https://github.com/urbste/ORB_SLAM3)(use this project as main project)  
Support GO PRO and insta one R  
**INPUT([videos](https://github.com/urbste/ORB_SLAM3/blob/master/Examples/Monocular-Inertial/mono_inertial_gopro_vi.cc)) => OUTPUT(6D Pose + trajectory + map(feature points))**
### 5.3 [ORB_SLAM3_FAST_IMU_INIT](https://github.com/lturing/ORB_SLAM3_FAST_IMU_INIT)  
<span style="color:red">[UNVERIFIED]</span>
Make ORB_SLAM3 IMU initialize faster than original version

## 6. Feature points extracting and matching
### 6.1 [SuperPoint](https://github.com/rpautrat/SuperPoint)
### 6.2 [SuperGlue](https://github.com/magicleap/SuperGluePretrainedNetwork)
### 6.3 [LightGlue](https://github.com/cvg/LightGlue)
### 6.4 [e2e_multi_view_matching](https://github.com/barbararoessle/e2e_multi_view_matching) (waiting for code)
### 6.5 [ORB](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=6126544)
### 6.6 [FAST: Features from Accelerated Segment Test](https://homepages.inf.ed.ac.uk/rbf/CVonline/LOCAL_COPIES/AV1011/AV1FeaturefromAcceleratedSegmentTest.pdf?ref=https://githubhelp.com)
### 6.7 [BRIEF: Binary Robust Independent Elementary Features](https://os.unil.cloud.switch.ch/tind-customer-epfl/f2565c9b-2939-46b0-90d4-51a560832321?response-content-disposition=attachment%3B%20filename%2A%3DUTF-8%27%27top_1.pdf&response-content-type=application%2Fpdf&AWSAccessKeyId=ded3589a13b4450889b2f728d54861a6&Expires=1695904580&Signature=R4N7TtZNIvziTwWe8oBUHczKjPw%3D)