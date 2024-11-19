import speech_recognition as sr
import keyboard
import datetime
import gmaps
import requests

# Google Maps API setup
gmaps_key = "your_actual_api_key_here"
gmaps.configure(api_key=gmaps_key)

# Speech recognition function
def recognize_speech():
    recognizer = sr.Recognizer()

    with sr.Microphone() as source:
        print("Press '1' to start recording...")
        keyboard.wait("1")
        print("Recording...")

        audio = recognizer.listen(source)

        print("Press '0' to stop recording...")
        keyboard.wait("0")
        print("Stopped recording.")

        try:
            print("Recognizing...")
            text = recognizer.recognize_google(audio)
            print("You said:", text)

            # Keyword detection
            if "emergency" in text.lower():
                print("WARNING: Detected keyword 'emergency'")
                
            if "help" in text.lower():
                print("WARNING: Detected keyword 'help'")
            
            # Timestamp
            timestamp = datetime.datetime.now().strftime("%d-%m-%Y %H:%M:%S")
            print("Timestamp:", timestamp)
            
            # Location
            location = get_location()
            print("Location:", location)
            
        except sr.UnknownValueError:
            print("Could not understand audio")
        except sr.RequestError as e:
            print("Error with the request: {0}".format(e))
            
# Location retrieval function
def get_location():
    # Example address or place_id for location
    address = "ChIJbU60yXAWrjsR4E9-UejD3_g"

    # API URL with key
    geocoding_url = f"https://maps.googleapis.com/maps/api/geocode/json?place_id={address}&key={gmaps_key}"

    try:
        # Make request to Google Maps API
        response = requests.get(geocoding_url)
        data = response.json()

        if data['status'] == 'OK':
            result = data['results'][0]
            formatted_address = result['formatted_address']
            latitude = result['geometry']['location']['lat']
            longitude = result['geometry']['location']['lng']

            return f"Formatted Address: {formatted_address}, Latitude: {latitude}, Longitude: {longitude}"

    except Exception as e:
        print(f"Error getting location: {str(e)}")

    return "Bengaluru, Karnataka, India"

# Run the code
if __name__ == "__main__":
    recognize_speech()
