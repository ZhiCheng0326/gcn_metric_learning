# Metric Learning using Graph Convolutional Neural Networks (GCNs)

The code in this repository implements a metric learning approach for irregular
graphs. The method has been applied on brain connectivity networks and is
presented in our papers:

* Sofia Ira Ktena, Sarah Parisot, Enzo Ferrante, Martin Rajchl, Matthew Lee,
  Ben Glocker, Daniel Rueckert, [Metric learning with spectral graph convolutions on brain connectivity networks](https://www.sciencedirect.com/science/article/pii/S1053811917310765), NeuroImage, 2018.

* Sofia Ira Ktena, Sarah Parisot, Enzo Ferrante, Martin Rajchl, Matthew Lee,
  Ben Glocker, Daniel Rueckert, [Distance Metric Learning using Graph Convolutional
  Networks: Application to Functional Brain Networks](https://arxiv.org/abs/1703.02161), Medical Image Computing
  and Computer-Assisted Interventions (MICCAI), 2017.

<p align="center">
<img src="http://www.doc.ic.ac.uk/~sk1712/graph_construction.png" alt="overview" width="800"/>
</p>
<p align="center">
<img src="http://www.doc.ic.ac.uk/~sk1712/overview_metric_learning.png" alt="overview" width="800"/>
</p>

The code is released under the terms of the [MIT license](LICENSE.txt). Please
cite the above paper if you use it.

There is also implementations of the filters and graph coarsening used in:
* Michaël Defferrard, Xavier Bresson, Pierre Vandergheynst, [Convolutional Neural
  Networks on Graphs with Fast Localized Spectral Filtering](https://arxiv.org/abs/1606.09375), Neural
  Information Processing Systems (NIPS), 2016.

The implementaton of the global loss function is based on:
* Vijay Kuma, Gustavo Carneiro, Ian Reid, [Learning Local Image Descriptors with Deep
  Siamese and Triplet Convolutional Networks by Minimising Global Loss Functions](https://arxiv.org/abs/1512.09272),
  IEEE Conference on Computer Vision and Pattern Recognition (CVPR), 2016.

## Installation
### Run from Google Colab
Open `gcn_metric_learning.ipynb` and run all

### Run in other environments
1. Clone this repository. Then:
   ```sh
   cd gcn_metric_learning
   ```

2. Install the dependencies. Please edit `requirements.txt` to choose the
   TensorFlow version (CPU / GPU, Linux / Mac) you want to install, or install
   it beforehand. (This code runs on tensorflow 1.x)
   ```sh
   pip install -r requirements.txt  # or make install
   ```
3. The root folder in fetch_data.py (line 27) and ABIDEParser.py (line 33) has to be updated to the folder were the data will be stored.

4. To download ABIDE datasets, obtain missing `subject_IDs.txt` and `mat` file,
   by using script from [parisots](https://github.com/parisots/population-gcn), run code below:
   ```sh
   python fetch_data.py
   ```

5. Run the code
   ```sh
   python main_all_sites.py
   ```


## Using the model

To use our siamese graph ConvNet on your data, you need:

1. pairs of graphs as matrices where each row is a node and each column is a node feature,
2. a class label for each graph,
3. an adjacency matrix which provides the structure as a graph; the same structure
   will be used for all samples.

Please get in touch if you are unsure about applying the model to a different
setting.
