Dear Reviewers, this is an anonymous Git Repo for CMP Rebuttal. In this anonymous link, we include additional results 
# Report
Here we report the extra experiments.
## 1. ColoredMNIST

|                  | Methods         | In-domain validation & stopping criteria |              | Oracle validation & stopping criteria |              |
|------------------|-----------------|------------------------------------------|--------------|---------------------------------------|--------------|
|                  |                 | Test-Acc                                 | Ood Test-Acc | Test-Acc                              | Ood Test-Acc |
| REx              | Linear          | 0.853                                    | 0.010        | 0.262                                 | 0.792        |
|                  | NN              | 0.850                                    | 0.099        | 0.518                                 | 0.491        |
|                  | Clip            | 0.850                                    | 0.098        | 0.669                                 | 0.604        |
| Fish             | Linear          | 0.852                                    | 0.010        | 0.521                                 | 0.500        |
|                  | NN              | 0.847                                    | 0.115        | 0.533                                 | 0.474        |
|                  | Clip            | 0.852                                    | 0.094        | 0.483                                 | 0.578        |
| GroupDRO         | Linear          | 0.853                                    | 0.101        | 0.498                                 | 0.233        |
|                  | NN              | 0.853                                    | 0.102        | 0.499                                 | 0.498        |
|                  | Clip            | 0.851                                    | 0.114        | 0.827                                 | 0.216        |
| IRM              | Linear          | 0.852                                    | 0.105        | 0.429                                 | 0.679        |
|                  | NN              | 0.725                                    | 0.103        | 0.728                                 | 0.642        |
|                  | Clip            | 0.832                                    | 0.094        | 0.626                                 | 0.515        |
| ERM              | Linear          | 0.852                                    | 0.103        | 0.842                                 | 0.157        |
|                  | NN              | 0.843                                    | 0.153        | 0.799                                 | 0.313        |
|                  | CMP-Clip        | 0.852                                    | 0.093        | 0.753                                 | 0.253        |
| Ours             | Linear          | 0.658                                    | 0.645        | 0.658                                 | 0.645        |
|                  | NN              | 0.737                                    | 0.675        | 0.721                                 | 0.691        |
|                  | CMP-Clip        | 0.742                                    | 0.694        | 0.734                                 | 0.711        |
| Na\’ive baseline | Random Guessing | 0.500                                    | 0.500        | 0.500                                 | 0.500        |
|                  | Theory Oracle   | 0.750                                    | 0.750        | 0.750                                 | 0.750        |
|                  | ERM Oracle      | 0.735                                    | 0.730        | 0.735                                 | 0.730        |

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
