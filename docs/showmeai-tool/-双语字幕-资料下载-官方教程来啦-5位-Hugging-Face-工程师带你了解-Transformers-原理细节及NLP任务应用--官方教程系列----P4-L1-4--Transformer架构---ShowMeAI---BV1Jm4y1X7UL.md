# 【双语字幕+资料下载】官方教程来啦！5位 Hugging Face 工程师带你了解 Transformers 原理细节及NLP任务应用！＜官方教程系列＞ - P4：L1.4- Transformer架构 - ShowMeAI - BV1Jm4y1X7UL

Let's study the transformer architecture。This video is the introductory video to the encoders。 decoders and Ender decoder series of videos。In the series。 we'll try to understand what makes a transformer network and we'll try to explain it in simple high level terms。No advanced understanding of neural networks is necessary。

 but an understanding of basic vectors and tensors may help。To get started。 we'll take up this diagram from the original transformformer paper entitledAttention is all you need by Pawa it up。As we'll see here， we can leverage only some parts of it according to what we're trying to do。We want to dive into the specific layers， building up that architecture。

 but we'll try to understand the different ways this architecture can be used。Let's first start by splitting that architecture into two parts on the left。 you have the encoder and on the right， the decoder。These two can be used together。 but they can also be used independently。Let's understand how these work。

The encoder accepts inputs that represent text， it converts these text。 these words into numerical representations。These numerical representations can also be called embedding or features。We'll see that it uses the self attention mechanism as its main component。And we recommend you check out the video on encoders specifically to understand what is this numerical presentation as well as how it works。

😊，We'll study the self attention mechanism in more detail as well as its bidirectional properties。😊。The decoder is similar to the encode， it can also accept text inputs。It uses a similar mechanism as the encoder， which is the masked self attention as well。It differs from the encoder due to its unitite directional feature and is traditionally used in an autoregressive manner。

Here too， we recommend you check out the video on decoders。 especially to understand how all of this works。Combining the two parts results in what is known as an anchor decoder or a sequence to sequence transform。The encoder accepts inputs and computes a high level representation of those inputs。These outputs are then passed to the decoder。 The decoder uses the encoder's outputs alongside other inputs to generate a prediction。

And then predict an output， which is will reuse in future iterations， hence the term autoregressive。Finally， to get an understanding of encoder decoders as a whole。 we recommend you check out the video on encoder decoder。![](img/d08fc3568a2c2da170bab8fd128110ce_1.png)

![](img/d08fc3568a2c2da170bab8fd128110ce_2.png)

Yeah。