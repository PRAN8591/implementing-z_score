# implementing-z_score

import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline

dataset = [37368763,2573736743,37676,3578757,3673878,245727,376768738,38738738738,8738738737,3573873873,243733367]

plt.hist(dataset)

outliers = []

def detect_outliers(data):
  threshold = 3 #3std deviation
  mean=np.mean(data)
  std=np.std(data)

  for i in data:
    z_score = (i-mean)/std
    if np.abs(z_score)>threshold:
      outliers.append(i)

  return outliers

detect_outliers(dataset)
	38738738738 <-- outliers
