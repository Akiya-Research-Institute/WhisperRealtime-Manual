# Modules

This plugin consists of the following 5 modules.

| Module | Description |
| ---- | ---- |
| Audio Input Spectrum Analysis | A module for audio capture and spectrum analysis. This module provides the Mel Log spectrum of microphone input which is then fed to the neutal network. |
| Byte level BPE Tokenizer | A module for the conversion between string and "tokens". "Tokens" are int arrays used for input and output of neural network. |
| Customized Onnx Runtime | A module for the execution of the neural network. While UE5 has an experimental Onnx Runtime module in its Neural Network Inference plugin with DirectML acceleration, this module provides the latest version of Onnx Runtime with CUDA acceleration. |
| Customized Onnx Runtime Editor | A module for defining UAsset of ONNX model. |
| Whisper Onnx Model | A module for the main implementation of speech-to-text feature. |

![](images/systemOverview.png){ loading=lazy }
