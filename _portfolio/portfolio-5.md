![image](https://github.com/kirthikasena/kirthikasena.github.io/assets/95086317/d7350a5a-37a4-4f9f-97a4-5606f99b5bc2)---
title: "K-means cluster analysis with silhouettes of vehicles using R studio"
excerpt: "conduct the k-means clustering analysis of this vehicle dataset problem. As this is
a typical multi-dimensional, in terms of features,PCA is done. In this specific clustering part, however, the analysis will be performed with all
initial features, as the main aim is to assess different clustering results under the initial
conditions. Before conducting the k-means, the following pre-processing tasks: scaling
and outliers’ removal are performed.  the number of cluster centres are defined  (via manual & automated
tools) and k-means analysis is performed for each attempt. For each of the above k-means
attempts, produced cluster outcome are checked against the information obtained from trype of cars/vehicles
column  Finally, for the “winner” case, the coordinates of
each centre for each clustering group is provided."
collection: portfolio
---

A set of observations on a number of silhouettes has been considered with
related to different type of vehicles, using a set of features extracted from the silhouette. Each
vehicle may be viewed from one of many different angles. The features were extracted from
the silhouettes by the HIPS (Hierarchical Image Processing System) extension BINATTS, which
extracts a combination of scale independent features utilizing both classical moments-based
measures such as scaled variance, skewness and kurtosis about the major/minor axes and
heuristic measures such as hollows, circularity, rectangularity, and compactness. Four model
vehicles were used for the experiment: a double decker bus, Chevrolet van, Saab, and an Opel
Manta. This particular combination of vehicles was chosen with the expectation that the bus,
van and either one of the cars would be readily distinguishable, but it would be more difficult
to distinguish between the cars.
One dataset (vehicles.xls) is available and has 846 observations/samples. There are 19
variables/features, all numerical and one nominal defining the class of the objects. This is a
classic multi-dimensional, in terms of features, problem.
Description of attributes:
1. Comp: Compactness
2. Circ: Circularity
3. D.Circ: Distance Circularity
4. Rad.Ra: Radius ratio
5. Pr.Axis.Ra: pr.axis aspect ratio
6. Max.L.Ra: max.length aspect ratio
7. Scat.Ra: scatter ratio
8. Elong: elongatedness
9. Pr.Axis.Rect: pr.axis rectangularity
10. Max.L.Rect: max.length rectangularity
11. Sc.Var.Maxis: scaled variance along major axis
12. Sc.Var.maxis: scaled variance along minor axis
13. Ra.Gyr: scaled radius of gyration
14. Skew.Maxis: skewness about major axis
15. Skew.maxis: skewness about minor axis
16. Kurt.maxis: kurtosis about minor axis
17. Kurt.Maxis: kurtosis about major axis
18. Holl.Ra: hollows ratio
19. Class: type of cars (desired output)

After the PCA and the preprocessing tasks(scaling and removal of outliers)
k-means analysis is done and evaluated

<h6>K-means-analysis and Evaluation using confusion matrix for each attempt</h6>
k-means centers used:2-4 to choose the winner cluster.Attempt to find the optimal number of clusters to use:
plot using NbClust package with :

<img src='/images/Screenshot 2023-08-03 at 13.25.47.png'>



<b>Technologies: R studio ,machine learning, unsupervised learning</b>
<a href="https://qvalia.com/features/unspsc-classification/">view the service</a>
<img rel="icon" href="https://img.shields.io/badge/Python-white?logo=Python"> <img rel="icon" href="https://img.shields.io/badge/Jupyter-white?logo=Jupyter"> <img rel="icon" href="https://img.shields.io/badge/Tensorflow-white?logo=Tensorflow">
<hr style="border-top: dotted 1px;" />
