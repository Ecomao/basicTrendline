# basicTrendline: an R package for adding trendline of basic regression models to plot

[![cran version](http://www.r-pkg.org/badges/version/basicTrendline)](http://cran.rstudio.com/web/packages/basicTrendline) 
[![rstudio mirror downloads](http://cranlogs.r-pkg.org/badges/grand-total/basicTrendline)](https://github.com/metacran/cranlogs.app)
[![HitCount](http://hits.dwyl.io/PhDMeiwp/basicTrendline.svg)](http://hits.dwyl.io/PhDMeiwp/basicTrendline)

## Installing "basicTrendline" package in R

- from R 

Open R software and run:

	install.packages("basicTrendline")
	library(basicTrendline)

- from Github

You can install directly **from GitHub** if you have the devtools package installed:

    install.packages("devtools")
	library(devtools)   
	install_github("PhDMeiwp/basicTrendline@master", force = TRUE)
	library(basicTrendline)


## Using "basicTrendline" package
	
Then upload your dataset including x and y data, for example

    x<-c(1,30,90,180,360)
    y<-c(4,8,10,11,11)

and run 

	library(basicTrendline)

	trendline(x,y,model="exp3P", summary=TRUE, eDigit=10, ePos="topleft",linecolor="red")  
	
You can chanage other models, using the same function "trendline()"

“model” is one of c('lin2P','line3P','log2P','exp3P','power3P')
	
- "line2P"    # y=a\*x+b

- "line3P"    # y=a\*x^2+b\*x+c

- "log2P"     # y=a\*ln(x)+b

- "exp3P"     # y=a\*exp(b\*x)+c

- "power3P"   # y=a*x^b+c)

**Moreover**, we can draw **different regression lines in one plot!!!**

<img src="docs/images/Multilines.png" width="890"/>

	plot(x1,y1,main="Different regression lines in one plot")
	
	library(basicTrendline)
	trendline(x1,y1,model="line2P",plot=FALSE,ePos="none",linecolor="red")
	trendline(x1,y1,model="log2P",plot=FALSE,ePos="none",linecolor="blue",lty=2)
	trendline(x1,y1,model="exp3P",plot=FALSE,ePos="none",linecolor="black",lty=3)
	legend("bottomright",c("line2P","log2P","exp3P"), lty=c(1,2,3),col=c("red","blue","black"))


## Highlights

<font color=red>The "basicTrendline" package in R software could output **a better regression result (higher R-squared and lower p-value)** for 'power3P' model（y = ax^b +c） **than those in OriginPro** software.</font> Please see the example below:

>formula as y=a*x^b +c

x<- c(1,30,60,90,180,360)

y<- c(2,14,16,18,19,20)  # increase convex-function

>in OriginPro software:

c=-7344.578

a=7347.183

b=43224.4

<font color=red>**adjR^2= 0.97129       # lower adjR^2 value**</font>

p-value of model=2.24891e-4

>in the 'basicTrendline' R package:

c=34.671

a=-32.703

b=-0.13999

<font color=red>**adjR^2= 0.99346 >  0.97129   # higher (or better ) adjR^2 value**</font>

p-value of model= 2.44924-5 < 2.24891e-4

## Graphics

<img src="docs/images/line2P.png" width="890"/>
<img src="docs/images/line3P.png" width="890"/>
<img src="docs/images/log.png" width="890"/>
<img src="docs/images/log0.5.png" width="890"/>
<img src="docs/images/exp.png" width="890"/>
<img src="docs/images/power.png" width="890"/>


To see examples on how to use "basicTrendline" in R software, you can run the following R code if you have the "basicTrendline" package installed:

    library(basicTrendline)
    ?trendline()


## Contributions

R codes contributed by


- adding-regression-line-equation-and-r2-on-graph-1: http://blog.sciencenet.cn/blog-267448-1021594.html
- adding-regression-line-equation-and-r2-on-graph-2: https://stackoverflow.com/questions/7549694/adding-regression-line-equation-and-r2-on-graph
- What is non-linear regression?: https://datascienceplus.com/first-steps-with-non-linear-regression-in-r/
- adding regression line for nonlinear regression: http://blog.sciencenet.cn/blog-651374-1014133.html
- R codes for 'print.summary.nls of exp3P and power3P' cite from https://github.com/SurajGupta/r-source/blob/master/src/library/stats/R/nls.R
- and so on...

## Appendix

The PDF files of this R package is available at https://cran.r-project.org/web/packages/basicTrendline/index.html 


**If you have any question or comment to this package, tell me at [here](http://meiweiping.cn/en/basicTrendline: an R package for adding trendline of basic regression models to plot/).**