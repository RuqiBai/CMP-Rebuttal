Dear Reviewers, this is an anonymous Git Repo for CMP Rebuttal. In this anonymous link, we include additional results.
# Report
## Our practical algorithm
![CleanShot 2025-04-08 at 17 44 46@2x](https://github.com/user-attachments/assets/ed6d4667-0c9b-4e1e-b48e-d40d2754658c)

Algorithm 1: Our practical algorithm uses Projected Gradient Descent (PGD) to constrain the model parameters to lie within the invariant subspace. This is achieved by projecting the parameters onto the orthogonal complement of the subspace spanned by the columns of the left singular vectors from the r-truncated Singular Value Decomposition (SVD) of the estimated counterfactual difference.
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
|                  | Clip        | 0.852                                    | 0.093        | 0.753                                 | 0.253        |
| CMP  (Ours)      | Linear          | 0.658                                    | 0.645        | 0.658                                 | 0.645        |
|                  | NN              | 0.737                                    | 0.675        | **0.721**                                 | **0.691**        |
|                  | Clip        | 0.742                                    | 0.694        | **0.734**                                 | **0.711**        |
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
| CMP  (Ours)           | NN      | 0.953                                    | 0.872       | 0.953                                | 0.872        |
|               | Clip    | 0.900                                    | 0.774        | 0.870                                | 0.853      |
| CMP+Upweight (Ours) | NN      | **0.958**                                    | **0.900**       | **0.958**                                 | **0.900**        |
|               | Clip    | **0.864**                                    | **0.812**        | **0.854**                                 | **0.860**        |


## Ablation Study

### Sensitivity on $r$
![CleanShot 2025-04-01 at 16 42 45@2x](https://github.com/user-attachments/assets/2505dc34-7b6a-4ce4-bcdc-f0fbbd84be4c)
Figure 4: Sensitivity to $r$ of the CLIP-based Linear model on Waterbirds. Accuracy is reported over 320 random runs with varying learning rates (from 1e-4 to 1e-2) and different values of $r$ (ranging from 2 to 512). The results show that changes in $r$ align with theoretical predictions. With large $r$, both average and worst-case accuracy are lower and less stable compared to smaller values of $r$. When $r$ approaches its optimal value (around $r=30$), the worst-case accuracy also reaches its peak. However, as $r$ decreases further, the average accuracy remains stable while the worst-case accuracy declines again—likely due to increased reliance on spurious features.
### Sensitivity on the Noise in Counterfactual Pairs
![CleanShot 2025-04-01 at 19 34 18@2x](https://github.com/user-attachments/assets/ac2b060e-0b74-45a1-9a96-f6ec1511f09e)
Figure 5: The number of noisy counterfactual pairs vs. DG accuracy on ColoredMNIST using the CLIP + Linear model. Different convergence curves correspond to varying numbers of incorrect counterfactual pairs out of 256 total, as indicated in the legend. The incorrect counterfactual pairs are conditionally matched samples (i.e., sharing the same label Y) rather than true counterfactuals. The results show that if 1/4 of the counterfactuals are incorrect, the model's performance degrades to (almost) random guessing.
### Sensitivity on the Number of Counterfactual Pairs
![CleanShot 2025-04-01 at 19 21 25@2x](https://github.com/user-attachments/assets/0efa3e88-dc8c-46f7-937c-f1decbc5eeea)
Figure 6: The number of counterfactuals vs. DG accuracy on ColoredMNIST using the CLIP + Linear model. The results show that with 32 counterfactual pairs, the number of pairs is insufficient for the model to eliminate spurious features, leading to overfitting (as indicated by an in-domain accuracy over 75%, meaning the classification relies on spurious features). However, when using 128 or 256 counterfactual pairs, the performance increases significantly and remains stable compared to the 32 counterfactual pairs.
