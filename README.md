# ChatGPT-vocal-assistant

This Python program accepts voice input from the user and interacts with a chat GPT API to generate responses. It uses the speech_recognition library to recognize speech from the user's microphone and convert it to text, and the pyttsx3 library to generate speech and pronounce the responses in Siri voice. It also uses the requests library to send requests to the API and receive responses.

The program starts by setting the API endpoint URL, API key, and headers, and initializing the input text. It then enters a loop in which it makes a request to the API with the current input text, receives a response, and pronounces the response in Siri voice. If the request is successful, it prompts the user to speak their response and recognizes it as text, then sets the input text for the next iteration. If the request is unsuccessful, it prints and pronounces the error message in Siri voice and exits the loop.

This program allows the user to have a conversation with the chat GPT API by speaking their responses and hearing the API's responses in Siri voice. It is useful for demonstrating how to interact with APIs using voice input and output.
