# P56：L9.2 - 实体识别 - ShowMeAI - BV1YA411w7ym

![](img/5471faaaa9053b43ca3a5dfd2a8fa409_0.png)

Let's now introduce the task of named entity recognition。

Proper names are another important and anciently studied linguistic category。

While parts of speech are generally assigned to individual words or morphmes。

 a proper name is often an entire multiword phrase like the name Marie Curie。

 the location New York City， or the organization Stanford University。

Part of speech tagging can tell us that words like Marie or Stanford or Colorado are all proper nouns。

 being a proper noun is a grammatical property of these words。

But if viewed from a semantic perspective， these nouns refer to different kinds of entities。

 Marie Cury is a person。 Stanmford is an organization。 Colorado is a location。

 A named entity is roughly speaking。 Anything that can be referred to with a proper name。

 and Ford entity tags are most common。 person location， organization or geopolitical entity。 However。

 the term named entity is commonly extended to include things that aren't entities per se。

 including dates， Time， other kinds of temporal expressions。

 and even numeric expressions like prices。The task of named entity recognition is to find spans of text that constitute proper names and then to tag the type of the entity。

 Here's a text showing some sample N E R named entity recognition output。

 You'll see 13 mentions of named entities， including five organizations。 There's one。

 and there's one， and there's one， and four locations， two times one person and one mention of money。

Named entityity tagging is a useful first step in lots of natural language understanding tasks。

In sentiment analysis， we might want to know a consumer sentiment toward a particular entity。

Enities are our first useful stage in question answering。

 or for linking text to information and structured knowledge sources like Wikipedia hand named entity tagging is also central to natural language understanding tasks of building semantic representations。

Unlike part of speech tagging， where there is no segmentation problem since each word gets one tag。

The task of named entity recognition is to find and label spans of text and is difficult。

 partly because of the ambiguity of segmentation。 We need to decide what's an entity and what isn't and where the boundaries are。

 Indeed， most words in a text will not be named entities。

Another difficulty is caused by type ambiguity。 For example。

 the name Washington can refer to the educator Booker T。

 Washington or the sports team or a location or the geopolitical entity。

The standard approach to sequence labeling for span recognition problems like named entity recognition is called BIO tagging BIO tagging is a method that allows us to treat named entity recognition like a word by word sequence labeling task via tags that capture both the boundary and the named entity type。

Let's look at this following sentence， Jane Villainueva of United， a unit of United Airlines Hol。

 said the fair applies to the Chicago route with the following named entities。

Here we're showing the same sentence now vertically represented with BIO tagging。

Notice we have tags corresponding to people， organizations， and locations。

 and we have one tag per token。How does it work in BIO tagging。

 we label any token that begins a span of interest with the label B。

Tokens that occur inside a span with an eye and tokens outside of any span are labeled O。

 While there's only one O tag will have distinct B and I tags for each named entity class。

The number of tags is thus 2 n plus1 where ends the number of entity types。

And you can see we have a begin person， a begin organization， a begin location， an inside person。

 an inside organization， and just one O tag for everything else。

There are variants of BI O tagging in which there's no B tag， so that would be just I O labeling。

 So we just have inside one I tag for each named density type and then an O tag or more complicated label schemes in which we have a begin and an end tag。

As well as an inside tag， or we have a special singleton tag for named entities that are single words。

Like part of speech tagging， named entity recognition is done by supervised machine learning。

 where we have a human label training set in which some text is marked up with named entity tags。

We can use classic ML algorithms like Hs or CRFs or neural models like sequence models or large language models that are fine tuned。

We've now introduced the idea of named entity tagging an important first step in many NLP tasks。



![](img/5471faaaa9053b43ca3a5dfd2a8fa409_2.png)