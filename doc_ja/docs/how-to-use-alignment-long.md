# 長いフレーズに対するアライメント

指定した複数の長いフレーズについて、それぞれがどこまで発話されたかを判定する機能です。

サンプル実装は、`Plugins > WhisperRealtime > Sample > BP > Alignment_Long > BP_WhisperRealtimeAlignmentLongText`にあります。  
`Plugins > WhisperRealtime > Sample > Map > test_AlignmentLong`のマップでテストできます。

## 基本的なセットアップ
1. アクターBlueprintを作成します
2. `Whisper Realtime Alignment Short`コンポーネントを追加します
3. ニューラルネットワーク設定（Neural Net settings）と音声入力・スペクトル分析設定（Audio Input Spectrum Analysis settings）のデフォルト値を設定します:
	- 詳細は、[使い方 - 文字起こし](../how-to-use-transcript)ページを参照してください。
4. アライメント設定のデフォルト値を設定します:
	- 詳細は、[使い方 - 短いフレーズに対するアライメント](../how-to-use-alignment-short)ページを参照してください。
5. 長いフレーズに対するアライメント設定のデフォルト値を設定します:
	- `Min Token Length to Search`：発話されたかどうかを確認するトークンの数を指定します。
	- `Probability Threshold`：発話を判定するための確率の閾値の基準値を指定します。
		
		??? Question "閾値の算出式"
			bをこの値、pを無音入力時の各トークンの出現確率とすると

			    (1 - p) * b + p
			
			が最終的な閾値です。

	- `Max Skip at Beginning of Speech`：発話開始時に閾値以下のトークンをいくつスキップすることを許可するかを指定します。
	- `Max Skip during Speech`：発話中に閾値以下のトークンをいくつスキップすることを許可するかを指定します。

5. イベント「On Speaking」と「On Spoken」から結果を取得します。
	- これらのイベントは、`Alignment Long Result`の配列を提供します。配列の要素は、下記の3つの情報を保持します。
		- `Spoken history`: フレーズの発話済みの部分。
		- `Cursor`: フレーズのまだ発話されていない部分の最初のトークンのインデックス。
		- `Probabilities`: フレーズ内の各トークンが発話されたかどうかの確率。
	- `On Speaking`と`On Spoken`の違いは、[使い方 - 文字起こし](../how-to-use-transcript)ページを参照してください。

	??? Question "各フレーズに含まれるトークンや閾値の確認方法"
		`Get Alignment Targets`を呼び出すことで、`Whisper Alignment Long Target`の配列を取得できます。  
		この配列の各要素は、各フレーズのトークンIDなどの情報を格納しています。

![](images/BP-align-long-basic-setup.png){ loading=lazy }  

## 進行状況のリセット

全フレーズのアライメントの進行状況をリセットするには、`Reset Progress`関数を呼び出します。

## 設定の変更

- 長いフレーズに対するアライメント設定を変更するには、`Change Alignment Setting`関数を呼び出します。
- アライメント対象の文字列`Phrases to Align`を変更するには、`Set Phrases`関数を呼び出します。
- 音声入力・スペクトル分析設定を変更するには、`Change Spectrum Analysis Setting`関数を呼び出します。
- ニューラルネットワーク設定を変更するには、`Change Neural Net Setting`関数を呼び出します。

![](images/BP-align-long-change-setting.png){ loading=lazy }  
