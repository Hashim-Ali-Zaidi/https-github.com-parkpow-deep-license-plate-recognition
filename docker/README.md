# On-premise Automatic License Plate Recognition

Accurate, fast and easy to use API for license plate recognition. Trained on data from over 100 countries and regions around the world. The core of our license plate detection system is based on state of the art deep neural networks architectures. Our [On-Premise LPR SDK](https://platerecognizer.com/) lets you run license plate recognition **locally** (no internet connection needed).


<p align="center">
  <img src="../assets/demo.jpg">
</p>

- [Snapshot SDK](#snapshot-sdk)
- [Stream](#stream)

## Snapshot SDK

### Installation

* [Guided SDK installation](https://github.com/parkpow/deep-license-plate-recognition/blob/master/docker/installer.md)
* Manual instructions to [install the SDK](https://platerecognizer.com/sdk/) are also available.

### Interfacing with the SDK

Make sure that the Docker container is running. That's the last step of the [SDK installation](https://platerecognizer.com/sdk/).

For convenience let's start by downloading a vehicle image.

```
curl -o /tmp/car.jpg https://platerecognizer.com/static/demo.jpg
```

Now let's clone the repository and read that image.

```
git clone git@github.com:parkpow/deep-license-plate-recognition.git
pip install requests
python plate_recognition.py --sdk-url http://localhost:8080  /tmp/car.jpg
```

The script outputs the license plates found in the picture as a JSON object. Feel free to edit it to your needs. If you are running the container with a different port, you can use the `--sdk-url` to set a different address. For example `--sdk-url=http://localhost:8000`.

You may also read **more than one images** in a directory.

```
python plate_recognition.py  --sdk-url http://localhost:8080 /path/to/vehicle1.jpg /path/to/vehicle3.jpg /path/to/vehicle2.jpg
```

## Stream

Highly-accurate ALPR software that processes live camera or video feeds quickly & efficiently. Stream runs On-Premise on a variety of machines.

- [Guided installation](https://github.com/parkpow/deep-license-plate-recognition/blob/master/docker/installer.md)
- [Step by step installation](https://docs.google.com/document/d/1vLwyx4gQvv3gF_kQUvB5sLHoY0IlxV5b3gYUqR2wN1U/edit)

---
Have questions?  [Let us know](https://platerecognizer.com/contact) how we can help.

Provided by Plate Recognizer, a subsidiary of [ParkPow](https://parkpow.com/).
