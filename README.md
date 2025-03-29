Dear Reviewer, this is an anonymous Git Repo for CMP Rebuttal. In this anonymous link, we include additional code (as well as the original code) for reproducing the results from paper. 
# Report
Here we report the extra experiments.
## ColoredMNIST
ColoredMNIST was first introduced in *Invariant Risk Minimization* [1]. Despite the simplicity of the image contents (handwritten digits), it remains one of the most challenging domain generalization benchmarks due to following reasons [2]:
1. the strong correlation between the spurious feature (color) and the prediction label $Y$;
2. the accuracy drop on the inverse line: the test domain exhibits an inverse correlation between the spurious feature and the label compared to the training domains.
### Experiment Setting
We follow the dataset creation from [1], and conduct 160 Bayesian Hyperparameter Optimization with following range.
#### ERM

#### IRM

#### REx

#### Fish

### Results


# Reproduce our results.
First please use conda to install the env from ```requirements.txt```.



# References
[1] Arjovsky, Martin, et al. "Invariant risk minimization." arXiv preprint arXiv:1907.02893 (2019).
[2] Salaudeen, Olawale Elijah, Nicole Chiou, and Sanmi Koyejo. "On Domain Generalization Datasets as Proxy Benchmarks for Causal Representation Learning." NeurIPS 2024 Causal Representation Learning Workshop.
