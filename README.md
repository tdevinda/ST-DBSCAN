# Documentation ST-DBSCAN

ST-DBSCAN is a density-based clustering algorithm that takes into account both spatial and non-spatial attributes of the points. Like DBSCAN, this algorithm has the ability to identify clusters with arbitrary shape and it does not necessarily predetermine the number of clusters. The non-spatial attribute could be anyone that is not related to coordinates in a space (e.g., color, time, temperature).  Thus, ST-DBSCAN can create groups with points that are spatially near each other and that has similar non-spatial attributes. 

Different from DBSCAN, wich requires only two parameters, ST-DBSCAN requires four parameters: Eps1, Eps2, MinPts, and Delta-Epson.  Eps1 is the spatial distance, the maximum distance for a point be assign to a cluster. Eps2 is the maximum difference between non-spatial attributes. MinPts is the minimum number of neighbors for a point be a core point. The last one, Delta-Epson is the maximum difference between the attributes value average of a cluster and the attribute value for a new point wich will be inserted in that cluster. The parameter Delta-Epson has the function of split clusters that are near each other considering spatial aspects and are much different considering the non-spatial attribute. Delta-Epson was not implemented on this version.

The ST-DBSCAN algorithm is composed basically of two functions. The main one is named ST-DBSCAN and creates clusters iteratively. This function uses another, retrive_neighborhood, which retrieves those points that are the neighbors of a given point.
