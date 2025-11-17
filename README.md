 💬 Vavo – Python Voice Assistant

A fully functional **Python-based voice assistant** capable of recognizing speech, responding with text-to-speech, performing web searches, opening applications, retrieving time, providing conversational replies, and more.

This project uses **SpeechRecognition**, **Google Text-to-Speech (gTTS)**, **playsound**, **OpenCV**, and other Python modules to create a lightweight but effective personal assistant named **Vavo – Virtual Assistance Version One**.


🌟 Features

 🎤 Speech Recognition

* Listens using your system microphone.
* Converts speech to text with Google Speech Recognition.

 🗣️ Text-to-Speech Responses

* Responds using Google Text-to-Speech (gTTS).
* Automatically generates and deletes temporary audio files.

🌐 Web Actions

* Google search
* Wikipedia search
* Open YouTube
* Open Gmail
* Open Google Maps with custom location

⏰ Utility Functions

* Tell the current time
* Shutdown the system using command

🤝 Conversational Abilities

* Greetings
* Introducing itself
* Asking your name
* Responding to mood queries
* Saying thanks and goodbye


## ▶️ Running the Assistant

Run the script:

```bash
python vavo_assistant.py
```

You will see:

```
>> listening...
```

Speak commands such as:

* "hello"
* "what is the time"
* "search google"
* "open youtube"
* "shutdown system"
* "what is your name"
* "where are you created"
* "search youtube"
* "exit"

---

## 🧠 How the Code Works (Detailed Explanation)

### 🔹 1. **Speech Recognition**

```python
audio = r.listen(source)
voice_data = r.recognize_google(audio)
```

The assistant continuously listens and converts audio to text.

---

### 🔹 2. **Command Detection (there_exists function)**

```python
def there_exists(terms):
    for term in terms:
        if term in voice_data:
            return True
```

This checks if user speech contains any keyword.

---

### 🔹 3. **Responding to User Queries**

The `respond()` function contains all logic:

Example:

```python
if there_exists(["hello", "hi"]):
    speak("hey, what's up?")
```

Every voice command triggers a specific action.

---

### 🔹 4. **Text-to-Speech Output**

Using Google Text-to-Speech:

```python
tts = gTTS(text=audio_string, lang='en-in')
playsound.playsound(audio_file)
```

Temporary MP3 files are generated and removed instantly.

---

### 🔹 5. **Web Searches**

Example: Google search

```python
url = 'https://google.com/search?q=' + search
webbrowser.get().open(url)
```

---

### 🔹 6. **System Shutdown**

```python
os.system("shutdown /s /t 30")
```

---

### 🔹 7. **Infinite Listening Loop**

```python
while(1):
    voice_data = record_audio()
    respond(voice_data)
```

Assistant keeps listening unless user says “exit”.

---

## 📦 Dependencies (requirements.txt)

```
SpeechRecognition
playsound
gTTS
opencv-python
PyAudio
```

---
