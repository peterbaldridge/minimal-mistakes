---
published: true
title: Machine Learning + Wine
layout: single
author: Peter Baldridge
header:
  image: grapevine.jpg
---

Why the Science of Wine Scoring Isn’t as Flimsy as You Might Think

***
**You can check out the code that I used for this project [here.](https://github.com/peterbaldridge/WineScore)** 

***

**Disclaimer:** The author is in no way affiliated with any part of the wine industry, and was not, nor has he ever been paid-off or lobbied with fine wines and trips to Bahamas to write this or other articles about wine (Not that he would object to any extravagant lobbying, by the way. Wine lobbyists, please take note).

### THE GRAPES OF WRATH
In recent years, the wine reviewing industry has come under fire. Critiques have ranged from the inconsistency of many wine experts’ [own reviews](https://www.theguardian.com/lifeandstyle/2013/jun/23/wine-tasting-junk-science-analysis) to allegations of [outright fraud](http://vinepair.com/wine-blog/wine-ratings-industrial-complex/). Equipped with a data science toolbox and a list of 5000 wines donated by the university of Minho, Portugal, I set out to test whether or not this hypothesis true.  Is there a reliable link between the chemical composition of a bottle of wine and its quality? Or is the human palette incapable of distinguishing the layers of nuance? The goal: to try to predict a wine’s rating based solely off of it’s chemical properties.

### THE DATASET
The dataset consists of 12 measurements: wine rating (ranging from  0, very bad, to 10, very excellent) and 11 chemical attributes such as acidity, alcohol, and residual sugar. A full description of the chemical attributes can be found [here](http://archive.ics.uci.edu/ml/datasets/Wine+Quality). The dataset contains 4898 individual white wine records, 80% of which I assigned to a training set, and 20% of which I assigned to a cross-validation set.

### THE PROCESS
I used a variety of machine learning techniques to predict wine ratings. These techniques included Multiple Linear Regression, Random Forest Regression, Support Vector Machine, Artificial Neural Networks.

![](https://peterbaldridge.github.io/media/wine/manufacturing3.jpg)

### THE RESULTS
The results were clear as a bottle of fine Sauvignon blanc: wine ratings can be reliably predicted using a variety of models, a few of which exceed 90% accuracy. From a list of four models, the clear winner was the Support Vector Machine, which had an accuracy rating of 91.8%. For anyone interesting in toying around with predictive models, I highly recommend Scikit-Learn.

|Learning Method|MSE |Mean Error|Accuracy\*|
|---------------|----|----------|--------|
|MLR            |0.51|    0.55  |88.6%   |
|Random Forest  |0.39|    0.51  |90.5%   |
|SVM            |0.40|    0.49  |91.8%   |
|Neural Network |0.52|    0.54  |85.3%   |

###### \*Predictions within one point of actual score

### WHY IT MATTERS
The fact that machines are capable of deducing the collective taste of a group of wine reviewers implies that there is an **internal logic** behind the "magic" of wine scoring. This negates the idea that competitive wine science is bunk. However, this doesn’t mean that wine scoring is at all an exceptionally precise science. For example, the average error for the Support Vector Machine model is 0.51 points, or about a 5% deviation. Would I trust these models to be in the ballpark? Sure. Would I trust them to pick a blue ribbon winner? Probably not, but then again,  [I’m not sure I’d believe the experts either](https://www.theguardian.com/lifeandstyle/2013/jun/23/wine-tasting-junk-science-analysis).

### MOVING FORWARD
Anyone with a laptop and a few beakers could potentially use these models to exploit inconsistencies in the wine market. For example, an enterprising restauranteur might want to improve the quality of their table wine on the cheap by purchasing significantly undervalued bottles, all before the market takes notice.

### CODE + DATA
You can access all of the code and data that I used for this project on my [GitHub account](https://github.com/peterbaldridge/WineScore). You can also find an original link to the data [here](http://archive.ics.uci.edu/ml/datasets/Wine+Quality).
