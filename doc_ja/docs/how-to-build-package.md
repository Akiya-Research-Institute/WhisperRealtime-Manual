# パッケージのビルド

WhisperRealtimeプラグインを使用したプロジェクトをビルドしてパッケージを作成するには、機械学習モデルのアセットをパッケージに含むようにアセットマネージャーを設定する必要があります。

## アセットマネージャー設定方法

`Project Settings > Game > Asset Manager > Primary Asset Types to Scan`に要素を追加し、下記の値を設定します。  
または、デフォルトでIndex=1に既に`PrimaryAssetLabel`が設定されているので、この要素を編集してもOKです。

1. `Primary Asset Types`を`PrimaryAssetLabel`に設定します。
1. `Asset Base Class`を`PrimaryAssetLabel`に設定します。
1. `Is Editor Only`をオフにします。
1. `Specific Assets`に要素を追加し、`WhisperModel_all`を指定します。

![](images/Asset-manager-setting.png){ loading=lazy }

## パッケージサイズの縮小

WhisperRealtimeプラグインが使用する機械学習モデルの一部のみをパッケージすることで、パッケージサイズを縮小することができます。

- [アセットマネージャー設定](#_2)の4で、`WhisperModel_all`ではなく、`Plugins > WhisperRealtime > PrimaryAssetLabels`の`BySize`以下のラベルを指定することで、指定したモデルサイズのみをパッケージすることができます。

- または、`ByFunctionAndLanguage`以下のラベルを指定することで、指定した機能に関するモデルのみをパッケージすることができます。

- または、下記のテーブルを参照し、必要なモデルのみを手動で指定することができます。

### 機械学習モデルのアセットとそれを利用する機能の関係

#### 英語のみのモデル

|Asset name of ML model|Transcription|Short-phrase Alignment|Long-phrase Alignment|
|-|-|-|-|
|`encoder_mask_1500_0_{SIZE}_en_opt_fp16`[^1]|✅|✅|✅|
|`decoder_1_-1_16_{SIZE}_en_opt_fp16`[^2]|✅|||
|`aligner_b_n_{SIZE}_en_opt_fp16`||✅|✅|

[^1]: `{SIZE}`は、`tiny`, `base`, `small`, `medium`
[^2]: モデルサイズがMediumの場合は、`decoder_1_-1_8_medium_en_opt_fp16`

#### 多言語対応モデル

|Asset name of ML model|Transcription|Short-phrase Alignment|Long-phrase Alignment|
|-|-|-|-|
|`encoder_mask_1500_0_{SIZE}_opt_fp16`|✅|✅|✅|
|`decoder_1_-1_16_{SIZE}_opt_fp16`[^3]|✅|||
|`aligner_b_n_{SIZE}_opt_fp16`||✅|✅|

[^3]: モデルサイズがMediumの場合は、`decoder_1_-1_8_medium_opt_fp16`