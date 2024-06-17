# DL_SE2CS
Deep Learning Enabled Ultra-high Quality NMR Chemical Shift Resolved Spectra
# 1.Profiles
## 1.1 Model Training
The model can be trained by **trainer.py**.
## 1.2 Model Test
The model can be tested by **detector.py**.
## 1.3 Experimental Data
Experimental data can be used to test the performance of the model, and four sample data are provided in this paper, which are **exp_asarone.mat**、**exp_azithromycin.mat**、**exp_estradiol.mat** and **exp_mixture.mat**.In addition, the weight file for the model is **net.pt**.The output of the model can be visualized by **plot_result.m**.
# 2.Dependencies
	1.python == 3.6.3
	2.h5py == 2.10.0
	3.numpy == 1.19.5
	4.torch == 1.10.2
Model has been written and tested with the above dependencies. Performance with other module versions has not been tested.
# 3.Preparing Data
The input to the model must be in '.mat' format (mat v7.3) with variable name of 'data', which can be edited in MATLAB or Python.
FID (free induction decay) containing less than 4096 complex points can be zero-filled to 4096 complex points. If the FID contains more than 4096 complex points, it can be filled with zero points to 8192 or more (integer multiples of 4096). Then the spectrum is divided into two or more spectra, spectra with 4096 points are used as the input of the network, and finally the processed spectra are spliced to get a complete spectrum.
