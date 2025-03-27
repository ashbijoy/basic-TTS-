# Text-to-Speech (TTS) Model Using pyttsx3

## Overview
This is a simple Python-based Text-to-Speech (TTS) script that uses the `pyttsx3` library to convert text into speech. The script runs locally without requiring an internet connection and supports voice customization.

## Features
- Uses `pyttsx3`, a text-to-speech conversion library.
- Works offline without any external API.
- Adjustable speech rate, volume, and voice selection.

## Requirements
- Python 3 installed
- `pyttsx3` library installed

## Installation
To install the required library, run:
```bash
pip install pyttsx3
```

## Usage
To run the script, simply execute the following command in the terminal:

```bash
python tts.py
```

### Example Script (`tts.py`)
```python
import pyttsx3

def text_to_speech(text):
    # Initialize the TTS engine
    engine = pyttsx3.init()
    
    # Set properties (optional)
    engine.setProperty('rate', 150)    # Speed of speech (words per minute)
    engine.setProperty('volume', 0.9)  # Volume (0.0 to 1.0)
    
    # Optional: Change voice (depends on system voices available)
    voices = engine.getProperty('voices')
    engine.setProperty('voice', voices[14].id)  # voices[0] for male, voices[1] for female (if available)
    
    # Convert text to speech
    engine.say(text)
    engine.runAndWait()

# Example usage
if __name__ == "__main__":
    sample_text = "Hello, My name is Ash. This is a test of the text to speech system. This group consists of Ashwin Bijoy, Reethika Shree and Nivya Raju. They belong to the Data Science Department. Thank You for listening to me"
    text_to_speech(sample_text)
```

## Customization
### Change Speech Rate
Modify the `rate` property to adjust the speech speed:
```python
engine.setProperty('rate', 180)  # Increase speed
engine.setProperty('rate', 120)  # Decrease speed
```

### Change Volume
Set the volume between `0.0` (mute) and `1.0` (max):
```python
engine.setProperty('volume', 0.7)  # Lower volume
```

### Change Voice
List available voices:
```python
voices = engine.getProperty('voices')
for index, voice in enumerate(voices):
    print(f"{index}: {voice.name} ({voice.id})")
```
Set a specific voice:
```python
engine.setProperty('voice', voices[0].id)  # Select a different voice
```

## License
This project is open-source and free to use.


