# システム要件

## 対応するUnreal Engineのバージョン

- 5.1

## 対応プラットフォーム

| Platform                   | Development | Target Build |
| -------------------------- | ----------- | ------------ |
| Windows 64bit              | ✅          | ✅          |
| Ubuntu Desktop 64bit       |             |              | 
| Android                    |             |              |

現在、サポートされているプラットフォームはWindowsのみです。  
しかし、将来的にはLinuxやAndroidのサポートを追加していきたいと考えています。

## 対応するハードウェアアクセラレーション 

| Platform                   | Default CPU | GPU DirectML | GPU CUDA | GPU TensorRT | NNAPI |
| -------------------------- | ----------- | ------------ | -------- |------------- | ----- |
| Windows 64bit              | ✅          |              | ✅      |              |       |
| Ubuntu Desktop 64bit       |             |              |          |              |       |
| Android                    |             |              |          |              |       |

<!-- - To use GPU acceleration with DirectML, a DirectX 12 capable GPU is required. -->
    
### CUDAとcuDNN

CUDAによるGPUアクセラレーションを利用するには、対応するNVIDIA GPUが必要で、以下のバージョンのCUDAおよびcuDNNのインストールが必要です。

=== "Windows"

    - [CUDA: 11.6](https://developer.nvidia.com/cuda-11-6-0-download-archive?target_os=Windows&target_arch=x86_64&target_version=10)
    - [cuDNN: 8.5.0.96](https://developer.nvidia.com/compute/cudnn/secure/8.5.0/local_installers/11.7/cudnn-windows-x86_64-8.5.0.96_cuda11-archive.zip)

<!-- === "Linux"

    - CUDA: 11.6
    - cuDNN: 8.2.4 -->
