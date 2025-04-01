Dear Reviewers, this is an anonymous Git Repo for CMP Rebuttal. In this anonymous link, we include additional results 
# Report
Here we report the extra experiments.
## 1. ColoredMNIST

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

![CleanShot 2025-03-31 at 21 23 25@2x](https://github.com/user-attachments/assets/5c34d80d-144c-4254-b755-93fc8884f6ca)
Figure 1: ColoredMNIST using the Linear model. Notice that IRM and REx are significantly osillated but the accuracy between training domains and test domains are inverse related.
![CleanShot 2025-03-31 at 21 25 33@2x](https://github.com/user-attachments/assets/b69ca6b8-c318-4b9d-8a61-00241558964e)
Figure 2: ColoredMNIST using the NN model. The NN structure is the same as the one used in DomainBed. 

## 2. Waterbirds-CF


## 3 CelebA-CF


### 3.2 Results

### 3.3 Convergence Curve

## Ablation Study
### Sensitivity on $r$
### Sensitivity on the Noise in Counterfactual Pairs
### Sensitivity on the Number of Counterfactual Pairs
# Reproduce our results.
Install the environment from ```requirements.txt```.



# References
[1] Arjovsky, Martin, et al. "Invariant risk minimization." arXiv preprint arXiv:1907.02893 (2019).

[2] Salaudeen, Olawale Elijah, Nicole Chiou, and Sanmi Koyejo. "On Domain Generalization Datasets as Proxy Benchmarks for Causal Representation Learning." NeurIPS 2024 Causal Representation Learning Workshop.

[3] Sagawa, Shiori, et al. "Distributionally robust neural networks for group shifts: On the importance of regularization for worst-case generalization." arXiv preprint arXiv:1911.08731 (2019).
