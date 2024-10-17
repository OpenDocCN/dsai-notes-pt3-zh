# P63：L11.1 - 聊天机器人与对话系统介绍 - ShowMeAI - BV1YA411w7ym

![](img/82f55a32978302a19af77f1391f6ac65_0.png)

In this series of lectures， we explore chatbots and dialogue systems。



![](img/82f55a32978302a19af77f1391f6ac65_2.png)

Conversational agents， also called dialogue systems， dialogue agents， chatbots。

 are systems designed to interact with humans via conversation， either in text or speech。

These include personal assistance on phones or other devices like Siri or Alexa Corana。

 the Google assistantsistant， and tools for simple。

 relatively short interactions like playing music or setting timers or clocks or keeping shopping lists。

 all the way to longer conversations maybe be just for fun or for practical applications like booking travel reservations。

 or even in clinical uses for mental health。We'll talk in these lectures about two broad categories of conversational agents。

Chat bots are systems that carry on extended conversations with the goal of mimicking the unstructured conversations or chats characteristic of informal human human interactions。

Mostly， these have been designed for fun。Yet starting from the very first system。

 Weiseizenbaum's Eliza。Chatbots have also been used for practical purposes。

 involving psychological counseling。The second kind of system are goal based dialogue agents used to solve some task like booking a flight or maintaining a shopping list。

Sometimes you'll see the word chatbot used for both types of systems。

 but we'll try to distinguish them in these lectures。

Like practically everything else in language processing。

 chat bot architectures fall into two classes， Rule based systems and corpus based systems。

 Rule based systems include the early influential Eliza and Perry systems。

Corpus based systems mine large data sets of human human conversations。

 which can be done by using information retrieval to copy a human response from a previous conversation or using an encoder decoder system to generate a response from a user utterance。



![](img/82f55a32978302a19af77f1391f6ac65_4.png)

These chatbot systems often have an entertainment value， such as Facebook's blenderbot。

 a neural chatbot that carries on conversations of this type。 The user says， will you sing me a song。

 And the chatbot says， sure， what do you want to be sung to， I can send you a song about baking。 Yes。

 singing me a song about baking and so on。😊。

![](img/82f55a32978302a19af77f1391f6ac65_6.png)

Or Microsoft's Shaai system chats with people in Chinese on text messaging platforms。

 responding mainly by extracting turns that humans have said in past conversations。

Other dialogue agents are built to solve a task like setting a timer， making a travel reservations。

 playing a song。These tend to be built around a knowledge structure called the frame。

A frame represents the user's intention for the task then consists of a collection of slots。

 each of which can take a set of possible values， so an airline booking agent might have slots like the destination city or the departure time。



![](img/82f55a32978302a19af77f1391f6ac65_8.png)

This has been a quick preview of the two classes of dialogue agents。

 chatbots and task based dialogue systems。