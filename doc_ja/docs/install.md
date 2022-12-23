# Installation

1. Purchase at [UE Marketplace](https://www.unrealengine.com/marketplace/product/d293a6a427c94831888ca0f47bc5939b) and install it.
2. Create an Unreal Engine project.
3. Open the project, open `Edit > Plugins` on the editor menu, enable `WhisperRealtime: Whisper-based Real-time Speech Recognition`, and restart the project.

<!-- !!! Warning "Install to Linux"
    Since the Epic Games Launcher is not provided for Linux, you need to copy the plugin manually from Windows.
    
    1. On Windows, install the plugin from Epic Games Launcher.
    2. On Linux, create a project.
    3. Copy the plugin from the UE4 plugin folder on Windows to the project directory on Linux.
        - Copy from: <*UE4 installation folder on Windows*\>\Engine\Plugins\Marketplace\WhisperBasedRealtimeSpeechRecognition
        - Copy to: <*directory containing the .uporject created on Linux*>/Plugins/WhisperBasedRealtimeSpeechRecognition
    4. Recreate the following symbolic links:
        - WhisperBasedRealtimeSpeechRecognition/Source/ThirdParty/onnxruntime-linux-1.13.1/lib
            - libnvonnxparser.so
            - libnvonnxparser.so.8 -->
