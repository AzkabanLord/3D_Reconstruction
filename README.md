# 3D_Reconstruction
## First Commit
This project can perform 3D reconstruction either on dataset or on gazebo.

It now does not perform the scene reconstruction of the fusion of LIDAR and RGBD camera, but instead runs independently either on LIDAR or RGBD camera.
### Build
First build the packages inside the repo independently.
Build [voxblox_ros](https://voxblox.readthedocs.io/en/latest/pages/Installation.html) .

Build the remaining packages just simply use catkin build 

`` catkin build orb_slam2_ros image_pipeline aloam_velodyne``

### Run

Run with RGBD on dataset (tested on [TUM](https://vision.in.tum.de/data/datasets/rgbd-dataset/download) )

Before running the dataset, double check the path of the dataset in your PC in dataset_tum1.launch. Then use 
 
 ``roslaunch orb_slam2_ros dataset_tum1.launch``
 
 to launch your dataset.
 
 Run with RGBD on gazebo (tested with Intel RealSense D435)
 
 Also, check the topic published by gazebo in sim_d435.launch, then use
  
  ``roslaunch orb_slam2_ros sim_d435.launch``
  
  Run with LIDAR on dataset (tested on Velodyne_VLP_16 [dataset](https://drive.google.com/file/d/1s05tBQOLNEDDurlg48KiUWxCp-YqYyGH/view)
  
  Modify the path and published topic and run
  
  ``roslaunch aloam_velodyne dataset_city.launch``
  
  The same with simulating velodyne_VLP_16 on gazebo, launch
  
  ``roslaunch aloam_velodyne sim_velodyne_16.launch``
  
If you want more details of the scence, modify ``voxel_size`` to better fit with 3D scene.
  
