# Install NVIDIA GPU drivers

To use these snaps with an NVIDIA GPU, you require a working CUDA setup on the host machine.

The version of the driver and utilities might be different depending on your setup.
On Ubuntu Server 24.04 the following commands install the appropriate packages.

```
sudo apt update
sudo apt install nvidia-driver-550 nvidia-utils-550 nvidia-cuda-toolkit
sudo reboot
```
