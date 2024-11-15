# 2FWL-SIRGN


This repository provides a reference implementation of **2FWL-SIRGN** as described in the paper:
```
    2FWL-SIRGN: A Scalable Structural 2-dimensional Folklore Weisfeiler Lehman Graph Representation Learning Approach Via Structural Graph Partitioning
```
Justin Carpenter and Edoardo Serra.


The 2FWL-SIRGN algorithm generates accurate structural node representations for large graphs. These representations utilizes a higher-order Weisfiler Lehman, 2 dimensional FWL. 

The cost of higher-order approaches, tend to outweigh the improvements in expresivity power. Due to this limitation, This repository provides a reference implementation of **Structural Graph Partition** allowing 2FWL-SIRGN to still operate on very large graphs.

## Citation
If you find Temporal SIR-GN useful for your research, please cite the following paper:
```bibtex
@article{TBD,
	author = {Carpenter, Justin, and Serra, Edoardo},
	title = {2FWL-SIRGN: A Scalable Structural 2-dimensional Folklore Weisfeiler Lehman Graph Representation Learning Approach Via Structural Graph Partitioning},
	year = {2024}
}
```

## Requirements
```
    numpy
    pandas
    sklearn
    math
    networkx
```
## Install and Running

To install, clone repository and install dependencies.

This includes the MUTAG dataset in the directory "data/MUTAG/" Be sure to not alter the path unless altering the __main__ in the file 2FWL_SIRGN_GraphPartition.py :
```
        'data/MUTAG/MUTAG_A.txt', list of edges in mutag
        'data/MUTAG/MUTAG_edge_labels.txt', list of edge labels
        'data/MUTAG/MUTAG_node_labels.txt', list of node labels
        'data/MUTAG/MUTAG_graph_indicator.txt', list of graph labels
```
Run using:
```
        python3 2FWL_SIRGN_GraphPartition.py
```
2FWL_SIRGN_GraphPartition.py Paramiters: (Graph1, Graph2, filename, n, node_labels, partitions, iterations)    
```    
    -Graph1: The primary graph to preform the graph partition on and returns the 2FWL_SIR-GN embeddings.             
    -Graph2: The second graph is the same but is format friendly for SIR-GN to operate on for pre-embeddings.        
    -Filename: This is the path to save the pre-embeddings from SIR-GN for decreased time in future operations.      
    -N: This is the number of hops away from each node to calculate.                                                 
    -Node_labels: This is a list of all the nodes in the graph and their corresponding labels.                       
    -Partitions: This is the number of partitions to split the graph into to increase performance                    
    -Iterations: This is the number of iterations to do the 2FWL-SIRGN algorithm on the graph   
```

## Details

By default the program runs for with 20 partitions and 10 iterations on the MUTAG dataset

## Output

Upon completion the program will store the finished embeddings to 'FWL_SIRGN_GRAPH_PARTITION_MUTAG_10_20_10.txt' with an additional file 'SIRGN_embeddings_MUTAG_10_20_10.txt' which contains the original SIR-GN embeddings. 

This model should produce an F1 score of around .95 using default settings.
