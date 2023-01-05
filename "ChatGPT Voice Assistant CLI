import requests
import json
import pyttsx3
import speech_recognition as sr

# Set the API endpoint URL
api_url = "https://api.chatgpt.com/response"

# Set the API key
api_key = "YOUR_API_KEY"

# Set the headers
headers = {
    "Content-Type": "application/json",
    "Authorization": f"Bearer {api_key}"
}

# Set the initial input text
input_text = "Hello, how are you today?"

while True:
    # Set the request data
    data = {
        "input": input_text
    }

    # Make the request
    response = requests.post(api_url, headers=headers, json=data)

    # Check the status code
    if response.status_code == 200:
        # Parse the response data
        response_data = response.json()
        
        # Print the response
        print(response_data["output"])
        
        # Pronounce the response in Siri voice
        engine = pyttsx3.init()
        voices = engine.getProperty('voices')
        engine.setProperty('voice', voices[4].id)  # change index to change voices (female is index 4)
        engine.say(response_data["output"])
        engine.runAndWait()
        
        # Get the user's response
        r = sr.Recognizer()
        with sr.Microphone() as source:
            print("Speak your response:")
            audio = r.listen(source)
        
        try:
            user_input = r.recognize_google(audio)
            print(f"You said: {user_input}")
        except Exception as e:
            print("Sorry, I couldn't understand you.")
            user_input = ""
        
        # Set the input text for the next iteration
        input_text = user_input
    else:
        # Print the error message
        print(f"Error {response.status_code}: {response.reason}")
        
        # Pronounce the error message in Siri voice
        engine = pyttsx3.init()
        voices = engine.getProperty('voices')
        engine.setProperty('voice', voices[4].id)  # change index to change voices (female is index 4)
        engine.say(f"Error {response.status_code}: {response.reason}")
        engine.runAndWait()
        
        break
