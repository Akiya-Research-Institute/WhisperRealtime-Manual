# Build package

To build a package using WhisperRealtime plugin, you need to configure the asset manager to include the machine learning model assets in the package.

## Asset manager settings

Add an element to `Project Settings > Game > Asset Manager > Primary Asset Types to Scan` and set the following values.  
(Or, since the default element with Index=1 is already set to `PrimaryAssetLabel`, you can edit this element.)

1. Set `Primary Asset Types` to `PrimaryAssetLabel`.
1. Set `Asset Base Class` to `PrimaryAssetLabel`.
1. Uncheck `Is Editor Only`.
1. Add an element to `Specific Assets` and specify `WhisperModel_all`.

![](images/Asset-manager-setting.png){ loading=lazy }

## Reduce package size

Package size can be reduced by packaging only a portion of the machine learning models used by the plugin.

- You can package only the specified model size by specifying the labels under `BySize` in `Plugins > WhisperRealtime > PrimaryAssetLabels` instead of `WhisperModel_all` in the [Asset manager settings](#asset-manager-settings) "4".

- Or, by specifying the labels under `ByFunctionAndLanguage`, you can package only models related to the specified function.

- Or, you can refer to the table below and manually specify only the models you need.

### Relationship between ML model assets and the functions that use them

#### English only models

|Asset name of ML model|Transcription|Short-phrase Alignment|Long-phrase Alignment|
|-|-|-|-|
|`encoder_mask_1500_0_{SIZE}_en_opt_fp16`[^1]|✅|✅|✅|
|`decoder_1_-1_16_{SIZE}_en_opt_fp16`[^2]|✅|||
|`aligner_b_n_{SIZE}_en_opt_fp16`||✅|✅|

[^1]: `{SIZE}` is `tiny`, `base`, `small`, or `medium`
[^2]: If the model size is Medium, `decoder_1_-1_8_medium_en_opt_fp16`

#### Multilingual models

|Asset name of ML model|Transcription|Short-phrase Alignment|Long-phrase Alignment|
|-|-|-|-|
|`encoder_mask_1500_0_{SIZE}_opt_fp16`|✅|✅|✅|
|`decoder_1_-1_16_{SIZE}_opt_fp16`[^3]|✅|||
|`aligner_b_n_{SIZE}_opt_fp16`||✅|✅|

[^3]: If the model size is Medium, `decoder_1_-1_8_medium_opt_fp16`