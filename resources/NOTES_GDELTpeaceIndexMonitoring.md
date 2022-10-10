# Estimating countries' peace index through the lens of the world news as monitored by GDELT

These are notes to accompany my reading the above stated academic article.

```
Abbreviations:
. p == peace, peacefulness
. wp == world peace
. wpc == world piece computer
. up == universal peace
. upc == universal peace computer
```

```
blairmunroakusa@0501Thu.21Jul22.anch.AK:br
Abstract:
. p is dimension of wellbeing, of interest to policy-makers and researchers
. recent emergence of novel digital data streams is impacting field of research
. study draws from Global Data on Events, Location, and Tone (GDELT) digital news database
. purpose of drawing from database is to capture p via Global P Index (GPI)
. ML technique demonstrates metrics from GDELT are proxies for measuring GPI
. + variable importance analysis generates country profiles emerge as result of study
. this all may enable real-time monitoring of p
```
```
blairmunroakusa@0514Thu.21Jul22.anch.AK:br
Introduction, 1st pass:
. a big issue in GPI generation is Dt lag
. results somehow verify that GDELT metrics are effective proxies
```
```
blairmunroakusa@0539Thu.21Jul22.anch.AK:br
Related Works, 1st pass:
. usually p is captured by official data (gov or NGO)
. Twitter is one example of a popular unofficial social media data stream
. mobility data (location services/GPS) is another unofficial stream source
*lookup* ACLED is a conflict-related news database 
. apparently GDELT is barely explored in this context
```
```
blairmunroakusa@0559Thu.21Jul22.anch.AK:br
Methodology, 1st pass:
. describing data used, three models to produce GPI estimates
A . Data description:
. GPI, measure of nations relative p (with 3 GDELT dimensions to predict)
.. # events (media attention)
.. tone (sentiment)
... Goldstein (social stability)
. GDELT, socio-political news database
*lookup* Tabari system for encoding news reports
*lookup* dyadic CAMEO format
.. tone is emotional impact of an event, from algorithms presented by Shook et al
.. Goldstein is a measure of potential impact on country stability
B . Prediction models
. ML models that handle time series are employed
. these models describe relationship between GPI and GDELT
. 1 Elastic Net
.. regularized + variable selection regression method
.. used to penalize unimportant shit, but by reducing to ~0, not removing
. 2 Decision Tree
.. meant to create training model to learn to predict dependent variable
. 3 Random Forest
.. prevents decision tree from overfitting the data
C . Dynamic training
. rolling forcast used to perform dynamic model training 
. models must be frequently retrained
. data comes from 2008-2018
```
```
blairmunroakusa@0716Thu.21Jul22.anch.AK:br
Results, 1st pass:
. all three models are applied separately
. Pearson correlation indicates random forest outperforms
. problem though with Pearson is anticorrelation in several states
. lots of cross-comparing the different correlatives and error measures for various cases
A . Variable importance
. variable importance measured by mean decrease accuracy (MDA)
. MDA applied to each of training phases
. _importance_ indicated by arithmetic mean of MDA values
. importance evaluation applied to all 3 models
. variable importance depends on the status of a state--wartorn, p, powerful
B . Interpretation of errors in the predictions
. variable importance analysis is used to explain differing model effectiveness
. lots of analysis here, little too detailed for now
```
```
blairmunroakusa@0730Thu.21Jul22.anch.AK:br
Conclusion, 1st pass:
. overview overview
. criticism: traditional media is distorted view of reality
. criticism: methods interpolate between annual GPI data
```

### Some immediate thoughts: 

This approach to correlating GPI to realtime datastreams will only go so far, due to criticism number one. A fundamental idea underminning wpc is that wpcs will be deployed and serve as datastream probes within society. The obvious challenge of course, will be networking the wpcs, especially with wps that may not be electronic/digital. In this case, upc (the network of codependent wpcs) will be responsible for running the ML models, regression analyses, etc...in that it will take sum(wpc data streams) and use them to compute global and local GPIs (and whatever other metrics will be deemed necessary to achieve wp).

In terms of the fractal nature of wpcs and upc, an individual wpc if functioning optimally, will be able to compute local GPI-like indeces. This will likewise be the difference between a community wpc and individual wpcs that comprise it. Again, the trinary structure:

```
A world piece computer:

_______________UPC______________
  * wpc		       : : : :
  |		       : : : : 	
  O pieces	  wpc  * : : :
		       | : : :
		       O-*-*-*	wpcs
		 	 | | |
			 O O O
```

