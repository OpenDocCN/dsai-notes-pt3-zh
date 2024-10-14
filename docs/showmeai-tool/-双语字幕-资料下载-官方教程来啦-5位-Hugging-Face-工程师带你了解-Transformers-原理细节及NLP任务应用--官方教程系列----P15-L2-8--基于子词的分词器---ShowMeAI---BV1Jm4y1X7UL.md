# 【双语字幕+资料下载】官方教程来啦！5位 Hugging Face 工程师带你了解 Transformers 原理细节及NLP任务应用！＜官方教程系列＞ - P15：L2.8- 基于子词的分词器 - ShowMeAI - BV1Jm4y1X7UL

Let's take a look at subward based tokenization。Understanding why sub word based tokenization is interesting requires understanding the flaws of word based and character based tokenization。

If you haven't seen the first videos on word based and character based tokenization。

 we recommend you check them out before looking at this video。

Subward based tokenization lies in between characteror based and word based tokenization algorithms。

The idea is to find a middle ground between very large vocabularies。

 a large quantity of out of vocabulary tokens， and a loss of meaning across very similar words。

 for word based tokens and very long sequences as well as less meaningful individual tokens for character based tokenizers。

These algorithms rely on the following principle。Frequently used words should not be splin into smaller subwords。

 while rare words should be decomposed into meaningful subs。An example is the word dog。

 we would like to have our tokenizer to have a single ID for the word dog。

 rather than splitting it into characters DONG。However， when encountering the word dogs。

 we would like our tokenizer to understand that at the root。

 this is still the word dog with an added S that slightly changes the meaning while keeping the original idea。

Another example is a complex word like tokenization， which can be split into meaningful subwords。😊。

The root of the word is token， and Iization completes the root to give it a slightly different meaning。

😊，It makes sense to split the word into two token as the root of the word labeled as the start of the word andization as additional information labeled as a completion of the word。

In turn， the model will now be able to make sense of token in different situations。

It will understand that the words token， tokens， tokenizing and tokenizations have a similar meaning and are linked。

It will also understand that tokenization， modernization， and immunization。

 which all have the same suffixes， are probably used in these same syntactic situations。

Subword based tokenrs generally have a way to identify which tokens are a start of word and which tokens complete start of wordss。

So here token as the start of a word and hash hashization as completion of the word。

Here the hash hash prefix indicates that Iization is part of award word rather than the beginning of it。

😊，The hash hash comes from the bird tokenizer based on the word peace algorithm。

Other tokens use other prefixes which can be placed to indicate part of words like in here or start of words instead。

There are a lot of different algorithms that can be used for subway tokenization。

 and most models obtaining state of the art results in English today use some kind of subward tokenization algorithms。

These approaches help in reducing the vocabulary sizes by sharing information across different words。

 having the ability to have prefixes and suffixes understood as such。

They keep meaning across very similar words by recognizing similar tokens， making them up。



![](img/682dd3ed84761ab915a2a8c8a20c6be7_1.png)

![](img/682dd3ed84761ab915a2a8c8a20c6be7_2.png)

Yeah。