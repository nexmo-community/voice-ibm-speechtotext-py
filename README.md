# Example code for connecting a Nexmo Voice API call to IBM Watson via websockets

You can use this code as a base for doing real time transcription on a phone call using IBM Watsons Speech to Text API.

The Audio stream is sent over a websocket to your server and you then relay that on to the Watson websocket interface, Watson replies on the same connction with transcription responses.

## Running the example

To run this on your machine you'll need an up-to-date version of Python 2. Install dependencies with:

```bash
pip install --upgrade -r requirements.txt
```

You'll need to edit the `server.py` file to add in your own service credentials from watson and also specify the hostname where your machine is running, tools like ngrok are great for exposing your local machine to the internet.

By default the server runs on port 8000

You will also need to set the correct speech model, we reccomend for all phone calls you use Narrowband Audio.

Run the server like this:
```bash
python ./server.py 

```

## Linking to Nexmo 
You will need to create a new application with the Nexmo CLI and set the answer_url as http://[YOUR HOSTNAME]/ncco and the event_url as  http://[YOUR HOSTNAME]/event
The server will return an appropriate NCCO.
Link a number to your application and then when you call the number you will be connected throgh to Watson, simply start talking and you should see results printed to the console.


## Extending 
This example code simply prints the reponses from Watson to the console, however to integrate it with your own applicaiton you should extend the `on_watson_message` [function in server.py](https://github.com/nexmo-community/voice-watson-speechtotext/blob/master/server.py#L94)
