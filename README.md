                            Network Intrusion Detection System using Autoencoder
In our model, we are implementing algorithm for Network Intrusion Detection System (NIDS) in which we have taken NSL-KDD dataset regarding various malicious attack which infect our network. We have implemented simple auto-encoder as well as stacked auto-encoder and compared their accuracy. Also we have implemented machine learning algorithms like random forest and logistic regression to compare their results.
Implementation Details – 
First we have imported various dependencies which are required for our implementation. After that we have imported the NSL-KDD dataset from online github repository. Training dataset from –https://raw.githubusercontent.com/defcom17/NSL_KDD/master/KDDTrain%2B.csv 
and testing dataset from – https://raw.githubusercontent.com/defcom17/NSL_KDD/master/KDDTest%2B.csv. After analysis of the dataset we came to know that we have 148517 rows and 42 columns. Also the training and testing dataset differ by some amount of different type of attacks. 

Now we start data pre-processing by making 5 different class as -
dos_attacks=["snmpgetattack","back","land","neptune","smurf","teardrop","pod","apache2","udpstorm","processtable","mailbomb"]
r2l_attacks=["snmpguess","worm","httptunnel","named","xlock","xsnoop","sendmail","ftp_write","guess_passwd","imap","multihop","phf","spy","warezclient","warezmaster"]
u2r_attacks=["sqlattack","buffer_overflow","loadmodule","perl","rootkit","xterm","ps"]
probe_attacks=["ipsweep","nmap","portsweep","satan","saint","mscan"] based on facts. Now categorize those various malicious attack based on the facts to these classes. Now we have 3 such rows which have categorical data, therefore we have used label and one-hot encoding which increases the number of columns to 122. Finally we have used standard scalar to transform our data such that its distribution will have a mean value 0 and standard deviation of 1. 
Now we use our splitted data for training and testing purpose to apply Random Forest Classifier and computing its accuracy which comes out to be 0.75. Also we applied Logistic Regression to our Splitted dataset and obtained accuracy of 0.7420.
Further we have implemented stacked auto-encoder to analyze accuracy of our system. Stacked auto-encoder is a neural network consisting of multiple layers of sparse auto-encoders in which the outputs of each layer is wired to the inputs of the successive layer. After dimensionality reduction with the help of stacked auto-encoder our number of columns come down to 10 and after this we apply Random Forest Classifier to get accuracy of 0.71. We have tested our data and found that there are 14595 Normal, 5997 DoS, 1892 Probe and 59 R2L attacks are there.
Also we have evaluated our results based on various performances metrics such as accuracy, recall, precision, f1 score and detection rate for each of the possible labels.
 
