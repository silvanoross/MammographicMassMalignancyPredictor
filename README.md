# MammographicMassMalignancyPredictor
Creates a Random Forest Regressor and Mulit-Layer Perceptron model then explains individual predictions with LimeTabularExplainer.

I chose a prediction instance where the two models were discrepant with respect to the prediction of a mass being malignant.

##### For the Random Forest Classifier:

Here we have a specific instance where the two models had a difference in predicted probability greater than 0.4 resulting in discrepant predictions:

*The ground truth at row 152 is: 0* 
*The MLP predicted probability: 0.412*
*The RF Classifier predicted probability: 0.814*

![image](https://github.com/silvanoross/MammographicMassMalignancyPredictor/assets/28959674/0a2b77b5-8159-4f07-9927-8fd7d8a2c82b)

The Random Forest Classifier put a heavy partial probability on the BI_RADS between 4 and 5 as the main predictor. It then ranked the next two top features as shape not being oval and the margin not being circumscribed to be important in predicting malignancy.

##### For the Multi-Layer Perception Model

![image](https://github.com/silvanoross/MammographicMassMalignancyPredictor/assets/28959674/17302e08-ce01-4c20-b2ef-93f6f2c6786b)

We can see a marketed difference in feature importances used by each model. The MLP has a much more balanced partial prediction distributions for each feature and puts the shape not being an oval, the shape being irregular and the age being between 45 and 57 as the top 3 features that lead to its prediction. It predicted this instance to be positive even though it was negative.

##### $$R^2$$ For the two models based on LimeTabularExplainer internal Linear regression baseline model
*The R2 for the RF is: 0.840* 
*The R2 for the MLP is: 0.163*

