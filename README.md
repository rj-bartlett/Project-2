### Project2 Write-Up

#### Penalized Logistic Regression ROC curves
 

This model was the best at correctly predicting if the wealth was 5, followed by 1, 2, 4, and 3 respectively. For this model, I chose a penalty of .0001 because it was the lowest penalty score, and it also had the highest area under the curve when compared to the other 14 penalties. It also had the highest overall mean value. From the results of the ROC curves, I would conclude that this model was more effective at predicting those with wealth 1 and wealth 5 because the curves deviated significantly from the central dotted lines which corresponds to a higher ability to correctly predict these values given the input variables. It was not as effective at predicting those at the other levels of wealth because the ROC curve was close to the central dotted line. 
Random Forest ROC curves
 

Like the penalized logistic regression, the random forest had a very similar result with the households with level 1 and 5 wealth were able to be successfully predicted at a higher rate than random chance because the ROC shape was curved and above the diagonal. Because the other curves were near the diagonal, it is reasonable to assume that these remaining graphs are not able to successfully predict the household’s wealth for 2,3 and 4 much better than random chance. 
When comparing the Random Forest to the Penalized Linear Regression, it can be observed from the plot below the results are fairly similar with a lot of overlap.  
A plot I thought would show the relationship between the variables and the potential for understanding which variable had a higher weight would be the normalized heatmap of the original dataset. The variables that had higher correlation would then have higher weights. 




 







#### Logistic Regression Model

WEALTH = 1
{'accuracy': 0.80963945, 'average_loss': 0.45066097, 'loss': 0.45066097, 'global_step': 17370}
AUC = .674
 
Interpretation: Slightly curved above the straight diagonal line through the origin which means that this curve can differentiate between the two categories of level 1 wealth and other better than by random chance. 









WEALTH = 2
{'accuracy': 0.81363344, 'average_loss': 0.46762374, 'loss': 0.46762374, 'global_step': 17370}
AUC = .623

 

Interpretation: This curve is closer to the diagonal than when wealth was in category 1, which means that the model is worse at correctly identifying the wealth level of a given input. It is closer to random chance when compared to the model with wealth at level 1. 









WEALTH = 3
{'accuracy': 0.8304728, 'average_loss': 0.4532691, 'loss': 0.4532691, 'global_step': 17370}
AUC: .547
 
Interpretation: This curve is very linear and has a AUC very close to .5 which means that this model is basically predicting the output at the same level as randomly assigning the output. 











WEALTH = 4
{'accuracy': 0.80764246, 'average_loss': 0.48824093, 'loss': 0.48824093, 'global_step': 17370}
AUC: .561
 
Interpretation: This model is better than the above model at predicting the outcome correctly. However, it is still not very capable of successfully predicting and is close to the same results of random chance. 











WEALTH = 5
{'accuracy': 0.7720747, 'average_loss': 0.5066069, 'loss': 0.5066069, 'global_step': 17370}
AUC: .711
 


Interpretation: This curve is significantly above the straight diagonal line and has a AUC greater than .7 which means that this model is able to successfully predict a family of wealth level 5 with the inputs at a higher rate than randomly assigning families a level 5 wealth. 









#### Gradient Boosting Model

WEATLH = 5
-	accuracy                  0.768351
-	accuracy_baseline         0.742768
-	auc                       0.766500
-	auc_precision_recall      0.531218
-	average_loss              0.463392
-	label/mean                0.257232
-	loss                      0.463392
-	precision                 0.703608
-	prediction/mean           0.262834
-	recall                    0.171842
-	global_step             100.000000
-	AUC: 				   0.768
 
 
Interpretation: Given the AUC score and shape of the ROC curve, I believe this model can successfully predict households with the highest ranking of wealth (5) better than randomly distributed. But, since the curve levels off at the top, I am suspicious and think the ability to successfully predict is actually lower than what the AUC led me to believe. 

WEALTH = 4
-	accuracy                  0.807696
-	accuracy_baseline         0.807696
-	auc                       0.630428
-	auc_precision_recall      0.244910
-	average_loss              0.457933
-	label/mean                0.192304
-	loss                      0.457933
-	precision                 0.000000
-	prediction/mean           0.202125
-	recall                    0.000000
-	global_step             100.000000
-	AUC:     			  0.643
Interpretation: Although the AUC score is above 0.5, the ROC curve is pretty linear which would leave me to believe that this model is not very good at predicting wealth level 4 from the other levels of wealth. 


WEALTH = 3
-	accuracy                  0.830149
-	accuracy_baseline         0.830149
-	auc                       0.645750
-	auc_precision_recall      0.230527
-	average_loss              0.427792
-	label/mean                0.169851
-	loss                      0.427792
-	precision                 0.000000
-	prediction/mean           0.176032
-	recall                    0.000000
-	global_step             100.000000
-	AUC: 				   0.668

Interpretation: This model is generally successful at predicting the households with level 3 wealth to the others, but is worse than the model with level 2 wealth shown below. But this curve seems to be pretty linear which makes me believe that it is not as accurate as the AUC score would lead me to believe.

WEALTH = 2
-	accuracy                  0.816764
-	accuracy_baseline         0.816764
-	auc                       0.711736
-	auc_precision_recall      0.300615
-	average_loss              0.432068
-	label/mean                0.183236
-	loss                      0.432068
-	precision                 0.000000
-	prediction/mean           0.193243
-	recall                    0.000000
-	global_step             100.000000
-	AUC: 				   0.735 
 
Interpretation: The model was generally successful at predicting the wealth level 2 from the others successfully due to the ROC curve and AUC score. 


WEALTH = 1
-	accuracy                  0.999946
-	accuracy_baseline         0.811421
-	auc                       1.000000
-	auc_precision_recall      1.000000
-	average_loss              0.082747
-	label/mean                0.188579
-	loss                      0.082747
-	precision                 1.000000
-	prediction/mean           0.192827
-	recall                    0.999714
-	global_step             100.000000
-	AUC: 				   1.000000
 
 
Interpretation: This model was able to successfully predict every single household’s wealth correctly. 


#### Conclusion:
From the ROC curves and AUC scores, the boosted models had the best ability to successfully predict correct outcomes at the highest rate. But, since the boosted model had a 100% accuracy for level 1 wealth, there might have been a mistake along the way. Generally speaking, it was interesting to see that the models were able to successfully predict households at level 1 and 5 wealth significantly better than those at the other levels. I think this may be because they are the two extremes so there is probably a larger separation in the really impoverished and really well-off households, whereas the families in the middle are harder to distinguish from others in middle class. This would explain why the middle levels of wealth had a AUC score of closer to 0.5







