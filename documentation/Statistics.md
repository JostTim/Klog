## Statistics :

[Simple and multiple](https://towardsdatascience.com/the-complete-guide-to-linear-regression-in-python-3d3f8f06bf8) linear regression in python, with scikit learn and statsmodels api

[ANCOVA](https://stackoverrun.com/fr/q/637878)

[Factorial ANOVA](https://www.pythonfordatascience.org/factorial-anova-python/#test_with_python)

[Normality test in scipy.stats](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.normaltest.html) - [Tutorial on normality tests in python](https://machinelearningmastery.com/a-gentle-introduction-to-normality-tests-in-python/)

| Test                        | Parametric    | Non parametric |
| --------------------------- | ------------- | -------------- |
| Two pop                     | T test        | U test         |
| One pop with two conditions | Paired T test | Wilcoxon       |
|                             |               |                |

RMSE - [Root mean square deviation - Ecart Quadratique Moyen](https://www.aspexit.com/comment-valider-un-modele-de-prediction/) Utilise pour quantifier l'erreur d'un modele de prediction ( ou l'erreur d'execution/de mesure entre un capteur et un actuateur, selon celui auquel on se fie)



### Standardization :

A more general term than than normalization, that can imply more specific things.

[Z score](https://www.topdowncharts.com/post/2018/05/28/how-do-you-create-a-z-score) [an use case](https://medium.com/@9soura/now-comes-the-painful-part-you-will-have-to-replicate-this-for-all-the-territories-separately-1b73f28d47b4) for detecting outliers in time series.

<u>Normalization</u> : 

[Z normalization](https://jmotif.github.io/sax-vsm_site/morea/algorithm/znorm.html) 

[A link where they compute it in python](https://xcdskd.readthedocs.io/en/latest/cross_correlation/cross_correlation_coefficient.html)



### Correlations  :

- Linear transformation on data do not change Pearson's correlation as it is a linear correlation. However, non linear transformations do. [ref](https://stats.stackexchange.com/questions/403413/does-data-normalization-and-transformation-change-the-pearsons-correlation)

	> the correlation coefficient is independent  of change of origin and scale. As such standardization will not alter  the value of correlation. [ref](https://www.researchgate.net/post/Do_we_need_to_standardize_variables_with_different_scales_before_doing_correlation_analysis)

- Pearson's correlation for so supposedly 2 random variables.

- Cross correlation : the time cross correlation of time series (Or any indexed signal).
	
	Très proche de la formule pour le [produit de convolution](https://fr.wikipedia.org/wiki/Produit_de_convolution) 
	
	> Produit de convolution :  fait correspondreà deux fonction *f* et *g* une autre fonction « *f* ∗ *g* » sur ce domaine, qui en tout point de celui-ci est égale à l'[intégrale](https://fr.wikipedia.org/wiki/Intégration_(mathématiques)) sur l'entièreté du domaine.
	
	- Autocorrelation is this phenomenon for a time series around itself
	
- Coorelation croisée de deux vecteurs  != covariance interne d'un vecteur aléatoire unique

	> La **corrélation croisée** est parfois utilisée en [statistique](https://fr.wikipedia.org/wiki/Statistique) pour désigner la [covariance](https://fr.wikipedia.org/wiki/Covariance) des vecteurs [aléatoires](https://fr.wikipedia.org/wiki/Variable_aléatoire) X et Y, afin de distinguer ce concept de la « covariance » d'un vecteur aléatoire, laquelle est comprise comme étant la [matrice de covariance](https://fr.wikipedia.org/wiki/Matrice_de_covariance) des coordonnées du vecteur.
	>
	> En [traitement du signal](https://fr.wikipedia.org/wiki/Traitement_du_signal), la **corrélation croisée** (aussi appelée **covariance croisée**) est la mesure de la similitude entre deux signaux.

### Agregators :

> Moyenne et médiane jouent un rôle similaire dans la compréhension de la  tendance centrale d'une série de chiffres. La moyenne a  traditionnellement été une mesure populaire d'un point central dans un  ensemble, mais elle a l'inconvénient d'être influencée par des valeurs  qui sont très inférieures ou supérieures au reste des valeurs. C'est  pourquoi la médiane (second quartile) est une meilleure mesure centrale pour les cas où un petit nombre de valeurs aberrantes peut considérablement fausser la  moyenne.



[Statistical dispersion indicators](https://fr.wikipedia.org/wiki/Indicateur_de_dispersion) 

### Boxplots :

Quartiles :

> Un **quartile** est chacune des trois valeurs qui divisent les données  triées en quatre parts égales, de sorte que chaque partie représente 1/4 de l'échantillon de population
>
> - le 1er quartile est la donnée de la série qui sépare les 25 % inférieurs des données (notation Q1) ;
> - le 2e quartile est la donnée de la série qui sépare les 50 % inférieurs des données (notation Q2) ; il est également appelé médiane ;
> - le 3e quartile est la donnée de la série qui sépare les 75 % inférieurs des données (notation Q3) ;
> - Par extension : le 0e quartile est la donnée de la série qui sépare les 0 % inférieurs des données (notation Q0, c'est le minimum) et le 4e quartile est la donnée de la série qui sépare les 0 % supérieurs des inférieurs des données (notation Q4, c'est le maximum)
>
>  [ref](https://fr.wikipedia.org/wiki/Quartile)

IQR : 

> In [descriptive statistics](https://en.wikipedia.org/wiki/Descriptive_statistics), the **interquartile range** (**IQR**), also called the **midspread**, **middle 50%**, or **H‑spread**, is a measure of [statistical dispersion](https://en.wikipedia.org/wiki/Statistical_dispersion), being equal to the difference between 75th and 25th [percentiles](https://en.wikipedia.org/wiki/Percentiles), or between upper and lower [quartiles](https://en.wikipedia.org/wiki/Quartile),[[1\]](https://en.wikipedia.org/wiki/Interquartile_range#cite_note-Upton-1)[[2\]](https://en.wikipedia.org/wiki/Interquartile_range#cite_note-ZK-2) IQR = *Q*3 − *Q*1. In other words, the IQR is the third quartile subtracted from the first quartile; these quartiles can be clearly seen on a [box plot](https://en.wikipedia.org/wiki/Box_plot) on the data. It is a [trimmed estimator](https://en.wikipedia.org/wiki/Trimmed_estimator), defined as the 25% trimmed [range](https://en.wikipedia.org/wiki/Range_(statistics)), and is a commonly used [robust measure of scale](https://en.wikipedia.org/wiki/Robust_measures_of_scale). [ref](https://en.wikipedia.org/wiki/Interquartile_range)

<img src="Statistics.assets/boxplot_explanation.png" style="zoom: 50%;" />



### Voc : 

- [Stochastique](https://en.wikipedia.org/wiki/Stochastic) : produit de l'effet du hazard
- [Heteroscedasticity](https://en.wikipedia.org/wiki/Heteroscedasticity) : inverse of the homogeneity of variance

- 
