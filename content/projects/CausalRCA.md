---
title: CausalRCA
date: 2025-10-21
weight: 3
---

## 🚀 快速开始

### 下载数据集

下载链接：---------------------

### 环境设置


# 安装依赖
```bash
uv sync

```

### 环境变量配置

```bash
export RCABENCH_BASE_URL=http://10.10.10.220:32080
export RCABENCH_USERNAME=admin
export RCABENCH_PASSWORD=admin123
export CHECKPOINT_PATH=checkpoints/train_dataset_17/best_model.ckpt
```

### 模型训练

```bash
sudo -E .venv/bin/python client.py train-by-id --dataset-id 17
```


## 🔧 部署

### Docker构建

```bash
docker build -t 10.10.10.240/library/rca-algo-eadro:study .
```

### 算法上传

```bash
rca upload-algorithm-harbor ./
```

## 🧪 测试与评估

### 批量测试

```bash
sudo -E .venv/bin/python run.py batch-test --label 8.26run
```

### 指标评估

```bash
# 使用最新平台进行评估
rca cross-dataset-metrics -a eadro -d pair-diag -dv study-test --tag 8.26run
```