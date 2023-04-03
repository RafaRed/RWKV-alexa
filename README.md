# RWKV-alexa

Implementation of RWKV as a Alexa Skil.


1. Say "ask" followed by your question.
2. Get your response by RWKV.

# Install

## Server

1. Follow the instructions on https://github.com/RafaRed/RWKV-api to setup an API,
then follow the extras on the same repo to start jprq to get the SERVER_ADDRESS in the port 5000 without portfoward.

## Create - Alexa Skill

#### Create
1. Go to `https://developer.amazon.com/alexa/console/ask`
2. Click on `Create Skill`
3. Choose a name and locale and Next
4. Select `other`use the custom model, in the bottom, select `Alexa-hosted (Python)` and Next
5. Select `Start from scratch` and Next
6. Click on `Create Skill`

#### Choose a name
7. in `Invocations` select `Skill Invocation Name` and choose a name

#### QuestionIntent
8. in `Interaction Model` select `Intents` to create your first intent for recieve the questions
9. `+ Add Intent` write `QuestionIntent` and `Create custom intent`
10. in `Sample Utterances` add `ask {question}` accept the dialog box `Add`, and click in the `+` to add.
11. on the bottom you will see a field `question` in the slot type choose `AMAZON.SearchQuery`


#### ContinueIntent
12. Create your intent to input the password
13. `+ Add Intent` write `ContinueIntent` and `Create custom intent`
14. in `Sample Utterances` add `continue` and other words if you want to.

#### Save
15. On the top click in `Save Model` and `Build Model`

#### Change the Code
16. on the tab `code` replace the code on `lambda_function.py` for the code on the github with the same name
17. on the code, search for the two fields `SERVER_ADDRESS` and replace by your jprq SERVER_ADDRESS.
18. click on `SAVE` and `DEPLOY`

#### Testing
19. On the `Test` tab select `Development` on top
20. on the text box write Open and your choosen Skill Invocation Name
21. you should recieve the message `Hello, say ask and your question!`
22. you can ask anything using ask before the question `ask what is your name?`
23. you should recieve your answer.
24. by default, should be working on alexa, in the same email, just call the Skill invocation Name.


## Errors
Currently, I'm runnign this project in a rtx 3060 12gb. If you are getting "There was a problem with the requested skill's response." after waiting for a while, is because alexa can hold just for 8 secs. If the API is slower then that, will return this error.  

Solutions: 
- Reduce the number of words generated.
- Try a model with lower parameters;
- Try a faster strategy;
