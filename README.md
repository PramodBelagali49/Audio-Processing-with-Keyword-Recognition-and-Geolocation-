# Audio Keyword Detection and Location Retrieval
This project allows users to detect specific keywords from spoken audio input and retrieve the current location using Google Maps API. It demonstrates how to use Python for speech recognition, keyword detection, and geolocation.

<h2>Features</h2> 
<p>
Audio Recognition: Recognizes spoken words using a microphone.<br>
Keyword Detection: Checks for specific keywords (e.g., "emergency" and "help") in the audio input.<br>
Timestamp Logging: Logs a timestamp each time a phrase is recognized.<br>
Location Retrieval: Uses Google Maps API to fetch and display the location when keywords are detected.<br>
</p>

<h2>Requirements</h2> 
<p>
To run this code, you need the following Python libraries:<br>
SpeechRecognition: For capturing and transcribing audio input.<br>
keyboard: To control the start and stop of recording with key presses.<br>
gmaps: For Google Maps API integration.<br>
requests: To make HTTP requests to Google Maps API.<br>
</p>

<h2>Installation</h2> 

Install the required packages by running:
pip install SpeechRecognition keyboard requests gmaps

Install PyAudio for audio input (especially on Windows):
<p style="background-color: #f5f5f5; border: 1px solid #ddd; padding: 10px; border-radius: 5px; font-family: monospace; font-size: 1em; color: #333;">
    pip install pyaudio
</p>


Add your Google Maps API Key in the code:
<p style="background-color: #f5f5f5; border: 1px solid #ddd; padding: 10px; border-radius: 5px; font-family: monospace; font-size: 1em; color: #333;">
gmaps_key = "YOUR_GOOGLE_MAPS_API_KEY"<br>
</p>


<h2>Usage</h2>
To start the program:
Run the script in your terminal or VS Code:<br>
Follow the on-screen prompts:
<br><br>
<ol>
 <li> Press "1" to begin recording your audio.</li>
 <li>Speak into the microphone.</li>
 <li>Press "0" to stop recording.</li>
</ol>

If a recognized phrase contains the keywords "emergency" or "help," the program will log a warning, add a timestamp, and retrieve your location using the Google Maps API.

<h2>Code Overview </h2>


![Image description](https://github.com/user-attachments/assets/020119c3-1b94-4e20-a732-03d1ff2b4ef3)

