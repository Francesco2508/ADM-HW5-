# ADM-HW5-

Group #17:
Mario Raimo,
Francesco Romeo, 
Omirbanu Nurassilova

## Homework 5 of ADM, MSc in Data Science Sapienza University
---
In this assignment we performed an analysis of the Wikipedia Hyperlink graph. As first step we downloaded the .txt files (Wikicat hyperlink graph, wiki-topcats-categories.txt, wiki-topcats-page-names.txt).
###### [RQ1]
After, using the hyperlink file, we created our graph in a shape of dictionary where the keys are the sources nodes and the values a list of all neightbours. From the graph we determinated:
- the type of our graph (it's a directed graph)
- number of nodes = 461193
- number of edges = 2645247
- the avarage node degree = 5.735661642739591 
- its density = 1.2436602635647606e-05
---
In our repository all work is in "ADM-HW 5.ipynb" file. It contains all our methods and calculations.

###### [RQ2]
After that, we denifed our function based on BFS (Breadth-first search). This function checks each node of the graph starting from the source up to the arrival node. 

Using the function we computed distances between every pair of nodes, where the source nodes were always the nodes belong to the input category and arrive nodes changed every time dipending on the i-th category. At the end of this proces we got 28 different dictionaries where the keys are always the node of the input category and the values a list of possible paths to reach the i-th category. Per each key of all 28 dictionaries we took, from their linked list, the shortest path; in this way at the end we had per each pair of category we have a list of all shortest path and from here we took the median, used after as a score to sort all the categories.

###### [STEP 1 to 3]

- [x] Step 1:	we compute subgraph of input category assuming for every in-edges a weight of 1
- [x] Step 2: Now if we take into account that: the in-edges coming from the previous category have as weights the score of the node that sends the edge.
We need to implement a function for storing weights of the edges of nodes that comes from previous subgraph. In that function we did: take all destinations of nodes of previous subrgaph, and then take each destination as a key, and as values we take scores of nodes. 
And then we implemented function that merges nodes of previous graph and nodes of the given category. It takes as weights of edges of previous graph and take 1 to edges that comes with given category.
- [x] Step 3: And again we need to store weights of edges of the graph that we got in step 2. And then organize a cycle to add categories respecting to their position in ranking vector.
At the screenshot below you can see that out output files takes more than 1000 KB, because of this reason we did not push into github our files.
![alt text](https://github.com/Francesco2508/ADM-HW5-/blob/master/Scores_files.jpg)
