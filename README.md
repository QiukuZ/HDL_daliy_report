# HDL_daliy_report

# HDL_map

### 数据采集:

- 激光数据采集

  录制rosbag并解析

- 图像数据采集

  使用Python脚本,依次启动相机,并抓取图像

### 标定整体框架:

![pipeline](image/pipeline.png)

### 2020.12.24

**当前进展:**

- AprilTag检测与点云生成
- 2D激光点云手动筛选
- 激光点云与AprilTag点云粗对齐与ICP配准
- 点云重投影并着色



**结果:**

- AprilTag检测

  <img src="image/apriltag_detect.png" alt="apriltag_detect" style="zoom:30%;" />

- ICP结果

<img src="image/align_result.png" alt="align_result" style="zoom:30%;" />

- 重投影结果

  <img src="image/reproj_result.png" alt="reproj_result" style="zoom:30%;" />

  ​	从重投影的结果中看外参的估计还是存在问题
  
- 点云着色结果

  <img src="image/result1.png" alt="result" style="zoom:33%;" />

**当前存在问题:**

1. 外参存在误差
   - 解决思路:
     - 在场景中增加Apriltag的数量,并合理分布
     - 将激光点云分割后,分别对平面进行拟合,然后通过点到面的误差进行优化
   
2. 遮挡问题

   由于激光和相机的物理位置存在差异,因此实际上激光的点云的遮挡关系和相机的图像中的遮挡关系并非完全一直,如果直接进行点到相机的投影,会存在一定的错误关系.





### 增加Apriltag板

​	如图

<img src="image/apriltag1.png" alt="april new" style="zoom:33%;" />

<img src="image/apriltag2.png" alt="apriltag2" style="zoom:33%;" />

目前存在问题:电机的电路板疑似烧坏,无法正常采集激光数据.已经向靖鑫要了一块新的.预计明天换上后可以正常采集激光数据.