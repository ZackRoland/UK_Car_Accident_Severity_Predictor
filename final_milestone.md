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

Our second model kind of showed us that separating our data with just 2 principal components was difficult and didn’t contain as much information as we really needed to create distinct, separate clusters. The explained variance ratio for the two principal components were 0.143 and 0.110, meaning that our PCA only contained around 25% of the variance of the data, meaning that it couldn’t capture a significant amount of the information in the data. Though a factor contributing to this could’ve been the data imbalance already present in the dataset as around 85% of the data points were 1 of the 3 possible classes, which could make it harder to really separate the clusters. Another issue was interpreting what each cluster really meant as it didn’t follow the accident severity we were doing before with classification because if you created a confusion matrix, it would there were low accuracies across the board for the positives, and taking a look at the classifcation report, the accuracy was 0.34, so basically random. This means we would need to do more analyzing of the data and plotting what data points have what feature values to understand what each cluster really grouped.

Beyond prediction errors, the overall clustering analysis showed that reducing the dataset to just two principal components limited our ability to separate classes effectively. The silhouette scores indicated instability at certain values of K, and data imbalance further hindered performance. Although the model sits in a reasonable range of complexity, improvements could be made through better handling of class imbalance, exploring additional features, and testing alternative methods such as hierarchical or density-based clustering. These steps would likely improve cluster separation and reduce misclassification rates. We could gain more information by increasing the dimensions from just 2, however, this would eliminate the visual aspects of the clustering and could make it harder for use to intuitively understand what is happening. We could also try to handle the data imbalance with something like SMOTE to see how our clustering would look like after that.

<img width="476" height="492" alt="image" src="https://github.com/user-attachments/assets/37b85ccf-d038-4304-8ebe-165bace2d121" />


