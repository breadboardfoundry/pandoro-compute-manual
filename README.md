# Pandoro Compute User Manual

Welcome to Pandoro, GPU infrastructure for research teams running ML experiments. This manual covers everything you need to get started with your dedicated compute instance.

## Quick Start

1. **[Getting Started](docs/getting-started.md)** - Login and authentication
2. **[Access Methods](docs/access-methods.md)** - Connect via browser-based SSH or VSCode
3. **[Using tmux](docs/tmux-guide.md)** - Keep processes running during disconnects
4. **[File Management](docs/file-management.md)** - Download and transfer files
5. **[Machine Specifications](docs/machine-specs.md)** - Hardware details and storage

## Your Machine at a Glance

| Component | Specification |
|-----------|---------------|
| GPU | NVIDIA RTX 6000 Pro Blackwell |
| CPU | AMD Ryzen 9900X (12 cores) |
| System RAM | 128 GB |
| System Drive | 1 TB |
| Data Drive | 4 TB (mounted at `/mnt/data`) |

## Access URLs

Your machine is assigned a number (e.g., `001`). Use these URLs to connect:

- **SSH in Browser**: `https://ssh001.pandoro.today/`
- **VSCode in Browser**: `https://code001.pandoro.today/`

Replace `001` with your assigned machine number.

## Support

Need help? Reach out to us:

- **Email**: pandoro@breadboardfoundry.com
- **Website**: [pandoro.today](https://www.pandoro.today/)
