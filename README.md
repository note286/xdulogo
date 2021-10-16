# 目录

- [项目名称](#项目名称)
- [素材来源](#素材来源)
- [成果展示](#成果展示)
  * [西电新标志1](#西电新标志1)
    + [白色-透明](#白色-透明)
    + [红色-不透明](#红色-不透明)
    + [红色-透明](#红色-透明)
    + [蓝色-不透明](#蓝色-不透明)
    + [蓝色-透明](#蓝色-透明)
  * [西电新标志2](#西电新标志2)
    + [白色-透明](#白色-透明)
    + [红色-黑色-不透明](#红色-黑色-不透明)
    + [红色-黑色-透明](#红色-黑色-透明)
    + [蓝色-黑色-不透明](#蓝色-黑色-不透明)
    + [蓝色-黑色-透明](#蓝色-黑色-透明)
  * [西电新标志3](#西电新标志3)
    + [白色-透明](#白色-透明)
    + [红色-黑色-不透明](#红色-黑色-不透明)
    + [红色-黑色-透明](#红色-黑色-透明)
    + [蓝色-黑色-不透明](#蓝色-黑色-不透明)
    + [蓝色-黑色-透明](#蓝色-黑色-透明)
  * [西电新标志4](#西电新标志4)
    + [白色-透明](#白色-透明)
    + [黑色-不透明](#黑色-不透明)
    + [黑色-透明](#黑色-透明)
- [转换代码](#转换代码)
- [作者](#作者)

# 项目名称

xdulogo-Xidian University Postgraduate Logo

西安电子科技大学校徽校

# 素材来源

素材下载自[西安电子科技大学校徽校名（JPG版本）-西安电子科技大学—党委宣传网](https://xcb.xidian.edu.cn/info/1008/1094.htm)

根据[VIS-西安电子科技大学新闻网](https://news.xidian.edu.cn/VIS.htm)中关于红蓝两色的要求对颜色进行了修正，确保每张图片中的颜色仅包含西电红、西电蓝、黑色、白色四种颜色之中的几种。另外已使用脚本对每一个像素的元素进行了检查，确保颜色的纯正。

# 成果展示

## 西电新标志1

### 白色-透明

![西电新标志1-白色-透明](西电新标志1-白色-透明.png)

### 红色-不透明

![西电新标志1-红色-不透明](西电新标志1-红色-不透明.png)

### 红色-透明

![西电新标志1-红色-透明](西电新标志1-红色-透明.png)

### 蓝色-不透明

![西电新标志1-蓝色-不透明](西电新标志1-蓝色-不透明.png)

### 蓝色-透明

![西电新标志1-蓝色-透明](西电新标志1-蓝色-透明.png)

## 西电新标志2

### 白色-透明

![西电新标志2-白色-透明](西电新标志2-白色-透明.png)

### 红色-黑色-不透明

![西电新标志2-红色-黑色-不透明](西电新标志2-红色-黑色-不透明.png)

### 红色-黑色-透明

![西电新标志2-红色-黑色-透明](西电新标志2-红色-黑色-透明.png)

### 蓝色-黑色-不透明

![西电新标志2-蓝色-黑色-不透明](西电新标志2-蓝色-黑色-不透明.png)

### 蓝色-黑色-透明

![西电新标志2-蓝色-黑色-透明](西电新标志2-蓝色-黑色-透明.png)

## 西电新标志3

### 白色-透明

![西电新标志3-白色-透明](西电新标志3-白色-透明.png)

### 红色-黑色-不透明

![西电新标志3-红色-黑色-不透明](西电新标志3-红色-黑色-不透明.png)

### 红色-黑色-透明

![西电新标志3-红色-黑色-透明](西电新标志3-红色-黑色-透明.png)

### 蓝色-黑色-不透明

![西电新标志3-蓝色-黑色-不透明](西电新标志3-蓝色-黑色-不透明.png)

### 蓝色-黑色-透明

![西电新标志3-蓝色-黑色-透明](西电新标志3-蓝色-黑色-透明.png)

## 西电新标志4

### 白色-透明

![西电新标志4-白色-透明](西电新标志4-白色-透明.png)

### 黑色-不透明

![西电新标志4-黑色-不透明](西电新标志4-黑色-不透明.png)

### 黑色-透明

![西电新标志4-黑色-透明](西电新标志4-黑色-透明.png)



# 转换代码

需要先下载安装[ImageMagick](https://imagemagick.org/script/download.php)，以下代码仅在Windows平台测试，不过应该可以移除注释运行在其他平台上。

```shell
rem 原始素材
copy org\西电新标志1.jpg .
copy org\西电新标志2.jpg .
copy org\西电新标志3.jpg .
copy org\西电新标志4.jpg .
rem 校正红色和黑色
rem 大约不是白色的填充为西电红 接着不是西电红的全部填充为白色
convert 西电新标志1.jpg -fuzz 30% -fill "#AF2125" +opaque white -fill white +opaque "#AF2125" -define png:exclude-chunks=date,time 西电新标志1-红色-不透明.png
rem 先处理左区域 再处理右区域
rem 左区域大约不是白色的填充为西电红 接着不是西电红的全部填充为白色
convert 西电新标志2.jpg -region 750x800+0+0 -fuzz 30% -fill "#AF2125" +opaque white -fill white +opaque "#AF2125" 西电新标志2-红色-黑色-不透明-临时.png
rem 右区域大约不是白色的填充为黑色 接着不是黑色的全部填充为白色
convert 西电新标志2-红色-黑色-不透明-临时.png -region 1800x800+740+0 -fuzz 30% -fill black +opaque white -fill white +opaque black -define png:exclude-chunks=date,time 西电新标志2-红色-黑色-不透明.png
del 西电新标志2-红色-黑色-不透明-临时.png
rem 先处理上区域 再处理下区域
rem 上区域大约不是白色的填充为西电红 接着不是西电红的全部填充为白色
convert 西电新标志3.jpg -region 1800x1050+0+0 -fuzz 30% -fill "#AF2125" +opaque white -fill white +opaque "#AF2125" 西电新标志3-红色-黑色-不透明-临时.png
rem 下区域大约不是白色的填充为黑色 接着不是黑色的全部填充为白色
convert 西电新标志3-红色-黑色-不透明-临时.png -region 1800x800+0+1000 -fuzz 30% -fill black +opaque white -fill white +opaque black -define png:exclude-chunks=date,time 西电新标志3-红色-黑色-不透明.png
del 西电新标志3-红色-黑色-不透明-临时.png
rem 大约不是白色的填充为黑色 接着不是黑色的全部填充为白色
convert 西电新标志4.jpg -fuzz 30% -fill black +opaque white -fill white +opaque black -define png:exclude-chunks=date,time 西电新标志4-黑色-不透明.png
rem 移除白底
convert 西电新标志1-红色-不透明.png -fuzz 30% -transparent white -define png:exclude-chunks=date,time 西电新标志1-红色-透明.png
convert 西电新标志2-红色-黑色-不透明.png -fuzz 30% -transparent white -define png:exclude-chunks=date,time 西电新标志2-红色-黑色-透明.png
convert 西电新标志3-红色-黑色-不透明.png -fuzz 30% -transparent white -define png:exclude-chunks=date,time 西电新标志3-红色-黑色-透明.png
convert 西电新标志4-黑色-不透明.png -fuzz 30% -transparent white -define png:exclude-chunks=date,time 西电新标志4-黑色-透明.png
rem 替换为蓝色
convert 西电新标志1-红色-不透明.png -fill "#004182" -opaque "#AF2125" -define png:exclude-chunks=date,time 西电新标志1-蓝色-不透明.png
convert 西电新标志2-红色-黑色-不透明.png -fill "#004182" -opaque "#AF2125" -define png:exclude-chunks=date,time 西电新标志2-蓝色-黑色-不透明.png
convert 西电新标志3-红色-黑色-不透明.png -fill "#004182" -opaque "#AF2125" -define png:exclude-chunks=date,time 西电新标志3-蓝色-黑色-不透明.png
rem 移除白底
convert 西电新标志1-蓝色-不透明.png -transparent white -define png:exclude-chunks=date,time 西电新标志1-蓝色-透明.png
convert 西电新标志2-蓝色-黑色-不透明.png -transparent white -define png:exclude-chunks=date,time 西电新标志2-蓝色-黑色-透明.png
convert 西电新标志3-蓝色-黑色-不透明.png -transparent white -define png:exclude-chunks=date,time 西电新标志3-蓝色-黑色-透明.png
rem 生成白色透明底素材
convert 西电新标志1-红色-透明.png -fill white -opaque "#AF2125" -fill white -opaque black -define png:exclude-chunks=date,time 西电新标志1-白色-透明.png
convert 西电新标志2-红色-黑色-透明.png -fill white -opaque "#AF2125" -fill white -opaque black -define png:exclude-chunks=date,time 西电新标志2-白色-透明.png
convert 西电新标志3-红色-黑色-透明.png -fill white -opaque "#AF2125" -fill white -opaque black -define png:exclude-chunks=date,time 西电新标志3-白色-透明.png
convert 西电新标志4-黑色-透明.png -fill white -opaque black -define png:exclude-chunks=date,time 西电新标志4-白色-透明.png
rem 移除原始素材
del 西电新标志1.jpg
del 西电新标志2.jpg
del 西电新标志3.jpg
del 西电新标志4.jpg
```

# 作者

- [@note286](https://github.com/note286)

