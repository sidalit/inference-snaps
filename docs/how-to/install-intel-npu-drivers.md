# Install Intel NPU drivers

If your system has an Intel NPU, and you want to make use of it, you need to install the user-space driver for it.
It is available as a snap:

```
sudo snap install intel-npu-driver
```

After you installed the AI model snap, connect the NPU driver to it:

```
sudo snap connect <ai-model>:npu-libs intel-npu-driver
``` 
