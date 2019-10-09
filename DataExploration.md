# Linda Loring Nature Foundation Phenology dataset
                                         
**Phenology Dataset has been given by Dr. Sarah T Bois. This data has been recorded as per month basis and then later divided as per Sites.
This dataset contains some important parameters for phenology like Date & Time, Temerature, Intensity and many more.**

### Below I have attached some Rplots which has been created with Date & Time, Temerature, Intensity variables.

#### 1a) Two scatter plots of two different variables

![](https://github.com/dhwani1403/LLNF_Data/blob/master/Rplot_1a.jpeg)
```
> library(tidyverse)
> LLNF <- read.csv("Site_A_LLNF.csv", header = TRUE)
> colnames(LLNF)
> names(LLNF)[names(LLNF) == "Date.Time..GMT.04.00"] <- "DateTime"
> names(LLNF)[names(LLNF) == "Temp..Â.C..LGR.S.N..10638853..SEN.S.N..10638853."] <- "Temperature"
> names(LLNF)[names(LLNF) == "Intensity..Lux..LGR.S.N..10638853..SEN.S.N..10638853."] <- "Intensity"
> ggplot(LLNF,aes(x=Temperature,y=Intensity))+
+ geom_point(color="Dark blue")
```
#### 1b)

![](https://github.com/dhwani1403/LLNF_Data/blob/master/Rplot_1b.jpeg)
```
> ggplot(LLNF,aes(x=DateTime,y=Intensity))+
+ geom_point(color="Dark blue")
```
#### 2) One scatter plot with three variables

![](https://github.com/dhwani1403/LLNF_Data/blob/master/Rplot_2.jpeg)
```
> ggplot(LLNF,aes(x=DateTime,y=Intensity,color=Temperature))+
+ geom_point()
```
#### 3) One scatter plot of two variables, properly labeled, with a trend line added in

![](https://github.com/dhwani1403/LLNF_Data/blob/master/Rplot_3.jpeg)
```
> ggplot(LLNF,aes(x=Temperature,y=Intensity))+
+ geom_point()+
+ geom_smooth(method="lm")
```

#### 4) One faceted plot of two variables

![](https://github.com/dhwani1403/LLNF_Data/blob/master/Rplot_4.jpeg)
```
> LLNF1<-gather(LLNF,key="measure",value="value",c(Intensity,DateTime))
> ggplot(LLNF1,aes(x=Temperature,y=value))+
+ geom_point()+
+ facet_wrap(~measure)+
+ theme_bw()
```
#### 5) One bar chart

![](https://github.com/dhwani1403/LLNF_Data/blob/master/Rplot_5.jpeg)
```
> ggplot(LLNF,aes(x=Temperature,y=Intensity,fill="grp"))+
+     geom_bar(stat="identity",color="blue",width=0.5)
```
