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
	
	Tr??s proche de la formule pour le [produit de convolution](https://fr.wikipedia.org/wiki/Produit_de_convolution) 
	
	> Produit de convolution :  fait correspondre?? deux fonction *f* et *g* une autre fonction ?? *f* ??? *g* ?? sur ce domaine, qui en tout point de celui-ci est ??gale ?? l'[int??grale](https://fr.wikipedia.org/wiki/Int??gration_(math??matiques)) sur l'enti??ret?? du domaine.
	
	- Autocorrelation is this phenomenon for a time series around itself
	
- Coorelation crois??e de deux vecteurs  != covariance interne d'un vecteur al??atoire unique

	> La **corr??lation crois??e** est parfois utilis??e en [statistique](https://fr.wikipedia.org/wiki/Statistique) pour d??signer la [covariance](https://fr.wikipedia.org/wiki/Covariance) des vecteurs [al??atoires](https://fr.wikipedia.org/wiki/Variable_al??atoire) X et Y, afin de distinguer ce concept de la ?? covariance ?? d'un vecteur al??atoire, laquelle est comprise comme ??tant la [matrice de covariance](https://fr.wikipedia.org/wiki/Matrice_de_covariance) des coordonn??es du vecteur.
	>
	> En [traitement du signal](https://fr.wikipedia.org/wiki/Traitement_du_signal), la **corr??lation crois??e** (aussi appel??e **covariance crois??e**) est la mesure de la similitude entre deux signaux.

### Agregators :

> Moyenne et m??diane jouent un r??le similaire dans la compr??hension de la  tendance centrale d'une s??rie de chiffres. La moyenne a  traditionnellement ??t?? une mesure populaire d'un point central dans un  ensemble, mais elle a l'inconv??nient d'??tre influenc??e par des valeurs  qui sont tr??s inf??rieures ou sup??rieures au reste des valeurs. C'est  pourquoi la m??diane (second quartile) est une meilleure mesure centrale pour les cas o?? un petit nombre de valeurs aberrantes peut consid??rablement fausser la  moyenne.



[Statistical dispersion indicators](https://fr.wikipedia.org/wiki/Indicateur_de_dispersion) 

### Boxplots :

Quartiles :

> Un **quartile** est chacune des trois valeurs qui divisent les donn??es  tri??es en quatre parts ??gales, de sorte que chaque partie repr??sente 1/4 de l'??chantillon de population
>
> - le 1er quartile est la donn??e de la s??rie qui s??pare les 25 % inf??rieurs des donn??es (notation Q1) ;
> - le 2e quartile est la donn??e de la s??rie qui s??pare les 50 % inf??rieurs des donn??es (notation Q2) ; il est ??galement appel?? m??diane ;
> - le 3e quartile est la donn??e de la s??rie qui s??pare les 75 % inf??rieurs des donn??es (notation Q3) ;
> - Par extension : le 0e quartile est la donn??e de la s??rie qui s??pare les 0 % inf??rieurs des donn??es (notation Q0, c'est le minimum) et le 4e quartile est la donn??e de la s??rie qui s??pare les 0 % sup??rieurs des inf??rieurs des donn??es (notation Q4, c'est le maximum)
>
>  [ref](https://fr.wikipedia.org/wiki/Quartile)

IQR : 

> In [descriptive statistics](https://en.wikipedia.org/wiki/Descriptive_statistics), the **interquartile range** (**IQR**), also called the **midspread**, **middle 50%**, or **H???spread**, is a measure of [statistical dispersion](https://en.wikipedia.org/wiki/Statistical_dispersion), being equal to the difference between 75th and 25th [percentiles](https://en.wikipedia.org/wiki/Percentiles), or between upper and lower [quartiles](https://en.wikipedia.org/wiki/Quartile),[[1\]](https://en.wikipedia.org/wiki/Interquartile_range#cite_note-Upton-1)[[2\]](https://en.wikipedia.org/wiki/Interquartile_range#cite_note-ZK-2) IQR = *Q*3 ??? *Q*1. In other words, the IQR is the third quartile subtracted from the first quartile; these quartiles can be clearly seen on a [box plot](https://en.wikipedia.org/wiki/Box_plot) on the data. It is a [trimmed estimator](https://en.wikipedia.org/wiki/Trimmed_estimator), defined as the 25% trimmed [range](https://en.wikipedia.org/wiki/Range_(statistics)), and is a commonly used [robust measure of scale](https://en.wikipedia.org/wiki/Robust_measures_of_scale). [ref](https://en.wikipedia.org/wiki/Interquartile_range)

<img src="Statistics.assets/boxplot_explanation.png" style="zoom: 50%;" />



### Voc : 

- [Stochastique](https://en.wikipedia.org/wiki/Stochastic) : produit de l'effet du hazard
- [Heteroscedasticity](https://en.wikipedia.org/wiki/Heteroscedasticity) : inverse of the homogeneity of variance

- 
