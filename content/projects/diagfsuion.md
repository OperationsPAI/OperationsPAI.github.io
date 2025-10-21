---
title: diagfusion
date: 2025-10-21
weight: 3
---

## 🚀 快速开始

### 下载数据集

下载链接：---------------------

### 环境设置

```bash
# 安装依赖
uv sync

```

### 环境变量配置

```bash
export CHECKPOINT_PATH=./data/middle/checkpoints/service_model.pt 
export DYNACONF_PATHS__METADATA=./data/middle/metadata 
export DYNACONF_PATHS__CKPT=./data/middle/checkpoints 
export RCABENCH_BASE_URL=http://10.10.10.220:32080
export RCABENCH_USERNAME=admin
export RCABENCH_PASSWORD=admin123
```

### 模型训练

```bash
sudo -E .venv/bin/python client.py --config rcabench.yaml
```

### 数据后处理

训练完成后需要复制相关文件：

```bash
sudo cp data/rcabench/demo/demo2/dgl/stratification_10/9/topology.pkl data/middle/metadata/ -f
sudo cp data/rcabench/demo/demo2/anomalies/service_instance_mapping.json data/middle/metadata/ -f
sudo rm -rf data/rcabench/demo/demo2
```

## 🔧 部署

### Docker构建

```bash
docker build -t 10.10.10.240/library/rca-algo-diagfusion:study .
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
rca cross-dataset-metrics -a diagfusion -d pair-diag -dv study-test --tag 8.26run
```


```