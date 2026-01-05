# Machine Specifications

Your Pandoro instance runs on dedicated hardware with full transparency for reproducible research.

## Hardware Overview

| Component | Specification |
|-----------|---------------|
| **GPU** | NVIDIA RTX 6000 Pro Blackwell |
| **CPU** | AMD Ryzen 9900X (12 cores / 24 threads) |
| **System RAM** | 128 GB |
| **System Drive** | 1 TB NVMe SSD |
| **Data Drive** | 4 TB NVMe SSD |

## GPU Details

The NVIDIA RTX 6000 Pro Blackwell is a professional-grade GPU built on NVIDIA's Blackwell architecture.

### Check GPU Status

```bash
nvidia-smi
```

This shows:
- GPU memory usage
- Running processes
- Temperature and power draw
- Driver version

### Monitor GPU Continuously

```bash
watch -n 1 nvidia-smi
```

Updates every second. Press `Ctrl+c` to stop.

## Storage

### System Drive (1 TB)

- Mounted at `/` (root)
- Contains your home directory (`~`)
- Use for: code, virtual environments, conda environments, configuration files

### Data Drive (4 TB)

- Mounted at `/mnt/data`
- Use for: datasets, model checkpoints, training outputs, large files

### Check Disk Usage

```bash
# Overall disk usage
df -h

# Size of current directory
du -sh .

# Size of data drive contents
du -sh /mnt/data/*
```

## CPU Information

The AMD Ryzen 9900X provides 12 physical cores with 24 threads via SMT (simultaneous multithreading).

### Check CPU Information

```bash
lscpu
```

### Monitor CPU and Memory

```bash
htop
```

Interactive process viewer. Press `q` to quit.

## Memory

128 GB of system RAM supports:
- Large dataset loading
- Multiple experiments in parallel
- Memory-intensive preprocessing

### Check Memory Usage

```bash
free -h
```

## Software Environment

Your instance comes with:
- NVIDIA drivers and CUDA toolkit
- Python and common ML frameworks
- Standard development tools

### Check CUDA Version

```bash
nvcc --version
```

### Check Python

```bash
python3 --version
```

## Performance Tips

### Use the Data Drive for Large Files

The data drive is optimized for large sequential reads/writes typical of ML workloads.

```python
# Save checkpoints to data drive
checkpoint_path = '/mnt/data/checkpoints/model.pt'
```

### Pin Data Loading to Multiple Workers

Take advantage of the 12-core CPU for data loading:

```python
# PyTorch DataLoader example
loader = DataLoader(dataset, batch_size=32, num_workers=8, pin_memory=True)
```

### Monitor Resources During Training

Open a second terminal (or tmux pane) to watch resource usage:

```bash
# GPU monitoring
watch -n 1 nvidia-smi

# CPU and memory monitoring
htop
```
