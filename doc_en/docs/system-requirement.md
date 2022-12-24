# System Requirements

## Supported Unreal Engine version:

- 5.1

## Supported Platforms

| Platform                   | Development | Target Build |
| -------------------------- | ----------- | ------------ |
| Windows 64bit              | ✅          | ✅          |
| Ubuntu Desktop 64bit       |             |              | 
| Android                    |             |              |

!!! Question "Support for other platforms"
    Currently Windows is the only supported platform.  
    But we are willing to add support for Linux and Android in the future.

## Supported hardware acceleration 

| Platform                   | Default CPU | GPU DirectML | GPU CUDA | GPU TensorRT | NNAPI |
| -------------------------- | ----------- | ------------ | -------- |------------- | ----- |
| Windows 64bit              | ✅          |              | ✅      |              |       |
| Ubuntu Desktop 64bit       |             |              |          |              |       |
| Android                    |             |              |          |              |       |

<!-- - To use GPU acceleration with DirectML, a DirectX 12 capable GPU is required. -->
    
### CUDA and cuDNN

To use GPU acceleration with CUDA, a supported NVIDIA GPU is required and the following versions of CUDA and cuDNN are required to be installed. 

=== "Windows"

    - [CUDA: 11.6](https://developer.nvidia.com/cuda-11-6-0-download-archive?target_os=Windows&target_arch=x86_64&target_version=10)
    - [cuDNN: 8.5.0.96](https://developer.nvidia.com/compute/cudnn/secure/8.5.0/local_installers/11.7/cudnn-windows-x86_64-8.5.0.96_cuda11-archive.zip)

<!-- === "Linux"

    - CUDA: 11.6
    - cuDNN: 8.2.4 -->
