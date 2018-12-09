#DATA



##You divide your data into

**Training set** 
< keep training >

**Cross_validation (dev) set**
< find what model works best with your set >

**Test set**
< after finding the best model, test your set to see a unbiased estimate of your algorithm performance > 



##Data dividing

**before** 
< 60/20/20 >

**now**
< we use a much smaller percentage to dev and test, because we only need dev set to analyze wich model is better, and test is for only seeing how your algorithm is doing, so we use something like 98/1/1 or smaller percentages (ONLY FOR GREATER DATASETS) >


##Mismatched train/test distribution

**Training set** 
< we can use something like cat pictures from webpages, better quality, more professional >

**Dev an test sets**
< pictures of cats updated from an app, taken by a cellphone camera, lower quality, different positions, so you dont control the percentage >

< IMPORTANT FOR YOUR DEV AND TEST SETS NEED TO BE FROM THE SAME DISTRIBUTION > 

**IF YOU ONLY HAVE 2 SETS, YOU HAVE A TRAIN AND A DEV, NOT A TRAIN AND A TEST, BECAUSE YOU'RE OVERFITTING THE TEST SET**













