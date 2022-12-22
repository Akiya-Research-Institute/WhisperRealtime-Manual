# Transcription

See `Plugins > WhisperRealtime > Sample > BP > Transcript > BP_WhisperTranscriptRealtime` for a sample implementation.  
You can test it in sample map located at `Plugins > WhisperRealtime > Sample > Map > test_Transcript`.

## Basic setup 

1. Create an actor blueprint.
2. Add `Whisper Realtime Transcript` component.
3. Set the default Neural Net settings:
	- Specify `Model Size`. The larger the model, higher the accuracy and the CPU/GPU/memory usage.
	- Specify `Execution device`, whether to use CPU or GPU.
	- Specify `GPU Device ID` if you use GPU and you have multiple GPUs in your PC.
	- Specify `Language spoken`.
	- Specify `Do Translate to English`. If you just want to transcribe speech to text in the language specified above, leave unchecked.
4. Set the default transcript settings:
	- Specify `Prohibited Phrases` if you want to suppress certain phrases.
	    - Note that this feature simply removes the specified phrases from the result. If you specify a short phrase, for example `at`, the phrase will be removed from all words (e.g. `that` becomes `th`).
5. Get results from `On Speaking` event and `On Spoken` event.
	- `On Speaking` event gives intermidiate result while the user is still speaking.
	- `On Spoken` event gives the final result after the user stops speaking.

    ![](images/BP-transcript-basic-setup.png){ loading=lazy }  

## Stop and restart

6. To stop transcription or translation, call `Stop Mic Input` function.
7. To restart transcription or translation, call `Restart Mic Input` function.

## Change settings

8. To change Neural Net settings, call `Change Neural Net Setting` function.

    ![](images/BP-transcript-change-setting.png){ loading=lazy }  
