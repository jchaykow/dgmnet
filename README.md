# Deep Generative Modeling For Networks

## Introduction
This repository contains for the code for the RAND Initiated Research (RIR) project "Deep Generative Modeling for Networks". The code consists of multiple Jupyter notebooks, each implementing a different workflow:
  1. `NDSSL Data Processing Notebook.ipynb`: loads and processes the NDSSL data used throughout the project.
  2. `Node Classification.ipynb`: implements a simple node classification example on the NDSSL dataset.
  3. `Link Prediction.ipynb`: implements a Graph Autoencoder (GAE) approach towards link prediction, again on the NDSSL dataset.
  4. `Graph Generation.ipynb`: implements the Graph Generation by Iterated Link Prediction approach towards generating artificial graphs. This code uses the results from running the link prediction notebook.
  5. `Generated Graph Analysis.ipynb`: analyzes and plots the results of running the graph generation notebook.

Please direct any questions to <hartnett@rand.org>.

![mlp_vs_gnn.png](mlp_vs_gnn.png "Graph Neural Networks")

## Installation
The workflows are coded in Python, and heavily utilize the packages [*Networkx*](https://networkx.github.io/) and [*Pytorch Geometric*](https://pytorch-geometric.readthedocs.io/en/latest/). These will need to be installed, along with the many other packages that are used. We recommend installing within a conda environment:

```
git clone https://code.rand.org/hartnett/dgmnet.git
cd dgmnet
conda create --name dgmnet
conda activate dgmnet
```

Next, install [Pytorch](https://pytorch.org/). The instructions for a CUDA 10.2 GPU is:

```
conda install pytorch torchvision cudatoolkit=10.2 -c pytorch
```

Then, install Pytorch Geometric:

```
pip install torch-scatter==latest+${CUDA} -f https://pytorch-geometric.com/whl/torch-1.6.0.html
pip install torch-sparse==latest+${CUDA} -f https://pytorch-geometric.com/whl/torch-1.6.0.html
pip install torch-cluster==latest+${CUDA} -f https://pytorch-geometric.com/whl/torch-1.6.0.html
pip install torch-spline-conv==latest+${CUDA} -f https://pytorch-geometric.com/whl/torch-1.6.0.html
pip install torch-geometric
```
where ${CUDA} should be replaced by either cpu, cu92, cu101 or cu102 depending on your PyTorch installation. Finally, install the other packages via:
```
python setup.py install
```

### NDSSL Data
The code expects to find the NDSSL data in the parent directory. The website hosting this data seems to have been taken down, but RAND retains a copy of the data which can be made available upon request.