# Detecting Cyberattacks In Industrial Control Systems: Ensemble Methods For Binary Classification Of Synchrophasor & Security Logs

*Exploring classification of high-dimensional synchrophasor security log data with ensemble methods*

find code for this project in [this jupyter notebook](https://github.com/disesdi/ics_ensemble/blob/45776b7bd6ce124714c37f29e5d9b5a183b98b84/ics_ensemble_1.ipynb)

full writeup & results [available here](https://anglesofattack.io/1/ics_ensemble.html)

## Background

Synchrophasors / Phasor Measurement Units (PMUs) use a common time source to synchronize measurements of electrical waves in an power grid.<sup>[3]</sup> 

These measurements sometimes present anomalous events, which may constitute cyberattacks.

Cyberattacks on power grids can take the form of data injections that mimic fault events, causing power to be erroneously shut down by sensors in the system.<sup>[4]</sup>

In the diagram below, G1 and G2 are power generators. R1 through R4 are Intelligent Electronic Devices (IEDs) that can switch the breakers on or off. 


![ics_ensemble_1](https://user-images.githubusercontent.com/110150470/197652921-2f98b627-4d1c-4f43-95d5-f3d286b825cd.png)

*[Image source](http://www.ece.uah.edu/~thm0009/icsdatasets/PowerSystem_Dataset_README.pdf) <sup>[1]</sup>*


The IEDs/breakers have no internal validation to detect whether fault events are valid or faked. Breakers can be shut off based on false data injections, resulting in malicious interruption of power.

Differentiating between real fault events and data injection attacks is thus vital to maintaining power grid operation.

The system from which these measurements were taken contains 4 PMUs measuring 29 features, which results in a total of 116 PMU measurement columns.

The dataset additionally contains [Snort](https://www.snort.org/) <sup>[5]</sup>  and simulated control panel logs.

## Data

This project utilyzes Power System Attack Datasets produced by Mississippi State University and Oak Ridge National Laboratory (ORNL). The datasets contain security logs as well as electrical synchrophasor data.

 
The Dataset(s) README is available [here](http://www.ece.uah.edu/~thm0009/icsdatasets/PowerSystem_Dataset_README.pdf):<sup>[1]</sup>

* http://www.ece.uah.edu/~thm0009/icsdatasets/PowerSystem_Dataset_README.pdf


Links to download these & other Industrial Control System (ICS) cyberattack datasets [here](https://sites.google.com/a/uah.edu/tommy-morris-uah/ics-data-sets?authuser=1):<sup>[2]</sup>

* https://sites.google.com/a/uah.edu/tommy-morris-uah/ics-data-sets?authuser=1

The dataset contains 2 target classes for binary classification, representing natural and attack scenarios. Where appropriate for the model, categorical data have been transformed to numerical values.

## References

1. Power System Attack Datasets - Mississippi State University and Oak Ridge National Laboratory - 4/15/2014, 15 April 2014, http://www.ece.uah.edu/~thm0009/icsdatasets/PowerSystem_Dataset_README.pdf. Accessed 21 October 2022.


2. “Tommy Morris - Industrial Control System (ICS) Cyber Attack Datasets.” Google Sites, https://sites.google.com/a/uah.edu/tommy-morris-uah/ics-data-sets?authuser=1. Accessed 21 October 2022.


3. Knapp, Eric D. and Raj Samani. “Applied Cyber Security and the Smart Grid: Implementing Security Controls into the Modern Power Infrastructure.” (2013).


4. Unsal, Derya, Taha Selim Ustun, S. M. Suhail Hussain and Ahmet Onen. “Enhancing Cybersecurity in Smart Grids: False Data Injection and Its Mitigation.” Energies 14 (2021): 2657.


5. Snort - Network Intrusion Detection & Prevention System, https://www.snort.org/. Accessed 21 October 2022.


6. “1.11. Ensemble methods — scikit-learn 1.1.2 documentation: Bagging meta-estimator.” Scikit-learn, https://scikit-learn.org/stable/modules/ensemble.html?highlight=bagging#bagging-meta-estimator. Accessed 21 October 2022.


7. L. Breiman, “Bagging predictors”, Machine Learning, 24(2), 123-140, 1996.


8. Ensemble methods — scikit-learn 1.1.2 documentation: Forests of randomized trees.” Scikit-learn, https://scikit-learn.org/stable/modules/ensemble.html?highlight=random+forests#forests-of-randomized-trees“1.11. Accessed 21 October 2022.



9. Breiman, “Random Forests”, Machine Learning, 45(1), 5-32, 2001.


10. “1.11. Ensemble methods — scikit-learn 1.1.2 documentation: Gradient Boosting.” Scikit-learn, https://scikit-learn.org/stable/modules/ensemble.html#gradient-boosting. Accessed 21 October 2022.


11. Friedman, J.H. (2001). Greedy function approximation: A gradient boosting machine. Annals of Statistics, 29, 1189-1232.


12. “1.11. Ensemble methods — scikit-learn 1.1.2 documentation: Gradient Boosting--Shrinkage.” Scikit-learn, https://scikit-learn.org/stable/modules/ensemble.html#gradient-boosting-shrinkage. Accessed 21 October 2022.


13. Tianqi Chen and Carlos Guestrin. XGBoost: A Scalable Tree Boosting System. In 22nd SIGKDD Conference on Knowledge Discovery and Data Mining, 2016


14. “Scalable, Portable and Distributed Gradient Boosting (GBDT, GBRT or GBM) Library, for Python, R, Java, Scala, C++ and more. Runs on single machine, Hadoop, Spark, Dask, Flink and DataFlow.” GitHub, https://github.com/dmlc/xgboost. Accessed 21 October 2022.


15. “1.11. Ensemble methods — scikit-learn 1.1.2 documentation: Histogram Based Gradient Boosting.” Scikit-learn, https://scikit-learn.org/stable/modules/ensemble.html#histogram-based-gradient-boosting. Accessed 21 October 2022


16. Ke et. al. “LightGBM: A Highly Efficient Gradient Boosting Decision Tree”
