# Note for learning Graph Anomaly Detection

## Related Paper

### Rethinking Graph Neural Networks for Anomaly Detection

Paper Link: [[2205.15508] (arxiv.org)](https://arxiv.org/abs/2205.15508) / [ICML2022](https://icml.cc/media/icml-2022/Slides/17968_le6HH92.pdf)

Code Link: [squareRoot3/Rethinking-Anomaly-Detection: ICML 2022 https://arxiv.org/abs/2205.15508 (github.com)](https://github.com/squareRoot3/Rethinking-Anomaly-Detection)

Motivation: There are few works on spectral domain to think about this task. They discover a special phenomenon that the spectral energy distribution concentrates less in low frequencies and more in high frequencies if the degree of anomaly becomes larger.

Method:

It builds a series of band-pass filters considering Betta distribution which is susally shown in CV, and puts they to apply wavelet transform. In this pattern, it aggregates all these filtering results instead of recursive message passing in normal GNN.


### Raising the Bar in Graph-level Anomaly Detection

Paper Link: [[2205.13845] (arxiv.org)](https://arxiv.org/abs/2205.13845) / [(ijcai.org)](https://www.ijcai.org/proceedings/2022/0305.pdf)

Code Link: [boschresearch/GraphLevel-AnomalyDetection: Code of the paper 'Raising the Bar in Graph-level Anomaly Detection' published in IJCAI-2022 (github.com)](https://github.com/boschresearch/graphlevel-anomalydetection)

Motivation: The studies of Graph level AD are few, which have multiple applications for this task, such as crime network.

Related work: previous work (OCGIN) have performance filp problem (performance is worse than the random on at least one exprimental variant)

Realted Topic: one class classification(OOC, learn only one class information)

Method:

Design two loss. One aims to each graph close to reference graph while they are not similar to each other. Another is designed from popular solution in OOC problem, which is map into minimal hypersphere containing all normal training data.

## Classification for Graph Anomaly Detection Mothods by GNN

### Attention based

To correlate different neighbors through various views

### Resampling based

To aggregate neighborhood information selectively

### Auxiliary losses

To enhance the network training power

### Graph signal

Anomaly will make the graph signal properties change, such as the distribution of low and high frequecy from spectral domain

## Dataset and Expriment

### Raising the Bar in Graph-level Anomaly Detection

from TUDataset

Expriment setting: 

10 folds cross validation

Compared baseline: WLK PK G2V FGSD OCGIN

Metric: AUC

### Rethinking Graph Neural Networks for Anomaly Detection

YelpChi, Amazon, T-Finance, T-Social

Expriment setting:

40% training set, rest 1:2 for validation: test(supervised)

1% training set, rest 1:2 for validation: test(semi-supervised)

10 runs

Baselines:

MLP, SVM, GCN, GAT, GIN, GraphSAGE, GWNN

GraphConsis, CAREGNN, PC-GNN

Metric: F1-macro, AUC
