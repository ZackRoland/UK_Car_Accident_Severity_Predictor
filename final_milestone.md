# Final Milestone:
## Model Evaluation:
From figure 1 we see as K increases, the inertia of the test and train sets decrease indicating tightness of clusters. The train is consistently higher than the test inertia but the difference between test and train from 10 is very minimal in comparison to the 2 clusters. Figure 2 shows that the shillouette  scores typically range from 0.45-0.55 for all K except k=6,7 where there is a major dip down to 0.39. This score describes the stability of clusterings so that significant dip means that in that range the clusters are less separated and contain some overlap. The curves for our test and train overlap almost exactly demonstrating that we have reproducibility with our results.

<ins>Figure 1:</ins> Test vs Train inertia (PCA + KMeans)

<img width="389" height="289" alt="Image" src="https://github.com/user-attachments/assets/7904e396-a4c6-410b-a7d3-62f12e48eda6" />

<ins>Figure 2:</ins> Test vs Train silhouette scores (PCA + KMeans)

<img width="389" height="289" alt="Image" src="https://github.com/user-attachments/assets/65b49e6e-a02d-414c-a7f9-6a3857765682" />

## Fitting Analysis
<ins>Figure 3:</ins> The Fitting Curve

<img width="499" height="377" alt="Image" src="https://github.com/user-attachments/assets/5157cfd3-28ae-47ce-b4a8-5eaaa3b0741e" />

Our model lies within the ideal range of model complexity as the silhouette isn’t too low so we're not in the underfit region but not too right to where added complexity is hurting us. Our next model we wanted to try out was hierarchical since it will make the outliers as its its own clusters and islands and make it so that the clusters make more sense, the thing is it is too memory intensive (around 8 terabytes) so we weren’t able to try that this go around.
## Conclusion
Our second model highlighted some important challenges in predicting crash severity. While many cases were classified correctly, we observed both false positives (less severe crashes predicted as severe) and false negatives (severe crashes predicted as less severe). The false negatives are especially concerning, since underestimating crash severity has more serious real-world implications. These results suggest that while the model captures some useful patterns, its reliability is limited without further refinement.

Beyond prediction errors, the overall clustering analysis showed that reducing the dataset to just two principal components limited our ability to separate classes effectively. The silhouette scores indicated instability at certain values of K, and data imbalance further hindered performance. Although the model sits in a reasonable range of complexity, improvements could be made through better handling of class imbalance, exploring additional features, and testing alternative methods such as hierarchical or density-based clustering. These steps would likely improve cluster separation and reduce misclassification rates.
