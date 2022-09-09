# Quantum Link Prediction in Complex Networks
### João P. Moutinho, André Melo, Bruno Coutinho, István A. Kovács, Yasser Omar
### Paper: https://arxiv.org/abs/2112.04768

This repository includes the code for the QLP method proposed in the paper above, as well as example input and output files, organized in a single Mathematica notebook. A simple description of the method is presented in the Methods section of the paper which should simplify an implementation in any other coding language.

- Input: edge-list for a complex network which can have the nodes numbered from 0 to N-1 or from 1 to N
- Output: two edge-lists corresponding to predictions based in the even or odd components of the method ordered from best to worst according to the respective scores, as described in the paper. 

Note: the output edge lists have the nodes numbered from 1 to N.

## Link Prediction

Our knowledge of complex networks is often incomplete, and predicting new links can, for example, help us obtain detailed mappings of biological networks, or predict the time-evolution of social and technological networks, significantly impacting the development of new medicine and information technologies.

Link prediction methods take as input a graph $G(\mathcal{V},\mathcal{E})$, where $\mathcal{V}$ is the set of nodes with size $N=|\mathcal{V}|$ and $\mathcal{E}$ is the set of undirected links, and output a matrix of predictions $P\in\mathbf{R}^{N\times N}$ where each entry $p_{ij}$ is a score value quantifying the likelihood of a link existing between nodes $i$ and $j$. A popular approach to link prediction is to assume $P\sim A^k$ for some power $k$ of the adjacency matrix, or some combination of powers. It has been shown that in some networks prediction methods based on even powers or odd power perform differently. 

In our method we use Continuous-Time Quantum Walks to develop a quantum algorithm that outputs predictions from $P\sim \cos(At)$ and $P\sim \sin(At)$, encoding a combination of even or odd powers of $A$ weighted by the free-parameter $t$, representing the time of the quantum walk. Our algorithm is competetitive with other path-based link prediction methods and has the potential for a quantum-speedup in this problem.
