Dear Reviewers, this is an anonymous Git Repo for CMP Rebuttal. In this anonymous link, we include additional results.
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
![CleanShot 2025-04-01 at 03 08 53@2x](https://github.com/user-attachments/assets/a0e9d003-1df0-4739-9c3b-9b30dbb287c3)
Figure 3: ColoredMNIST using the Clip pretrained model + Linear Classifier. As we can see, our method is still the only one reaches to 70% accuracy, close to oracle performance (73%) with stable convergecne behaviour.

## 2. Waterbirds-CF
|               | Methods | In-domain validation & stopping criteria |              | Oracle validation & stopping criteria |              |
|---------------|---------|------------------------------------------|--------------|---------------------------------------|--------------|
|               |         | Test-Acc                                 | Ood Test-Acc | Test-Acc                              | Ood Test-Acc |
| REx           | NN      | 0.924                                    | 0.744        | 0.917                                 | 0.855        |
|               | Clip    | 0.891                                    | 0.617        | 0.878                                 | 0.729        |
| Fish          | NN      | 0.904                                    | 0.699        | 0.872                                 | 0.843        |
|               | Clip    | 0.900                                    | 0.744        | 0.869                                 | 0.805        |
| GroupDRO      | NN      | 0.923                                    | 0.765        | 0.907                                 | 0.842        |
|               | Clip    | 0.906                                    | 0.684        | 0.896                                 | 0.827        |
| IRM           | NN      | 0.940                                    | 0.769        | 0.920                                 | 0.849        |
|               | Clip    | 0.838                                    | 0.707        | 0.820                                 | 0.767        |
| ERM           | NN      | 0.917                                    | 0.767        | 0.917                                 | 0.767        |
|               | Clip    | 0.885                                    | 0.781        | 0.882                                 | 0.800        |
| ERM+Upweight  | NN      | 0.936                                    | 0.856        | 0.936                                 | 0.856        |
|               | Clip    | 0.889                                    | 0.795        | 0.882                                 | 0.829        |
| Ours          | NN      | 0.953                                    | 0.872        | 0.953                                 | 0.872        |
|               | Clip    | 0.900                                    | 0.774        | 0.870                                 | 0.853        |
| Ours+Upweight | NN      | 0.958                                    | 0.900        | 0.958                                 | 0.900        |
|               | Clip    | 0.864                                    | 0.812        | 0.854                                 | 0.860        |


## Ablation Study

### Sensitivity on $r$
![CleanShot 2025-04-01 at 16 42 45@2x](https://github.com/user-attachments/assets/2505dc34-7b6a-4ce4-bcdc-f0fbbd84be4c)
Figure 4: Sensitivity on $r$ of clip based linear Model on Waterbirds. The accuracy is on 320 random run with different learning rate from 1e-4 to 1e-2 and different $r$ from 2 to 512. The results show that the changing of $r$ is predicted by the theory. With large $r$ the average and worst-case accuracy is not as well and not as stable as smaller $r$, when $r$ reaches the best in domain accuracy around $r=30$, the worst-case accuracy is also reaches the maximum. When $r$ becomes smaller, the average accuracy stays same while the worst-case accuracy starts to degrade again due to overuse of spurious features.
### Sensitivity on the Noise in Counterfactual Pairs
Will be ready soon...
### Sensitivity on the Number of Counterfactual Pairs
![CleanShot 2025-04-01 at 19 21 25@2x](https://github.com/user-attachments/assets/0efa3e88-dc8c-46f7-937c-f1decbc5eeea)
Figure 6: The number of counterfactual vs the DG accuracy on ColoredMNIST using Clip + Linear model, the results show that with 32 pairs of counterfactual, the counterfactual pairs are not enough to help model get rid of spurious features, thus lead to overfitting (check in-domain accuracy here is over 75%, meaning the classificaton utilizes the spurious feature.). When we have 128 or 256 pairs of counterfactuals, the performance increase significantly and stay stable compared to 32 counterfactual pairs.
