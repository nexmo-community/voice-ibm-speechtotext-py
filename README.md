# Example code for connecting a Nexmo Voice API call to IBM Watson via websockets

You can use this code as a base for doing real time transcription on a phone call using IBM Watsons Speech to Text API.

The Audio stream is sent over a websocket to your server and you then relay that on to the Watson websocket interface, Watson replies on the same connction with transcription responses.

