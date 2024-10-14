# 【双语字幕+资料下载】官方教程来啦！5位 Hugging Face 工程师带你了解 Transformers 原理细节及NLP任务应用！＜官方教程系列＞ - P13：L2.6- 基于词的分词器 - ShowMeAI - BV1Jm4y1X7UL

Yes。Let's take a look at word based tokenization。World based organization is the idea of splitting the raw text into words by splitting on spaces or other specific rules。Like punctuation。In this algorithm， each word has a specific number or ID attributed to it。

Here lets has VI 250， Du has 861 and tokenization followed by an exclamation mark has a 345。😊。This approach is interesting， as the model has representations that are based on entire words。The information held in a single number is high， as a word contains a lot of contextual and semantic information。However， this approach does have its limits。😊，For example。

 the word dog and the word dogs are very similar， and their meaning is close。The word based tokenization hall， however， will attribute entirely different ideas to these two words。 and the model will therefore learn two different embeddings for these two words。This is unfortunate。 as we would like the model to understand that these words are indeed related。

And that dogs is simply the plural form of the word dog。Another issue with this approach is that there are a lot of different words in an language。If we want our model to understand all possible sentences in that language。 then we will need to have an ID for each different word。And the total number of words。

 which is also known as the vocabulary size， can quickly become very large。This is an issue because each ID is mapped to a large vector that represents the words mean。And keeping track of these mappings requires an enormous number of weights。When the vocabulary size is very large。😊，If we want our models to stay lean。

 we can opt for our tokenizer to ignore certain words that we don't necessarily need。For example。 here， when training our tokenizer in text， we might want to take only the 10。000 most frequent words in that text， rather than taking all words from in that text or all language's words。To create our basic vocabulary。The tokenizer will know how to convert those 10。

000 words into numbers， but any other word will be converted to the out of vocabulary word。 or like shown here， the unknown word。Unfortunately， this is a compromise。 the model will have the exact same representation for all words that it doesn't know。😊。Which can result in a lot of lost information if many unknown words are present。



![](img/2d2fd0eb1726791600f98ab3dc5465fa_1.png)

![](img/2d2fd0eb1726791600f98ab3dc5465fa_2.png)

Yeah。