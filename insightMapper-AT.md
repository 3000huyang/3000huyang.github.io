# InsightMapper-AT

InsightMapper-AT 是一款免费的空三软件


免责声明：
本软件仅为科研学习之用，不对其产生的任何结果负法律责任

## Download

## V 1.1.0711

链接：https://pan.baidu.com/s/113o2ETsLOcuO8lQDyRCOgg 
提取码：z34i 

## 使用步骤

- 1 新建工程，输入名称目录等信息
- 2 点击‘Project setting’
    - 2.1 'add camera' 增加相机，设置相机参数，其中width,height,ppx,ppy,focal(pix)为必填
    - 2.2 'import images' 添加图像，添加后选择某个相机，或者新建相机，或者从exif中自动读取相机
            该过程会比较慢，软件会尝试读取经纬度等坐标信息
   -  2.3'import pose'导入GPS/IMU pose信息，支持个转角为omega，phi，kappa，弧度，如果是其他格式，可以通过3.1操作生成该格式
- 3 pose 转换
   -  3.1 'Process'->'Convert pose' 导入pose数据，通过preview辅助观察参数是否正确，如果正确，点击‘save’导出
- 4 空三
  - 点击 ‘Align images’进行空三
  - 点击 ‘post Adjustment’进行绝对定项，控制点平差，注意要先进行绝对定向然后进行平差
 - 其他功能


# version

- 1.1.0711 增加坐标系支持 
- 1.1.0706 支持导出ContextCapture格式，由于坐标系重新开发，暂时只支持自由网空三
  - 
- 1.1 目前为1000张测试版本，稳定之后再提供更多