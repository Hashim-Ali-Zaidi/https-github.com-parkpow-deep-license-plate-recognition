# Webhooks

Plate Recognizer lets you forward the inference results to a third party. Here are examples for how to use our [webhook API](http://docs.platerecognizer.com/#webhooks).

## Starting the Webhook Server

Here are some webhook server examples. **Pick one** of the options below.

- __Python and the standard library:__

Start the server
```bash
python3 webhook_reader.py
```

- __Python and Flask:__

Install flask
```bash
pip install Flask==1.1.2
```
Start the server
```bash
export FLASK_APP=app.py
export FLASK_DEBUG=1
python3 -m flask run -h 0.0.0.0 -p 8001
```

- __Javascript / Node:__

Install dependencies
```bash
npm install
```
Start the server
```bash
node server.js
```

## Sending Data to the Webhook Server

1. Try the command below to check if the server is running correctly. Change car.jpg to a local file:
   - `curl -F 'json={"field": "value"}' -F 'upload=@car.jpg' http://localhost:8001/`

2. Find your machine local IP for example 192.1.0.206. You can use `ifconfig` to get it.
3. Configure the webhook on Platerecognizer.
   - In Stream, edit your `config.ini`, add the following to a camera: `webhook_target = http://MY_IP_ADDRESS:8001/`
   - For Snapshot, open [Webhooks Configuration](https://app.platerecognizer.com/accounts/webhooks/).
   
## Integrations

- [Connect Stream to Home Assistant](https://github.com/adamjernst/plate-handler). This project uses Stream webhooks to send license plate data to a home automation server. Form there, it will send a notification.
