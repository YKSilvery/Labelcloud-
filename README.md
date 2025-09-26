# labelCloud 中文新手教程

## 目录
1. 简介
2. 安装Python
3. 安装labelCloud
4. 准备点云数据
5. 配置软件
6. 开始标注
7. 快捷键参考
8. 导出格式
9. 获取帮助
10. 学术使用

## 简介
labelCloud是一个轻量级的点云3D边界框标注工具，用于为3D物体检测任务创建训练数据。它支持多种点云格式和标注导出格式，适合计算机视觉和自动驾驶领域的研究和开发。

## 安装Python
1. 访问Python官网(https://www.python.org/downloads/)
2. 下载Python 3.7、3.8或3.9版本（labelCloud支持这些版本）
3. 运行安装程序，务必勾选"Add Python to PATH"选项
4. 完成安装后，打开命令提示符(CMD)或终端，输入以下命令验证安装：
   python --version
   应该显示安装的Python版本号。

## 安装labelCloud
### 方法一：通过pip安装（推荐新手）
pip install labelCloud
labelCloud --example  # 启动带有示例点云的labelCloud

### 方法二：通过git克隆安装
git clone https://github.com/ch-sa/labelCloud.git
cd labelCloud
pip install -r requirements.txt
python labelCloud.py

## 准备点云数据
1. 在labelCloud目录下创建或使用已有的pointclouds文件夹
2. 将你的点云文件放入该文件夹
3. 支持的格式包括：
   - 彩色点云：.pcd, .ply, .pts, .xyzrgb
   - 无色点云：.xyz, .xyzn, .bin (KITTI格式)

## 配置软件
编辑config.ini文件来自定义设置，或通过图形界面中的设置菜单进行调整。主要配置包括：
- 点云文件夹路径
- 标签保存路径
- 点大小和颜色设置
- 标注框默认尺寸等

## 开始标注
labelCloud提供两种标注模式和多种校正功能。

### 点选模式(Picking Mode)
1. 点击确定边界框的前上边缘位置
2. 使用鼠标滚轮调整z轴旋转角度

### 跨度模式(Spanning Mode)
1. 依次选择四个顶点来确定边界框的长度、宽度和高度
2. 最后两个顶点（宽度和高度）的图层会被锁定以便选择

### 校正功能
- 使用左侧按钮或快捷键校正边界框的平移、尺寸和旋转
- 将光标悬停在边界框的某一面上，使用鼠标滚轮调整尺寸

### 高级功能
9自由度边界框标注：在菜单或设置中取消勾选"仅z轴旋转"模式，即可标注绕所有三个轴旋转的边界框。

语义分割：在启动对话框中切换分割按钮，标注完成后点击"Assign"按钮为边界框内的所有点分配标签。

## 快捷键参考
快捷键       功能描述
左键拖动      旋转视角
右键拖动      平移视角
鼠标滚轮      缩放
W/A/S/D      平移边界框
Z/X          z轴旋转
Del          删除当前边界框
1-9          选择前9个边界框

## 导出格式
labelCloud支持多种导出格式，包括：
- centroid_rel：中心点坐标+尺寸+相对旋转角度（弧度）
- centroid_abs：中心点坐标+尺寸+绝对旋转角度（度数）
- vertices：8个顶点坐标
- kitti：KITTI格式（需要标定文件）

## 获取帮助
如果在使用过程中遇到问题：
1. 查看详细文档(https://github.com/ch-sa/labelCloud)
2. 检查配置文件中参数设置
3. 通过邮箱联系开发者：christoph.sager@gmail.com

## 学术使用
如在学术项目中使用本工具，请引用相关论文：
@article{Sager_2022,
    doi = {10.14733/cadaps.2022.1191-1206},
    url = {http://cad-journal.net/files/vol_19/CAD_19(6)_2022_1191-1206.pdf},
    year = 2022,
    volume = {19},
    number = {6},
    pages = {1191--1206},
    author = {Christoph Sager and Patrick Zschech and Niklas Kuhl},
    title = {labelCloud: A Lightweight Labeling Tool for Domain-Agnostic 3D Object Detection in Point Clouds},
    journal = {Computer-Aided Design and Applications}
}

现在你已经准备好开始使用labelCloud进行3D点云标注了！祝你使用愉快！
