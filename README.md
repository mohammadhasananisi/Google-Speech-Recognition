SpeechRecognition installation
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

# recognize speech using Google Speech Recognition to persian
<pre>
import speech_recognition as sr

r = sr.Recognizer()
with sr.Microphone() as source:
	print("Say something!")
	audio = r.listen(source)

try:
	print("Google Speech Recognition thinks you said in English: -  " + r.recognize_google(audio, language = "en-US"))
	print("Google Speech Recognition thinks you said in Turkish: -  " + r.recognize_google(audio, language = "tr-TR"))
	print("Google Speech Recognition thinks you said in fa-IR: -  " + r.recognize_google(audio,language='fa-IR'))
except sr.UnknownValueError:
	print("Google Speech Recognition could not understand audio")
except sr.RequestError as e:
	print("Could not request results from Google Speech Recognition service; {0}".format(e))
</pre>
**if you want to use on other language just change this code  `r.recognize_google(audio, language = "en-US")`**


# If you had trouble installing, you couldn't install

**Keep it in a virtual environment**
To install 
On macOS and Linux:
<pre>
    python3 -m pip install --user virtualenv
</pre>
On Windows:
<pre>
    py -m pip install --user virtualenv
</pre>


To create a virtual environment, go to your project’s directory and run venv. If you are using Python 2, replace venv with virtualenv in the below commands.

**On macOS and Linux:**
<pre>
    python3 -m venv env
</pre>
**On Windows:**
<pre>
    py -m venv env
</pre>
The second argument is the location to create the virtual environment. Generally, you can just create this in your project and call it env.

venv will create a virtual Python installation in the env folder.

**On macOS and Linux:**
<pre>
    source env/bin/activate
</pre>

**On Windows:**
<pre>
    .\env\Scripts\activate
</pre>

if you 

If you do not understand, you can go to your home virtual environment from [here](https://packaging.python.org/guides/installing-using-pip-and-virtual-environments/)