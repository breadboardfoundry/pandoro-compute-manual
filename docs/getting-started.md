# Getting Started

This guide covers how to log in to your Pandoro compute instance.

## Authentication Methods

Pandoro supports two login methods:

### GitHub Login

1. Navigate to your access URL (SSH or VSCode)
2. Click **Sign in with GitHub**
3. Authorize Pandoro to verify your GitHub identity
4. You'll be connected to your machine

### One-Time Passcode via Email

1. Navigate to your access URL
2. Enter your registered email address
3. Check your inbox for a one-time passcode
4. Enter the passcode to complete login

The passcode expires after a short time. If it expires, request a new one.

## Your Dedicated Machine

Your Pandoro instance is a dedicated machine—it's entirely yours. You don't share resources with other users, and you have full control over the environment.

### Admin Access

You have administrator (sudo) access to install packages, configure services, and customize the system as needed. Your admin password is included in the welcome email from the Pandoro team.

Use sudo for administrative tasks:

```bash
# Install packages
sudo apt update
sudo apt install <package-name>

# Manage services
sudo systemctl status <service>
```

Keep your admin password secure and don't share it.

## Next Steps

- [Access Methods](access-methods.md) - Learn about SSH and VSCode browser interfaces
- [Machine Specifications](machine-specs.md) - Review your hardware details
