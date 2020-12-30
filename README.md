# Simpledata
A blockchain system made by rdpstudio.

Note:

Now it didn't support parallel chain(P2P).


## What is a blockchain?

>A block chain is a transaction(Data) database shared by all nodes participating in a system based on the SimpleData protocol. A full copy of a currency(data)'s block chain contains every transaction(data) ever executed in the currency(data). With this information, one can find out how much value belonged to each address at any point in history. 


## How to run it

First, install ```requirements.txt```.

```
pip install -r requirements.txt
```

Then you have 2 options:

- Run ```backend.py``` to become a node and start mining
- Run ```data.py``` to become a user and send data (to send data you must run a node, in other words, you must run ```backend.py``` too)

> Important: DO NOT run it in the python IDLE, run it in your console. The ```backend.py``` uses parallel processing that doesn't work in the python IDLE.

## How this code work?

There are 2 main scripts:

- ```backend.py```
- ```data.py```

### Backend.py

This file is probably the most important. Running it will create a node (like a server). From here you can connect to the blockchain and process data (that other users send) by mining. As a reward for this work, you recieve some datas. The more nodes exist, the more secure the blockchain gets.

```backend.py``` has 2 processes running in parallel:

1. The first process takes care of mining, updating new blockchains and finding the proof of work.

2. The second process runs the flask server where peer nodes and users can connect to ask for the entire blockchain or sumbmit new data.

> Parallel processes don't run in python IDLE, so make sure you are running it from the console.

### data.py

This file is for those who don't want to be nodes but simple users. Running this file allows you to generate a new address, send datas and check your transaction history (keep in mind that if you are running this in a local server, you will need a "backend" to process your transaction).
When creating a data address, a new file will be generated with all your security credentials. You are supposed to keep it safe.


## Contribution

Anybody is welcome to collaborate in this project. Feel free to push any pull request (even if you are new to coding). See ```CONTRIBUTING.md``` to learn how to contribute.

Note: the idea of this project is to build a **really simple** blockchain system, so make sure all your code is easy to read (avoid too much code in 1 line) and don't introduce complex updates if they are not critical. In other words, keep it simple.
