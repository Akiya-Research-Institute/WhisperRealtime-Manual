# モジュール構成

本プラグインは、以下の5つのモジュールで構成されています。

| Module | Description |
| ---- | ---- |
| Audio Input Spectrum Analysis | オーディオキャプチャとスペクトル解析のためのモジュールです。このモジュールは、マイクの入力波形をMel-Logスペクトログラムに変換し、ニュートラルネットワークに供給します。 |
| Byte level BPE Tokenizer | 文字列と「トークン」の変換を行うモジュールです。「トークン」は、ニューラルネットワークの入出力に使われるint型配列です。 |
| Customized Onnx Runtime | ニューラルネットワークを実行するためのモジュールです。UE5のNeural Network InferenceプラグインではDirectMLアクセラレーションによるOnnx Runtimeモジュール（ただしUE5.1時点でExperimental）がある中で、このモジュールが存在する理由はCUDAアクセラレーションによる最新バージョンのOnnx Runtimeを提供することです。 |
| Customized Onnx Runtime Editor | ONNXモデルのUAssetを定義するためのモジュールです。 |
| Whisper Onnx Model | 音声からテキストへの変換機能の主要な実装を担うモジュールです。 |

![](images/systemOverview.png){ loading=lazy }
