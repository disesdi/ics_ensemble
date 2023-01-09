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
