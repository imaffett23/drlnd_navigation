[//]: # (Image References)

[image1]: https://user-images.githubusercontent.com/10624937/42135619-d90f2f28-7d12-11e8-8823-82b970a54d7e.gif "Trained Agent"

# Project 1: Navigation

### Project Details

This repository contains the work needed to submit for the Navigation project of Udacity's Deep Reinforcement Learning Nanodegree.  The project is based on the Banana Collector environment. 

![Trained Agent][image1]

A reward of +1 is provided for collecting a yellow banana, and a reward of -1 is provided for collecting a blue banana.  Thus, the goal of your agent is to collect as many yellow bananas as possible while avoiding blue bananas.  

The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around agent's forward direction.  Given this information, the agent has to learn how to best select actions.  Four discrete actions are available, corresponding to:
- **`0`** - move forward.
- **`1`** - move backward.
- **`2`** - turn left.
- **`3`** - turn right.

The task is episodic, and in order to solve the environment, your agent must get an average score of +13 over 100 consecutive episodes.

### Getting Started

1. Download the project environment from one of the links below.  You need only select the environment that matches your operating system:
    - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux.zip)
    - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana.app.zip)
    - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86.zip)
    - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86_64.zip)
    
    (_For Windows users_) Check out [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

    (_For AWS_) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux_NoVis.zip) to obtain the environment. 

1. Place the downloaded file in the project repository, in a folder named `data/`, and unzip (or decompress) the file.

1. Python dependencies are given in the folder `python/`.  Running `pip -q install ./python` will trigger `setup.py`, which installs unityagents and other dependencies given in the `requirements.txt` file.

### Instructions

In order to train the agent and save the model weights, one can execute the `Navigation.ipynb` file.  Specifically:

1. The first section **"Start the Environment"** has executable cells which will: install dependencies by triggering `python/setup.py`, set up the Banana Collector Unity environment, and setup the default brain for the environment
1. The second section **"Examine the State and Action Spaces"** has executable cells which will define our action and state sizes to be used later in our Agent.
1. The third section **"Take Random Actions in the Environment"** is simply to demonstrate how we use python to control the agent.  It is completely random however and does not contribute to our final solution.
1. The fourth section **"It's Your Turn"** has executable cells that define our DQN agent and run the training.  More specifically, this section:
    - Imports the packages needed to run our agent for the Banana Collector environment
    - Sets up hyperparameters used in the agent
    - Defines our basic Q-Network as a dense neural network with ReLU activation
    - Defines our Agent class which acts and learns upon the environment
    - Defines a replay buffer which stores previous experiences for sampling in the learning process
    - Trains and saves a model which solves the problem after earning an average score greater than or equal to 13 over 100 episodes