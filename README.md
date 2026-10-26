# sound-therapy

One Google Colab notebook, `sound_therapy.ipynb`, that generates a tone, mixes in an optional spoken affirmation, and writes a one-page PDF explaining the tone.

## Run it

1. Open `sound_therapy.ipynb` in Google Colab.
2. Set the options in the first cell (Settings).
3. Runtime > Run all. The WAV and PDF play in the notebook and download automatically.

The notebook also runs in Jupyter; there the files are saved next to the notebook.

## Options (first cell)

| Group | Options |
| --- | --- |
| Audio | duration, sample rate, master volume, fade; `TONE_MODE` `"tones"` (left, right, and center tones at chosen frequencies) or `"binaural"` (one carrier split between the ears to make a beat) |
| Voice | `VOICE` `"none"`, `"female"` (gTTS), or `"male"` (eSpeak NG); the text, how often it repeats, and its volume |
| PDF | on/off, title, the 528 Hz research notes and references, typeset equation images (Codecogs, needs internet) or text equations |
| Output | file name prefix, inline playback, auto-download in Colab |

## Presets

| What you want | Settings |
| --- | --- |
| Pure tone with the math PDF | `VOICE = "none"`, `INCLUDE_RESEARCH_NOTES = False` |
| 528 Hz with the female voice and the research PDF | `VOICE = "female"`, `INCLUDE_RESEARCH_NOTES = True`, `EQUATION_IMAGES = True` |
| 528 Hz with the male voice and the research PDF | `VOICE = "male"`, `INCLUDE_RESEARCH_NOTES = True`, `EQUATION_IMAGES = True` |
| WAV only | `MAKE_PDF = False` |

## Requirements

Colab has everything except `reportlab`, `gTTS`, and eSpeak NG, which the notebook installs when an option needs them. On a Mac you also need `ffmpeg` (used to decode the voice clip) and, for the male voice, eSpeak NG: `brew install ffmpeg espeak-ng`.

## Original notebooks

The `original` folder holds the three notebooks this one replaces: `tone-generator.ipynb`, `528_Hz.ipynb`, and `sound_therapy.ipynb`.
