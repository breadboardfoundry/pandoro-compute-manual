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

## Uploading Files

### Via VSCode

1. Open the File Explorer
2. Navigate to the destination folder
3. **Right-click** in the folder
4. Select **Upload**
5. Choose files from your local machine

### Via Drag and Drop

Some browsers support dragging files directly into the VSCode file explorer.
