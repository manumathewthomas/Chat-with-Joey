# Seq2Seq ChatBot: Chat with Joey!

## Introduction

Chat with Joey is a TensorFlow implementation of [A Neural Conversational Model](http://arxiv.org/abs/1506.05869) (aka the Google chatbot) with the help of [DeepQA repo](https://github.com/Conchylicultor/DeepQA). It make use of a [seq2seq model RNN](https://www.tensorflow.org/tutorials/seq2seq) for sentence predictions. The chatbot is designed to mimic the personality of Joey, a character from the tv-show "F.R.I.E.N.D.S" (more about this under dataset). 

![alt tag](https://github.com/manumathewthomas/Chat-with-Joey/blob/master/Results/Good.png)

#### Table of Contents

* [Installation](#installation)
* [Running](#running)
* [Dataset](#dataset)
* [Hyperparameters](#hyperparameter)
* [Results](#results)
* [Improvements](#improvements)
* [Credits](#credits)

## Installation

To run the project you will need:
 * python 3.5
 * tensorflow (v0.12)
 * django (1.10)
 * channels
 * Redis
 * asgi_redis (at least 1.0)
 * [CKPT FILE](https://uofi.box.com/shared/static/vm0sm79oh037eh2kood6tvnaq010f75h.zip)

## Running

Once you have all the depenedencies ready, do the folowing:

Extract the ckpt zip file, you will get a folder 'model-server' with the ckpt file and its associated files. Move this folder to /save. The server will look at the model present on save/model-server/model.ckpt

To configure the web app

```bash
export CHATBOT_SECRET_KEY="my-secret-key"
cd chatbot_website/
python manage.py makemigrations
python manage.py migrate
```

Then, to launch the server locally, use the following commands:

```bash
cd chatbot_website/
redis-server &  # Launch Redis in background
python manage.py runserver 0.0.0.0:8888
```
Go to the browser, if you are running it on a server then [ip-address]:8888, if you are on your local machine then localhost:8888

## Dataset
For this project we used the [Friends TV Corpus](https://sites.google.com/site/friendstvcorpus/), which was currated by David Ayliffe for his masters thesis to study inter-gender and intra-gender conversation. We formatted the data t get conversation between Joey(a character) and several other characters. There are two reasons for this 1) We were targetting sentence which are less than 5 words 2) Joey has the most conversations in the dataset

## Hyperparameters

## Results

## Improvements

## Credits
