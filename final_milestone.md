# Final Milestone:
## Model Evaluation:
Figure 1: As K increases, the inertia of the test and train sets decrease indicating tightness of clusters. The train is consistently higher than the test inertia but the difference between test and train from 10 is very minimal in comparison to the 2 clusters.


Figure 2: The scores typically range from 0.45-0.55 for all K except k=6,7 where there is a major dip down to 0.39. This score describes the stability of clusterings so that significant dip means that in that range the clusters are less separated and contain some overlap. The curves for our test and train overlap almost exactly demonstrating that we have reproducibility with our results.

## Fitting Analysis
3: Answer the questions: Where does your model fit in the fitting graph? and What are the next models you are thinking of and why? (3 points)

Our model lies within the ideal range of model complexity as the silhouette isn’t too low so we're not in the underfit region but not too right to where added complexity is hurting us. Our next model we wanted to try out was hierarchical since it will make the outliers as its its own clusters and islands and make it so that the clusters make more sense, the thing is it is too memory intensive (around 8 terabytes) so we weren’t able to try that this go around.
## Conclusion
5. Conclusion section: What is the conclusion of your 2nd model? What can be done to possibly improve it? Note: The conclusion section should be it's own independent section. i.e. Methods: will have models 1 and 2 methods, Conclusion: will have models 1 and 2 results and discussion. (3 points)
	Our second model kind of showed us that separating our data with just 2 principal components was difficult. Another factor contributing to this could’ve been the data imbalance
6. Provide predictions of correct and FP and FN from your test dataset. (2 point)
