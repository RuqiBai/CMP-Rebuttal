Dear Reviewer, this is an anonymous Git Repo for CMP Rebuttal. In this anonymous link, we include additional code (as well as the original code) for reproducing the results from paper. 
# Report
Here we report the extra experiments.
## ColoredMNIST
ColoredMNIST was first introduced in *Invariant Risk Minimization* [1]. Despite the simplicity of the image contents (handwritten digits), it remains one of the most challenging domain generalization benchmarks due to following reasons [2]:
1. the strong correlation between the spurious feature (color) and the prediction label $Y$;
2. the accuracy drop on the inverse line: the test domain exhibits an inverse correlation between the spurious feature and the label compared to the training domains.
### Results
|                  | Methods         | In-domain validation & stopping criteria |              | Oracle validation & stopping criteria |              |
|------------------|-----------------|------------------------------------------|--------------|---------------------------------------|--------------|
|                  |                 | Test Acc                                 | Ood Test Acc | Test Acc                              | Ood Test Acc |
| REx              | Linear          | 0.853                                    | 0.010        | 0.2618                                | 0.792        |
|                  | NN              |                                          |              | 0.715                                 | 0.685        |
|                  | Clip            |                                          |              |                                       |              |
| Fish             | Linear          |                                          |              |                                       |              |
|                  | NN              |                                          |              |                                       |              |
|                  | Clip            |                                          |              |                                       |              |
| GroupDRO         | Linear          |                                          |              | 0.825                                 | 0.231        |
|                  | NN              |                                          |              |                                       |              |
|                  | Clip            |                                          |              |                                       |              |
| IRM              | Linear          | 0.852                                    | 0.105        | 0.4292                                | 0.6782       |
|                  | NN              | 0.725                                    | 0.103        | 0.728                                 | 0.642        |
|                  | Clip            |                                          |              | 0.626                                 | 0.515        |
| ERM              | Linear          | 0.852                                    | 0.103        | 0.842                                 | 0.157        |
|                  | NN              | 0.843                                    | 0.153        | 0.799                                 | 0.313        |
|                  | CMP-Clip        |                                          |              | 0.87x                                 | 0.2x         |
| Ours             | Linear          |                                          |              | 0.682                                 | 0.682        |
|                  | NN              |                                          |              | 0.71                                  | 0.70x        |
|                  | CMP-Clip        |                                          |              | 0.742                                 | 0.724        |
| Na\’ive baseline | Random Guessing |                                          |              | 0.500                                 | 0.500        |
|                  | Theory Oracle   |                                          |              | 0.750                                 | 0.750        |
|                  | ERM Oracle      |                                          |              | 0.735                                 | 0.730        |


Here's the convergence curve


### Experiment Setting
We follow the dataset creation from [1], and conduct 160 Bayesian Hyperparameter Optimization with following range.
#### CMP
{"lr": 10^[-5, -3], "penalty_weight": 10^[0,5], "r": 2^[4,8]}
#### ERM
{"lr": 10^[-5, -3]}
#### IRM
{"lr": 10^[-5, -3], "penalty_weight": 10^[0, 5], "penalty_anneal_iters": [50, 250], "weight_decay": 10^[-4, -2]}
#### REx
{"lr": 10^[-5, -3], "penalty_weight": 10^[0, 5], "penalty_anneal_iters": [50, 250], "weight_decay": 10^[-4, -2]}
#### Fish
{"lr": 10^[-5, -3], "fish_step": 10^[-4,-1], "weight_decay": 10^[-4, -2]}}
#### GroupDRO
{"lr": 10^[-5, -3], "eta": 10^[-4,-1], "weight_decay": 10^[-4, -2]}}

## Waterbirds-CF
Waterbirds is first introduced in GroupDRO[3]. In the dataset during training, waterbirds are highly correlated to waterbirds background 

TODO: Here.
### Experiment Setting
The hyperparamter is selected according to the corresponding best model parameter reported.
#### CMP
{"lr": 10^[-5, -3], "penalty_weight": 10^[0,5], "r": 2^[4,8]}
#### ERM
{"lr": 10^[-5, -3]}
#### IRM
{"lr": 10^[-5, -3], "penalty_weight": 10^[0, 5], "penalty_anneal_iters": [50, 250], "weight_decay": 10^[-4, -2]}
#### REx
{"lr": 10^[-5, -3], "penalty_weight": 10^[0, 5], "penalty_anneal_iters": [50, 250], "weight_decay": 10^[-4, -2]}
#### Fish
{"lr": 10^[-5, -3], "fish_step": 10^[-4,-1], "weight_decay": 10^[-4, -2]}}
#### GroupDRO
{"lr": 10^[-5, -3], "eta": 10^[-4,-1], "weight_decay": 10^[-4, -2]}}

# Reproduce our results.
First please use conda to install the env from ```requirements.txt```.
<img src="[![CleanShot 2025-03-29 at 14 26 06@2x](https://github.com/user-attachments/assets/e4b9bcf7-51aa-4b79-8d8c-f9a6724e3514)
](https://github.com/user-attachments/assets/e4b9bcf7-51aa-4b79-8d8c-f9a6724e3514)" width="300" height="200">


# References
[1] Arjovsky, Martin, et al. "Invariant risk minimization." arXiv preprint arXiv:1907.02893 (2019).
[2] Salaudeen, Olawale Elijah, Nicole Chiou, and Sanmi Koyejo. "On Domain Generalization Datasets as Proxy Benchmarks for Causal Representation Learning." NeurIPS 2024 Causal Representation Learning Workshop.
[3] Sagawa, Shiori, et al. "Distributionally robust neural networks for group shifts: On the importance of regularization for worst-case generalization." arXiv preprint arXiv:1911.08731 (2019).
