---
title: 记录钱德拉望远镜天文软件ciao的一些简单使用，本文能谱拟合基于sherpa
date: 2020-12-13
authors:
  - admin
  - Love Astro

tags:
  - Linux
  - sherpa

categories:
  - Linux
  - 天文
---

&emsp;&emsp;为了记录正在学习使用钱德拉望远镜的天文软件包**ciao**，写下这篇博客.
<!--more-->


**前言：**

heasoft的安装请参看：[HEAsoft安装教程](https://blog.csdn.net/qq_46753404/article/details/117304662)

## 一.下载样本数据

下载有专属的命令，本文以下载观测号**13858**为例.当然，你也可以官网先下载样本数据，之后解压就行.


1.下载命令：
```bash
download_chandra_obsid 13858 
```
注意：一定要初始化**ciao**，否则只会显示以下内容：
```bash
download_chandra_obsid: command not found
```
下载完以后会在你的当前目录下生成一个名为**13858**的目录.


2.下载数据后，首先进行预处理.这是每次处理数据前一定要做的事情！！！以保证软件包使用的是望远镜最新的相应文件.

预处理命令：

```bash
chandra_repro 13858 outdir=""
```
效果显示：

```bash
Running chandra_repro
version: 03 April 2020


Processing input directory '/home/wang/Downloads/13858'

Resetting afterglow status bits in evt1.fits file...

Running the destreak tool on the evt1.fits file...

Running acis_build_badpix and acis_find_afterglow to create a new bad pixel file...

Running acis_process_events to reprocess the evt1.fits file...
Output from acis_process_events:
# acis_process_events (CIAO 4.12): The following error occurred 2 times:
	dsAPEPULSEHEIGHTERR -- WARNING: pulse height is less than split threshold when performing serial CTI adjustment.
Filtering the evt1.fits file by grade and status and time...
Applying the good time intervals from the flt1.fits file...
The new evt2.fits file is: /home/wang/Downloads/13858/repro/acisf13858_repro_evt2.fits

Updating the event file header with chandra_repro HISTORY record
Creating FOV file...
Setting observation-specific bad pixel file in local ardlib.par.

Cleaning up intermediate files

WARNING: Observation-specific bad pixel file set for session use:
         /home/wang/Downloads/13858/repro/acisf13858_repro_bpix1.fits
         Run 'punlearn ardlib' when analysis of this dataset completed.

The data have been reprocessed.
Start your analysis with the new products in
/home/wang/Downloads/13858/repro

```

之后就会在你之前下载的观测号文件中生成一个名为**repro**的目录

## 二.建立源区域和背景区域
可以先查看**repro**目录下都有哪些文件.
 1.切换目录到repro：
```bash
cd 13858/repro
```
2.使用**ls**命令查看.

```bash
ls
```
效果显示如下：

```bash
acisf13858_000N001_bpix1.fits  acisf13858_repro_bpix1.fits
acisf13858_000N001_fov1.fits   acisf13858_repro_evt2.fits
acisf13858_000N001_msk1.fits   acisf13858_repro_flt2.fits
acisf13858_000N001_mtl1.fits   acisf13858_repro_fov1.fits
acisf13858_000N001_stat1.fits  acisf456520720N001_pbk0.fits
acisf13858_asol1.lis           pcadf456520092N001_asol1.fits

```

我们需要定义两个区域，一个用于源，另一个用于背景.要做到这一点，首先用**ds9**显示图像:

```bash
ds9 acisf13858_repro_evt2.fits
```
效果如下：
![image](https://github.com/wangboting/hugo-blog-theme/assets/71454203/1f21cc97-16e0-4714-a31e-619c36c9a985)

3.换颜色
点击**color**， 选**b**
![image](https://github.com/wangboting/hugo-blog-theme/assets/71454203/3ae65857-d718-4d46-9e4d-377b8da92563)


4.放大
点击**zoom**，再选择**zoom 4**
![image](https://github.com/wangboting/hugo-blog-theme/assets/71454203/d062e2cc-52fc-41b0-b4cd-1e1164043cc1)

5.选源（src_region）.
点击**edit**，后选择**region**，然后在源附近长按左键拖动，就会出现圆圈.这是src图效果
![image](https://github.com/wangboting/hugo-blog-theme/assets/71454203/d8480691-84b3-4fd7-9cbb-9bad0f592906)
6.选背景区域（bkg_region）
远离亮点，选一个较大的区域作为背景.步骤同第**5**步
![image](https://github.com/wangboting/hugo-blog-theme/assets/71454203/a2f9fcfb-153b-474f-b3bb-b53e72bbed16)

## 三、能谱拟合.
1.仍然在ciao初始化的环境下.依次输入以下命令.

```bash
punlearn specextract
pset specextract infile="acisf13858_repro_evt2.fits[sky=region(src.reg)]"
pset specextract bkgfile="acisf13858_repro_evt2.fits[sky=region(bkg.reg)]"
pset specextract outroot=13858
pset specextract clobber=yes
pset specextract grouptype=NUM_CTS
pset specextract binspec=30
pset specextract weight=no
specextract
```
2.进入**sherpa**.

```bash
sherpa
```
进入界面如下：
![image](https://github.com/wangboting/hugo-blog-theme/assets/71454203/b1d08047-083b-4055-8c30-0480014bd0a9)
依次输入以下内容：

```bash
load_pha('13858_grp.pi')
ignore(':0.8,8.0:')
subtract()
plot_data()
plt.savefig('notice.jpg')
set_source(xsphabs.abs1*powlaw1d.p1)
abs1.nH = 0.07
freeze(abs1.nH)
guess(p1)
fit()
plot_fit_delchi()
plt.savefig('fit.jpg')
```
我的拟合结果如下：![image](https://github.com/wangboting/hugo-blog-theme/assets/71454203/abbbdead-6c91-4547-8d21-085286c39465)


## 总结
一、下载需要的数据.

二、在ds9选区域.

三、能谱拟合.

<div id="commento"></div>
<script src="https://cdn.commento.io/js/commento.js"></script>


