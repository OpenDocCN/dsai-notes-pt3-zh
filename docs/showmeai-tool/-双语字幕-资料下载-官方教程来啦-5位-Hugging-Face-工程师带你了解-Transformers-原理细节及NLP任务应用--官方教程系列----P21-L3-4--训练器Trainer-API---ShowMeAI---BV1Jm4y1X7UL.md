# 【双语字幕+资料下载】官方教程来啦！5位 Hugging Face 工程师带你了解 Transformers 原理细节及NLP任务应用！＜官方教程系列＞ - P21：L3.4- 训练器Trainer API - ShowMeAI - BV1Jm4y1X7UL

Saattrino EPA。So Transforms library provides a Traer API that allows you to easily fine tune transformformal models on your data set。So train your class， take sure that that sets your model， as well as the training IP parameters。And can perform the training on any kind of setup， CPU， GPU， multiple GPUus， TUus。Can also compute the predictions on any dataset set， and if you provided matrix。

 evaluate your model on any dataset set。You can also install final data processing such as dynamic padding as long as you provide a tokenizer or given data coulator。Roll drive API in the MRRPC data set， since it's relatively small and easy to prepoces。

As we saw in the dataset sets of a view video， or we can proposepo it。You do not apply padding during the preprosing， as we will use dynamic padding before data aulator with padding。Note that we don't do the final steps of renaming removing ins， or set the format to torch tensils。So trainer will do all of this automatically for us by analyzing the model signature。

The last step before creating the trainer are to define a model and some training ups。We saw to do the first in the model API video。For the second。 we use the training argument class it only takes a path to a folder door where results and checkpoint will be saved。 but you can also customize all the app parameters your trainer will use learning grade。

 number of training as， etc。It's been very easy to create a trainer and launch a training。This should display your progress bar and after a few minutes if you're running on a GPU。 you should have the training finished。The result will be however antiticlimatic or however。 as you will only get a training class which doesn't really tell you anything about how well your model is performing。

This is because we didn't specify any metric for the evaluation。To get this matrix。 we'll first cover the predictions on the wall evaluation set using the Preic method。It returns a name to poll with three fields prediction， which contains the model predictions。 label Is， which contains the label if you at that them， and matrix， which is empty here。

 we're trying to do that。The predictions are the looks of the models for all the sentences in the dataset set。 so an by array of shape 48 by 2。To match them with our labels。 we need to take the maximum look for each prediction to know which of the two classes was predicted。We do this with the a max function。Then we can use the matrix from the dataset library。

 it can be loaded as easily as a dataset set with a load metric function。 and it returns the evaluation metric used for the dataset。We can see our model did learn something as it is 85。7% accurate。To monitor the evaluation matrix during 20， we need to define a compute matrix function but does the same step as before。

It takes a name to poll with predictions on labels and must return a dictionary with the metrics we want to keep track of。By passing the epoch evaluation strategy to our training arguments。 we tell the trainer to evaluate at the end of every epoch。Lunching a training inside your notebook will then display a progress bar and complete the table you see here as you pass every apo。



![](img/1ef271a91eb13804a6c25e3c97f83cbb_1.png)

。

![](img/1ef271a91eb13804a6c25e3c97f83cbb_3.png)