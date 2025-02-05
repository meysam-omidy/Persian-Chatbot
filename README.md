## Overview
This repository contains the implementation of a persian banking chatbot which is aimed at efficiently handling user intents and slots in the Persian language. It leverages state-of-the-art machine learning techniques and models, such as the BERT-based ParsBERT, to ensure high accuracy in understanding and responding to user queries.

## Key Features
- **Intent Recognition**: Accurate identification of user intents with over 90% confidence.
- **Slot Filling**: Efficient extraction and processing of user-provided slots to enhance interaction quality.
- **Multiturn Interaction**: Well suited questions to recognize intent and extract slots for proper interaction with user.
- **Scalable Architecture**: Designed to handle large datasets and complex interactions, ensuring reliability and scalability.

## Requirements
To run the code, ensure you have the following dependencies installed:
- Python 3.x
- NumPy
- Transformers
- PyTorch

## Brief Training Strategy
Training was done using data from Novin Kish Informatic Services Corporation, around 2000 data for train and 200 data for validation, each containing a json object with a user request, its slots and its intent. Base model for intent detection and slot filling is pretrained parsbert model. Training was done in two phases; In first phase, model was trained on the main dataset for 20 epochs and in second phase, additional data was generated with only direct intent specification adn slots specification user prompts in 5 epochs. Finally, average 90 percent validation f1 score on both intent detection and slot filling was achieved.

## Brief Explanation Of How Chatbot Operates
For its first task, chatbot needs to identify user's intent, and it happens by asking what your intent is or did you mean the specified task until it can extract intent with more than 90 percent accuracy. Next, chatbots begins asking user to input missing slots one slot at a time, and it changes the required slot name after extracting it with more than 80 percent accuracy, by asking input slot or is the value of slot the value you input. it can also extract other slots while extracing another slot if its value could be extracted with more than 80 percent accuracy. Finally, it outputs a json object containing user's intent along with values of required slots. 

## Usage
1. Download pretrained model weights along with the saved files. All files and pretrained weights are all uploaded to a google drive, for accessing it, just send me an email.
2. Run chatbot.ipynb for chatting with the chatbot

## Results
Some sample chats along with their results are included in the results folder. 
