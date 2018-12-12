# Free software of Progressive TIN Densification for filtering airborne LiDAR data ----Free PTD  

## 机载LIDAR点云滤波算法之-渐进三角网加密算法免费软件 Free PTD

<img src="./result1.png" style="width= 100%; height=auto">


### Free PTD 是一个免费的机载激光雷达（Lidar)滤波软件,你可以免费使用它，只要是非商业目的使用

### V0.6 发布 <a href = "https://pan.baidu.com/s/1MLFfsr0QD-86nAiCq70fEQ "> 百度链接下载</a> 密码：mp9p 详见<a href="#2">V0.6 Release Notes</a>


Free PTD 使用简单的命令行操作来提供处理的参数。使用方式可参见<a href="#1">参数设置></a>

Free PTD 使用参考TerraScan软件的渐进三角网加密算法来进行滤波。
双击打开FreePTD.exe,之后使用下列命令来处理一个一个las点云的滤波

    -i input_las.las -o output_las.las -d 1.2 -a 30 -m 60  

其中 input_las.las为需要处理的las格式的点云文件；
output_las.las 为处理后的结果文件；其他为参数；
output_las.las 结果中，会把点云分成两类，一类时地面点，一类时未分类点
算法在运行过程中不会考虑回波信息，仅仅提供最原始的渐进三角网滤波算法。

Free PTD采用CPU并行方式来进行加速，这可能会引起计算机CPU满负荷工作。
如果点云数量较大，可能需要更多的内存,此时可以采用分块策略即：使用-b <block_size> 命令来进行分块 例如以下命令：


    -i input_las.las -o output_las.las -d 1.2 -a 30 -m 60 -b 500

>注意：
Free PTD 不会对点云数据进行外点去除，因为极低点外点会影响滤波结果，所以请确定输入的点云
没有极低点。  
>Free PTD目前版本只提供window 64位，如果有其他操作系统需求，可以<a href="mailto:371000913@qq.com">email</a>

****
<a name="1"> 参数设置</a>

+  -i 输入需要滤波的las文件，支持1.0-1.2
+  -o 输出滤波后的las，输入的las数据被分成两类，未分类和地面，参见isprs las格式中分类的类别值
+  -d 点到三角形的距离阈值，默认值1.2  
+  -a 点和三角形端点的连线与三角形所在平面最大角阈值，默认值30
+  -m 最大建筑物大小，默认值60
+  -b <block size> 分块设置，block size 为分块大小，单位米(m) 采用分块后，Free PTD会自动进行分块缓存数据，从而减少使用的内存。通常 500 m 的分块大小一般不会使用超过4G的内存，这具体也要看点云的密度。如果内存更小，可以尝试减少分块大小。注意：分块是通过磁盘进行缓存数据，这会占用磁盘空间。Free PTD会使用输入点云input_las的路径缓存一些文件，待Free PTD退出后这些文件会自动删除。默认值500
+ -e 减少角度最小边长；当一个三角形的最长边长小于该值，则减少对应的角度为参数g对应的角度。默认值2.0
+ -g 最小角度；当达到-e对应的参数条件，那么迭代角度取该值；默认值2.0
+ -u 最小边长；当三角形最长边长小于该值时，不再迭代；默认值0.2
+ -t 最大迭代次数，默认值100


# <a name="2"> Release Notes</a>
---
## V 0.6 2018-12-12
1. 参考TerraScan实现

## V 0.4
1. 增加分块支持，可显著降低内存需求

## V 0.3      
1. 提高地面点数量


## V 0.2       
1. 增加自适应地形处理  
2. 增加角度a和距离d参数，增加分类标志参数c，增加自适应参数s

## V 0.1  
1. 实现算法初始版本

****

希望你在使用后，可以给我提供处理效果视频、图片，也可以提供原始的点云数据。这会帮助我提供对FreePTD更好的改进。我的Email： <a href="mailto:371000913@qq.com">371000913@qq.com</a>
