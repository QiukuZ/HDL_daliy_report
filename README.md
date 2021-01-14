## HDL_DAILY_REPORT

#### 目前情况:

- 激光电机外参标定完成
- 相机之间外外参/激光相机Base外参的标定按下图进行

<img src="image/0112-2.png" alt="0112-2" style="zoom:50%;" />

- 实验室人员多,计划0113早晨进行数据采集



#### 2021-01-13

- 数据采集[Done!]

<img src="image/0113-1.png" alt="0113-1" style="zoom:100%;" />

​	600+张运动相机的图像+ 5*5张相机系统图像 + 5个地点的激光扫描[如上图]

- 图像COLMAP运行[使用COLMAP估计的内参进行建图]

  所选用的相机模型 [fx,fy,cx,cy,k1,k2]

  一共注册了632张image + 152998 个特征点

  <img src="image/0113-2.png" alt="0113-2" style="zoom:50%;" />

<img src="image/0113-3.png" alt="0113-3" style="zoom:50%;" />



- 下一步: 使用AprilSLAM恢复相机的pose以及Tag的世界坐标[这一步可能需要采集的图像序列中对AprilTag的观测不间断]