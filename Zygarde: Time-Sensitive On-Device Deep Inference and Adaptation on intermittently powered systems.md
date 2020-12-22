## Zygarde: Time-Sensitive On-Device Deep Inference and Adaptation on Intermittently-Powered Systems
## Bashima Islam, Shariar Nirjon

#### Summary
For intermittently-powered systems to realize their capacity to improve healthcare, enviornmental monitoring, and xxx, their capacity to perform on-board classification needs to improve. DNNs are the state-of-the-art in classification, but they don't scale well to intermittently-powered systems because they are power, computation, and memory intensive; [some work](https://dl.acm.org/doi/abs/10.1145/3297858.3304011) has already adapted DNN techniques to intermittently-powered systems, but these techniques don't address deadlines for classifications. Zygarde adapts techniques from Lucia's SONIC software system to deal with intermittency, but they use a k-means clustering based early-exit strategy for DNN evaluation; they introduce a scheduler that uses early-exit to dynamically trade off accuracy for power consumption when forecasted power availability is low. Zygarde is able to increase the likelihood that a job will finish before its deadline without sacrificing significant amounts of classification accuracy. I'm interested in seeing how Zygarde could be used to predict when interesting events are unlikely to happen, so the system's sampling rate can drop and more power can be conserved.

#### Strengths
  * It's a good concept...
  * Natural extension of SONIC et. al

#### Weaknesses
  * Doesn't provide benefits for systems without realtime deadlines AFAIK
  *

#### Additional comments
Can Zygarde benefit systems where there are no real-time deadlines for the completion of a classificaton? What about data collection systems where on-board classification is just being used to improve power consumption? Does the

#### What potential directions of future work remain (if any)?


#### Points for clarification
  * Is the "agile DNN + k-means clustering" early-exit thing a concept pioneered by Islam & Nirjon? <br/>
    Looks like it isn't. Not sure where the idea comes from originally though.
  * How do they estimate expected inference accuracy early on? <br/>
    This is discussed in section 4.1: "Dynamic Partitioning and Utility"
