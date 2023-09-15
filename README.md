# LUSS_plus
(Jittor) This is a large-scale unsupervised semantic segmentation of open source code implemented using jittor (LUSS_plus).

# Jittor 大规模无监督语义分割比赛 baseline


## 简介

本项目包含了第三届计图挑战赛计图 - 大规模无监督语义分割比赛的代码实现。本项目的特点是：采用了PASS模型对ImageNet-S50大规模无监督语义分割数据集进行训练和测试，取得了mIoU=0.285016的效果。

## 安装 

本项目可在 2 张 3090 上运行，训练时间约为 60 小时。

#### 运行环境

- ubuntu 18.04 LTS
- python == 3.8
- jittor == 1.3.7.16
- mpirun
- sklearn
- numpy
- tqdm
- PIL
- pandas
- munkres
- faiss

#### 训练模型

训练模型模型下载地址为链接：[百度网盘](https://pan.baidu.com/s/1E_gc3rGZtV0Ibf3X463ChA) 提取码：pdcc，下载后分别将checkpoint.pth.tar与ckp-19.pth.tar权重文件放入目录"weights\pass50\pixel_finetuning"与"weights\pass50\pixel_finetuning\checkpoints"下。

## 数据预处理

将ImageNet数据下载后，按照以下链接对ImageNet数据预处理制作ImageNet-S数据集：

[LUSS数据集制作](https://github.com/LUSSeg/ImageNet-S)

## 训练


单卡训练可运行以下命令：

```
bash train_singleGPU.sh
```

多卡训练可以运行以下命令：

```
bash scripts/train-multigpu.sh
```

## 推理


生成测试集上的结果可以运行以下命令：

```
python test.py
```

## 致谢

此项目基于论文 Large-scale Unsupervised Semantic Segmentation* 实现，部分代码参考了 [jittor-pass](https://github.com/LUSSeg/PASS/tree/jittor)。
