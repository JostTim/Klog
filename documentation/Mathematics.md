## Mathematics :

## Algebra : 

[Laplace tranasform](https://www.youtube.com/watch?v=n2y7n6jw5d0)



## Geometry :

#### 3D space :

[Rotations](http://web.cs.iastate.edu/~cs577/handouts/rotation.pdf)

[Rotating 3D shapes forumlas](https://www.khanacademy.org/computing/computer-programming/programming-games-visualizations/programming-3d-shapes/a/rotating-3d-shapes) and [example code (javascript ?)](https://www.khanacademy.org/computer-programming/cube-rotated-around-z/5446827933696000)

<u>Quaternions :</u>

[Quaternions, vectors and matrices for 3D space - applied for processing](https://behreajj.medium.com/3d-rotations-in-processing-vectors-matrices-quaternions-10e2fed5f0a3)

[How to handle quaterions and use them if you are not mathematician](https://developerblog.myo.com/quaternions/)

[Visualized quaternions video (3Blue1Brown)](https://www.youtube.com/watch?v=zjMuIxRvygQ) and [INTERACTIVE VIDEOS :](https://eater.net/quaternions) Ben eater's website eater.net



## Theory of information :

- Shannon entropy [ref](https://en.wikipedia.org/wiki/Entropy_(information_theory))

	> In [information theory](https://en.wikipedia.org/wiki/Information_theory), the **entropy** of a [random variable](https://en.wikipedia.org/wiki/Random_variable) is the average level of "information", "surprise", or "uncertainty" inherent in the variable's possible outcomes.

## [Graph theory](https://en.wikipedia.org/wiki/Graph_theory) :

[A very simplified explanation of it and the many uses in the real world](https://towardsdatascience.com/what-is-graph-theory-and-why-should-you-care-28d6a715a5c2)

Child of a greater branch called [network science](https://en.wikipedia.org/wiki/Network_science)

**Used for arborescence and "tree" of possibilities**. amongst other uses

[Graphs algorithms for python](https://networkx.org/documentation/latest/reference/algorithms/index.html)

Key concepts :

- **Centrality** :

  > Indicators of **centrality** assign numbers or rankings to [nodes](https://en.wikipedia.org/wiki/Vertex_(graph_theory)) within a graph corresponding to their network position. [ref](https://en.wikipedia.org/wiki/Centrality)

  - Betweenness centrality :

  	Or short : EBC for edges - NBC for nodes
  	
  	<img src="Mathematics.assets/Graph_betweenness.svg" style="zoom:33%;" />
  	
  	An [undirected graph](https://en.wikipedia.org/wiki/Undirected_graph) colored based on the betweenness centrality of each vertex from least (red) to greatest (blue).
  	
  	> For every pair of vertices in a connected graph, there exists at least  one shortest path between the vertices such that either the number of  edges that the path passes through (for unweighted graphs) or the sum of the weights of the edges (for weighted graphs) is minimized. The  betweenness centrality for each [vertex](https://en.wikipedia.org/wiki/Vertex_(graph_theory)) is the number of these shortest paths that pass through the vertex [ref](https://en.wikipedia.org/wiki/Betweenness_centrality)


- **Communities** :

	> A network is said to have **community structure** if the nodes of the network can be easily grouped into (potentially overlapping) sets of nodes such that each set of nodes is densely connected internally. [ref](https://en.wikipedia.org/wiki/Community_structure)
	
	- Detection : 
	
		Using EBC as edges weights 
	
		> (a) Agglomerative Methods
		>
		> In agglomerative methods, we start with an empty graph that consists  of nodes of the original graph but no edges. Next, the edges are added  one-by-one to the graph, starting from “stronger” to “weaker” edges.  This strength of the edge, or the weight of the edge, can be calculated  in different ways.
		>
		> Don’t worry – we will discuss this later. Keep in mind that new  communities are formed in the consecutive steps of the algorithm.
		>
		> 
		>
		> (b) Divisive Methods
		>
		> In divisive methods, we go the other way round. We start with the  complete graph and take off the edges iteratively. The edge with the  highest weight is removed first. At every step, the edge-weight  calculation is repeated, since the weight of the remaining edges changes after an edge is removed. After a certain number of steps, **we get clusters of densely connected nodes.**
		>
		> The **Girvan-Newman** algorithm is an example of the divisive method.
	
		[Community detection using EBC](https://www.analyticsvidhya.com/blog/2020/04/community-detection-graphs-networks/) and the Girvan-Newman algorithm.
		
		[A paper review on the processes available](https://arxiv.org/abs/0906.0612) 

- [Adjacency matrix](https://en.wikipedia.org/wiki/Adjacency_matrix) a representation of a graph in a matricial calculation way

[Deep learning and graph theory for connectivity analysis](https://tel.archives-ouvertes.fr/tel-02479670/document)





## Interesting concepts :

- A classical approach to spike sorting using PCAs  [ref](https://yliapis.github.io/A-Classical-Approach-to-Spike-Sorting/)  Yannis Liapis's github website

- [Bande passante](https://fr.wikipedia.org/wiki/Bande_passante) 

	> est l'intervalle de [fréquences](https://fr.wikipedia.org/wiki/Fréquence) dans lequel l'affaiblissement du signal est inférieur à une valeur spécifiée ([CEI](https://fr.wikipedia.org/wiki/Bande_passante#CEI60050)).
	>
	> C'est une façon sommaire de caractériser la gamme de fréquences qu'un système peut raisonnablement traiter
	>
	> Par [analogie](https://fr.wikipedia.org/wiki/Analogie), dans le domaine des [réseaux informatiques](https://fr.wikipedia.org/wiki/Réseau_informatique), spécialement les [accès à internet à haut débit](https://fr.wikipedia.org/wiki/Accès_à_internet_à_haut_débit), on utilise le terme *bande passante* pour désigner le [débit binaire](https://fr.wikipedia.org/wiki/Débit_binaire) maximal d'une voie de transmission.

- [Fonction de transfert](https://fr.wikipedia.org/wiki/Fonction_de_transfert) 

	> une **fonction de transfert** est un modèle mathématique de la relation entre l'entrée et la sortie d'un [système linéaire](https://fr.wikipedia.org/wiki/Système_linéaire)

- Dynamic time warping [DTW](https://en.wikipedia.org/wiki/Dynamic_time_warping) : comparison of two time series that may be shifted in time or scaled differently in time. [ref](https://groups.google.com/g/sci.image.processing/c/KOZoeLL945I?pli=1)
- Comparison paper with another strategy for comparing time series based on "features" extraction [ref](https://ieeexplore.ieee.org/document/9095654)

Application for the same kind of need for images : 

- Image registration  :

	[ref](https://en.wikipedia.org/wiki/Image_registration)
	
	![](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d7/Registrator_Demo2.png/220px-Registrator_Demo2.png)


​	

	- Image obtained with the great software Twibright registrator http://ronja.twibright.com/registrator.php

- [diffeomorphic](https://en.wikipedia.org/wiki/Diffeomorphism) mapping ([diffeomorphometry](https://en.wikipedia.org/wiki/Computational_Anatomy#Diffeomorphometry:the_metric_space_of_shapes_and_forms)) :

	- [LDDMM](https://en.wikipedia.org/wiki/Large_deformation_diffeomorphic_metric_mapping)
	
- Image Edge detection [ref](https://en.wikipedia.org/wiki/Edge_detection)

- Filtre de Canny [ref](https://fr.wikipedia.org/wiki/Filtre_de_Canny) - 

	[![img](Mathematics.assets/220px-Valve_original_(1).PNG)](https://commons.wikimedia.org/wiki/File:Valve_original_(1).PNG?uselang=fr)[![img](Mathematics.assets/220px-Valve_monochrome_canny_(6).PNG)](https://commons.wikimedia.org/wiki/File:Valve_monochrome_canny_(6).PNG?uselang=fr)
	
	> Le **filtre de Canny** (ou détecteur de Canny) est utilisé en [traitement d'images](https://fr.wikipedia.org/wiki/Traitement_d'images) pour la [détection des contours](https://fr.wikipedia.org/wiki/Détection_de_contours). 



Ordre de magnitude : [ref](https://en.wikipedia.org/wiki/Order_of_magnitude#Calculating_the_order_of_magnitude)

> | In words ([long scale](https://en.wikipedia.org/wiki/Long_and_short_scales)) | In words ([short scale](https://en.wikipedia.org/wiki/Long_and_short_scales)) | Prefix (Symbol)                                   | Decimal | [Power](https://en.wikipedia.org/wiki/Exponent#Powers_of_ten) of ten | Order of magnitude |
> | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------- | ------- | ------------------------------------------------------------ | ------------------ |
> | tenth                                                        | tenth                                                        | deci- (d)                                         | 0.1     | 10−1                                                         | −1                 |
> | one                                                          | one                                                          |                                                   | 1       | 100                                                          | 0                  |
> | ten                                                          | ten                                                          | [deca-](https://en.wikipedia.org/wiki/Deca-) (da) | 10      | 101                                                          | 1                  |
> | hundred                                                      | hundred                                                      | hecto- (h)                                        | 100     | 102                                                          | 2                  |
> | thousand                                                     | thousand                                                     | kilo- (k)                                         | 1000    | 103                                                          | 3                  |



[Attracteur de lorenz](https://fr.wikipedia.org/wiki/Attracteur_de_Lorenz#Points_d'%C3%A9quilibre) - [Fractales](https://fr.wikipedia.org/wiki/Fractale) - [Ensemble de Julia et de Fatou](https://fr.wikipedia.org/wiki/Ensemble_de_Julia) - [Dimension de Hausdorff](https://fr.wikipedia.org/wiki/Dimension_de_Hausdorff)



<u>Inverse kinematics</u> - to detemine the position of a point in space with rigid bodies with various degrees of liberties tethered to that point



[Notation polonaise inverse :](https://fr.wikipedia.org/wiki/Notation_polonaise_inverse)

Position des opérandes différente de la notation classique

> « 3 × (4 + 7) » peut s'écrire en NPI sous la forme « 4 (enter) 7 + 3 × »

