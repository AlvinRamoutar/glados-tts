# GLaDOS Text-to-speech (TTS) Voice Generator
Neural network based TTS Engine.

## Installation Instruction
If you want to install the TTS Engine on your machine, please follow the steps
below.

1. Install the required Python packages, e.g., by running `pip install -r
   requirements.txt`

I personally just ignored warnings about Torch since I'm not training the model.


## Running the Synthesizer
```
python3 engine.py
```

Default port is 8124
```
http://localhost:8124/synthesize/
```

Provide text after Synthesize.
Most modern browsers will encode whatever string you slap into the URL bar after `*/synthesize/`

e.g.:
```
http://127.0.0.1:8124/synthesize/This%20is%20a%20triumph.%20I'm%20making%20a%20note%20here:%20HUGE%20SUCCESS.
```

Streamed file is a .wav.


## Training (New Model)
The Tacotron and ForwardTacotron models were trained as multispeaker models on two datasets separated into three speakers. LJSpeech (13,100 lines), and then on the heavily modified version of the Ellen McClain dataset, separated into Portal 1 and 2 voices (with punctuation and corrections added manually). The lines from the end of Portal 1 after the cores get knocked off were counted as Portal 2 lines.


## Training (Old Model)
The initial, regular Tacotron model was trained first on LJSpeech, and then on a heavily modified version of the Ellen McClain dataset (all non-Portal 2 voice lines removed, punctuation added).

* The Forward Tacotron model was only trained on about 600 voice lines.
* The HiFiGAN model was generated through transfer learning from the sample.
* All models have been optimized and quantized.



