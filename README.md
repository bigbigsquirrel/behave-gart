# behave-gart
## BEHAVE
The BEHAVE dataset offers multi-view RGB-D sequences capturing 3D human-object interactions, with SMPL-based human tracking and template-mesh object tracking. It contains 15.2k annotated frames(10.7k frames for training and 4.5k frames for testing respectively) (including contact labels) from 8 participants and 20 objects across 5 environments, supporting research in interaction modeling.
- multiview(4 cams)
- interactions between human and objects
- rgb, mask, SMPL, calibs parameters
<img width="1141" alt="image" src="https://github.com/user-attachments/assets/6ccc3de6-f90c-4043-a2fa-40f2744648a8" />


### datasets structure
以一个场景(Data01 yogaball_play)为例：
```
DATASET_PATH
|--calibs           # Kinect camera intrinsics and extrinsics for different locations
|----Date01         
|------background   # background image and point cloud 
|------config       # camera poses(extrinsics)
|------intrinsics      # intrinsics of 4 kinect camera
|--videos
|----cam00.mp4
|----cam01.mp4
|----cam02.mp4
|----cam03.mp4
|--Date01_Sub01_yogaball_play
|----t00[xx].000        # 第xx个帧的图像、点云、poses信息等
|------k[0-3].color.jpg           # 四个相机角度的rgb图片
|------k[0-3].depth.png           # 四个相机角度的depth图片
|------k[0-3].person_mask.jpg     # human masks
|------k[0-3].obj_rend_mask.jpg   # object masks
|------k[0-3].color.json          # openpose detections, OpenPose工具生成的人体姿态估计
|------k[0-3].mocap.[json|ply]    # FrankMocap estimated pose and mesh
|------person
|--------person.ply               # segmented person point cloud
|--------fit02                    # registered SMPL mesh and parameters
|------object_name
|--------object_name.ply          # segmented object point cloud
|--------fit01                    # object registrations
|------------       


```
