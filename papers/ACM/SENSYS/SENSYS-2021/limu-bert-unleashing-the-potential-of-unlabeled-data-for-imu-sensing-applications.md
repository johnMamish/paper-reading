## LIMU-BERT: Unleasing the Potential of Unlabelled data for IMU Sensing Applications
#### [[authors/Huntao Xu]], [[authors/Pengfei Zhou]], [[authors/Rui Tan]], [[authors/Mo Li]], [[authors/Guobin Shen]], 2021
#### Summary
Analysis of IMU data is often for mobile and IoT devices to understand their environment. Machine learning methods for IMU data work well, but labelled IMU data is difficult to generate; furthermore, labelled data generated for a specific user on a specific device might not be useful for training a model that will run on a different device. The authors use a neural network architecture from natural language processing to learn from unlabelled IMU data, which is plentiful.

BERT is a widely used neural network in natural language processing; it is capable of learning embeddings (lower-dimensional representations) of words from unlabelled data by training with "find the missing word" style "exercises". The authors of LIMU-BERT adapt BERT to operate on IMU data by reducing its complexity and changing training methods to operate on IMU data. LIMU-BERT trains by trying to fill in missing sections from IMU data logs. Like BERT, LIMU-BERT cannot classify data on its own. It merely learns lower-dimensional representations of IMU data traces, which can then be fed into a smaller classifier that can be trained off of much fewer labelled samples.

The authors test LIMU-BERT on 5 open-source labelled datasets, removing 99% of the labels. The authors compare a LIMU-BERT to other classifiers over many labelling rates. The performance of the other classifiers approaches LIMU-BERT for high labelling rates, but LIMU-BERT vastly outperforms other methods at lower labelling rates. They also show that the LIMU-BERT "frontend" can be used as a feature extractor for many different types of classifier.

#### Strengths
  - Use of technique from other area is well-motivated
  - Works with unlabelled data, which is plentiful
  - Learns embeddings which can be used with many different classifiers

#### Weaknesses
  - No discussion of how well this method will adjust to lower-energy systems
  - Weak data normalization discussion (3.2)
  - Limited discussion of LIMU-BERT's effectiveness when working with other sensors / platforms

#### Additional comments

#### What potential directions of future work remain (if any)?

#### Citations

Keywords: [[keywords/mobile-computing]], [[keywords/IMU]], [[keywords/human-activity-recognition]], [[deep-learning]]
Tags: (link to pages under the tags/ directory here)