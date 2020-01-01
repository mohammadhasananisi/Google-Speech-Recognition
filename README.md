# recognize speech using Google Speech Recognition to persian
SpeechRecognition
=================

Library for performing speech recognition, with support for several engines and APIs, online and offline.

Speech recognition engine/API support:

* `CMU Sphinx <http://cmusphinx.sourceforge.net/wiki/>`__ (works offline)
* Google Speech Recognition
* `Google Cloud Speech API <https://cloud.google.com/speech/>`__
* `Wit.ai <https://wit.ai/>`__
* `Microsoft Azure Speech <https://azure.microsoft.com/en-us/services/cognitive-services/speech/>`__
* `Microsoft Bing Voice Recognition (Deprecated) <https://www.microsoft.com/cognitive-services/en-us/speech-api>`__
* `Houndify API <https://houndify.com/>`__
* `IBM Speech to Text <http://www.ibm.com/smarterplanet/us/en/ibmwatson/developercloud/speech-to-text.html>`__
* `Snowboy Hotword Detection <https://snowboy.kitt.ai/>`__ (works offline)

**Quickstart:** ``pip install SpeechRecognition``. See the "Installing" section for more details.

To quickly try it out, run ``python -m speech_recognition`` after installing.

Project links:

-  `PyPI <https://pypi.python.org/pypi/SpeechRecognition/>`
-  `Source code <https://github.com/Uberi/speech_recognition>`
-  `Issue tracker <https://github.com/Uberi/speech_recognition/issues>`

# Use Persian

import speech_recognition as sr

r = sr.Recognizer()
with sr.Microphone() as source:
	print("Say something!")
	audio = r.listen(source)

try:
	# for testing purposes, we're just using the default API key
	# to use another API key, use `r.recognize_google(audio, key="GOOGLE_SPEECH_RECOGNITION_API_KEY")`
	# instead of `r.recognize_google(audio)`
	print("Google Speech Recognition thinks you said in English: -  " + r.recognize_google(audio, language = "en-US"))
	print("Google Speech Recognition thinks you said in Turkish: -  " + r.recognize_google(audio, language = "tr-TR"))
	print("Google Speech Recognition thinks you said in fa-IR: -  " + r.recognize_google(audio,language='fa-IR'))
except sr.UnknownValueError:
	print("Google Speech Recognition could not understand audio")
except sr.RequestError as e:
	print("Could not request results from Google Speech Recognition service; {0}".format(e))
    
** if you want to use on other language just change this code  r.recognize_google(audio, language = "en-US")  **