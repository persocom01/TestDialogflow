# TestDialogflow

A Dialogflow testing playground.

# Setup

Dialogflow is a google service that can be found at https://dialogflow.cloud.google.com/

The steps here detail how to create a chatbot using Dialogflow.

1. Create an agent.
Select create agent from the left panel. Give it an appropriate name, such as "pizza takeaway".

2. Intents.
There are two default intents in an agent, welcome and fallback. The former is how the chatbot introduces itself, the latter is what the chatbot says when it doesn't understand the question. Click create intent and name it "order pizza".

3. Enter training phrases.
These are what you typically expect a customer to say when ordering pizza.
```
One extra large Hawaiian with extra cheese please.
Can I have a pizza delivered to my home at 5pm?
I'll like to order a pizza.
```
The system automatically identifies certain entities, such as $time. You may assign any words in the phrases to entities by highlighting them.

4. Enter responses.
```
Your $pizzaType pizza will be delivered to $address at $time.
```
The dollar sign indicates the entities from the training phrases inserted into the response.

5. Enter action and parameters.
Here you can enter what entities you need the user to provide, such as time, as well as the question the chatbot will ask the user when it is missing said entities. They call this slot filling. Check the @sys.time entity and set the prompt to:
```
What time do you want your pizza delivered?
```

6. Click integrations.
Enable webdemo.

7. Click entities.
Add entities you wish to identify from input text here. In this case, we will enter "pizzaType" and under edit entries, add:
```
hawaiian
pepperoni
supreme
```
We can now set training phrases to identify these entities as well as new action prompts if they are not given by the user.
