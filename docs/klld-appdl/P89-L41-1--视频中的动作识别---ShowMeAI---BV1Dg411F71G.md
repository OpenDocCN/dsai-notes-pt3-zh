# P89：L41.1- 视频中的动作识别 - ShowMeAI - BV1Dg411F71G

So last session we started working with data in the form of a video and a video。

 you can treat it as several conuous frames in time。

 So it's gonna be several contiguous images in time it is still structure data It has a structure it's gonna be on a two dimensionsal grid and you're gonna have that two dimensional grid evolving over time。

 So now you have three dimensions rather than two to worry about and there are two important data sets。

 These are two benchmarks that I highly encourage you to do exploratory data analysis on them。

 they are not big data sets they are of moderate size to small size is UCf 101 from YouTube videos and it has one01 categories and the other one has51 categories It's for action recognition So one observation that you can make about videos is that you can。

And naturally decompose them into spatial and temporal。



![](img/bef70c02dbede9baf4af1548d68b0a03_1.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_2.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_3.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_4.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_5.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_6.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_7.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_8.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_9.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_10.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_11.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_12.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_13.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_14.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_15.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_16.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_17.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_18.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_19.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_20.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_21.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_22.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_23.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_24.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_25.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_26.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_27.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_28.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_29.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_30.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_31.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_32.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_33.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_34.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_35.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_36.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_37.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_38.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_39.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_40.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_41.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_42.png)

![](img/bef70c02dbede9baf4af1548d68b0a03_43.png)