# Triads Enumeration Using Single Machine

This repository contains Java implementations for enumerating triads in large directed graphs. The details are described in the following paper:

Y. Santoso, V. Srinivasan, A. Thomo, S. Chester, Triad Enumeration at Trillion-Scale Using a Single Commodity Machine. In the 22nd International Conference on Extending Database Technology (EDBT 2019).

## The codes:

* CombinedInOutGraph.java - Combine the graph and its transpose, and encode the links using 2-bits.

* GGTAscBg.java - Sort nodes according to degree ascendingly, relabel, and keep only neighbours with higher label. Do the relabeling simultaneously for both graph and transpose graph, using the degrees of whichever has larger max degree.

* J8PariTriadAI.java - Our implementation of the  Intersection Based algorithm (S. Parimalarangan, G.M. Slota, K. Madduri: Fast Parallel Graph Triad Census and Triangle Counting on Shared-memory Platforms, IPDPSW 2017).

* J8SevenTriangles.java - Our triad enumeration code using the 4-pointers algorithm.

* RedistDeg.java - Redistribute the effective degrees for balancing the workload when using multi-threads.

## Dependency

This requires:

* Java version 8 or higher.

* The WebGraph library.

## Input

The input graphs are in WebGraph format.

Available datasets in this format can be found in: <http://law.di.unimi.it/datasets.php>

There are three files needed:

*basename.graph* 

*basename.properties* 

*basename.offsets*

The first two files can be downloaded. The "offsets" file can be created by running: 
```
java -cp "lib/*" it.unimi.dsi.webgraph.BVGraph -o -O -L cnr-2000
```
We also need the transpose graph. 



