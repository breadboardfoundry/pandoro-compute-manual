# File Management

This guide covers how to download files from your Pandoro instance to your local computer.

## Downloading Files via VSCode

The browser-based VSCode interface provides the easiest way to download files.

### Download a Single File

1. Open VSCode at `https://code001.pandoro.today/`
2. In the **File Explorer** (left sidebar), navigate to your file
3. **Right-click** on the file
4. Select **Download**
5. The file saves to your browser's download location

### Download a Folder

1. Right-click on the folder in the File Explorer
2. Select **Download**
3. The folder downloads as a zip archive

## Storage Locations

Your machine has two storage locations:

| Location | Size | Purpose |
|----------|------|---------|
| Home directory (`~`) | 1 TB system drive | Code, configs, environments |
| `/mnt/data` | 4 TB data drive | Datasets, model checkpoints, outputs |

### Accessing the Data Drive

In VSCode:
1. Click **File** > **Open Folder**
2. Enter `/mnt/data`
3. Click **OK**

Or from terminal:
```bash
cd /mnt/data
ls -la
```

## Best Practices

### Organize Your Data Drive

```
/mnt/data/
├── datasets/
│   ├── imagenet/
│   └── custom-dataset/
├── checkpoints/
│   └── experiment-001/
├── outputs/
│   └── results/
└── models/
    └── pretrained/
```

### Large File Transfers

For very large files or datasets, consider:

- **rsync over SSH**: For resumable transfers
  ```bash
  rsync -avz --progress user@ssh001.pandoro.today:/mnt/data/large-file.tar.gz ./
  ```

- **Cloud storage**: Upload to S3, GCS, or similar, then download locally
  ```bash
  # Example with AWS CLI (if installed)
  aws s3 cp /mnt/data/results.tar.gz s3://your-bucket/
  ```

### Save Checkpoints Regularly

Store model checkpoints on the data drive:

```python
# Example in PyTorch
torch.save(model.state_dict(), '/mnt/data/checkpoints/model_epoch_10.pt')
```

This protects your work and makes it easy to download later.

## Uploading Files

### Via VSCode

1. Open the File Explorer
2. Navigate to the destination folder
3. **Right-click** in the folder
4. Select **Upload**
5. Choose files from your local machine

### Via Drag and Drop

Some browsers support dragging files directly into the VSCode file explorer.
