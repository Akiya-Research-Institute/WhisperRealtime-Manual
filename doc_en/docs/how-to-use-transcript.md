# Transcription

See `Plugins > WhisperRealtime > Sample > BP > Transcript > BP_WhisperTranscriptRealtime` for a sample implementation.  
You can test it in sample map located at `Plugins > WhisperRealtime > Sample > Map > test_Transcript`.

## Basic setup 

1. Create an actor blueprint.
2. Add `Whisper Realtime Transcript` component.
3. Set the default Neural Net settings:
	- Specify `Model Size`. The larger the model, higher the accuracy and the CPU/GPU/memory usage.

		??? Question "Where is Large model?"
			The official implementation of Whisper offers "Large" as the largest model size, but this plugin does not include the Large model.  
			This is because it is too large for game use and could not be made to work properly in the plugin developer's environment.

	- Specify `Execution device`, whether to use CPU or GPU.
	- Specify `GPU Device ID` if you use GPU and you have multiple GPUs in your PC.
	- Specify `Language spoken`.
	- Specify `Do Translate to English`. If you just want to transcribe speech to text in the language specified above, leave unchecked.

3. Set the default Audio Input Spectrum Analysis settings:
	- Specify `Silence Volume Threshold`, volume threshold for determining silence.  
		Maximum microphone input is 1.0. Complete silence is 0.0.
	- Specify `Silence Duration Threshold`, time threshold for determining silent state (in seconds).  
		If the volume below `Silence Volume Threshold` continues for this time, a transition is made from the speech state to the silent state.
	- Specify `Speaking Duration Threshold`, Time threshold for determining speaking state (in seconds).  
		If the volume above `Silence Volume Threshold` continues for this time, a transition is made from the silent state to the speech state.

4. Set the default transcript settings:
	- Specify `Prohibited Phrases` if you want to suppress certain phrases.
	    - Note that this feature simply removes the specified phrases from the result. If you specify a short phrase, for example `at`, the phrase will be removed from all words (e.g. `that` becomes `th`).

5. Get results from `On Speaking` event and `On Spoken` event.

	- `On Speaking` event gives intermidiate result while the user is still speaking.
	- `On Spoken` event gives the final result after the user stops speaking.

	!!! Warning
		Note that the end of the `On Speaking` result tends to be incorrect because the speech is abruptly cut off in the middle of the speech.

	!!! Info
		The values for Audio Input Spectrum Analysis settings are used to determine user is speaking or not.

    ![](images/BP-transcript-basic-setup.png){ loading=lazy }  

## Change settings

- To change Audio Input Spectrum Analysis settings, call `Change Spectrum Analysis Setting` function.
- To change Neural Net settings, call `Change Neural Net Setting` function.

	![](images/BP-transcript-change-setting.png){ loading=lazy }  

## Stop and restart

- To stop transcription or translation, call `Stop Mic Input` function.
- To restart transcription or translation, call `Restart Mic Input` function.
