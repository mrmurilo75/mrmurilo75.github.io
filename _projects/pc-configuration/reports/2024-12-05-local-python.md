---
title: Local Python Development
layout: post
---

On debian-based systems, python development setup is not built-in. To configure it, run the following commands:

```bash
# Install Libraries, PyPi Package Manager, and Virtual Environment
sudo apt install -y python3-dev python3-pip python3-venv

# Install improved python terminal (optional)
sudo apt install -y ipython3

# Create alias
echo -e '\nalias python=python3\n' >> $HOME/.bashrc
```
