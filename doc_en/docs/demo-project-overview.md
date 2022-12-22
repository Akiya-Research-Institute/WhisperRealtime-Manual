# Realtime transcription demo

https://s3.ap-northeast-1.wasabisys.com/whisperrealtime/WhisperRealtimeDemo.zip

[Whisper-based Real-time Speech Recognition](https://www.unrealengine.com/marketplace/product/d293a6a427c94831888ca0f47bc5939b), or `WhisperRealtime` for short, is an Unreal Engine plugin for real-time speech-to-text transcription and translation with multi-language support, based on OpenAI's Whisper model.

Demo project is available on [GitHub](https://github.com/Akiya-Research-Institute/WhisperRealtime-Demo).

## System Requirements

- Windows 10 64bit
- Unreal Engine 5.1.0
- WhisperRealtime plugin v1.0.0 or above
- Microphone connected to your PC

If you want to run with GPU,

- CUDA: 11.6
- cuDNN: 8.5.0.96

## How to use the demo

1. Clone the repository: `git clone git@github.com:Akiya-Research-Institute/WhisperRealtime-Demo.git`
2. Open `WhisperRealtime-Demo/WhisperRealtimeDemo.uproject`
3. Click `Play` on UE editor.
4. Say something to your microphone.

## Options

![](images/demoOptions.png){ loading=lazy }  

- `Execution device`: Whether to use CPU or GPU.
- `Model Size`: The larger the model, the higher the accuracy and the greater the CPU/GPU/memory usage.
- `Language`: The language to be spoken.
- `Translate to English`: If you just want to transcribe speech to text in the language specified above, select `No`. If you want to translate it to English, select `Yes`.
- `Stop transcription`: Stops the transcription process.
