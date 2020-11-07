### DRD Feature Extraction

Decay rate distribution (DRD) is a reverberation based feature. In order to detect DRD feature audio signal isconverted into frequency domain then log magnitude spectrum is taken to get envelop. Then the audio signal is divided into 32 frequency bands. In each frequency bands peaks are detected. Start and stop point of each detected peak selected by pre-defined threshold values. In each frequency bands 10 peaks are detected by taking mean of detected peaks in different frequency bands a feature set is created. The
size of the feature set is 32. These 32 parameters are statistically analyzed in terms of mean, skewness, standard deviation and kurtosis. 



# Short Time Fourier Transform: 
STFT is used to convert the time domain signal into frequency domain. Output of STFT gives spectrum of signal. The log of magnitude of DFT is taken to get the envelope of the spectrum.

# Mel Filter Bank:
A normal frequency scale is transformed to a perceptual (mel) scale byapplying Mel filter bank. That gives a log-magnitude spectrum in a number of frequency bands, with the number of bands Nb as defined by the Mel filter bank.

# Peak Detection:
In each frequency bands the number of peaks are available, these peaks are selected by comparing difference between the magnitude of the sample of interest and
its neighboring samples, which are detected by pre-defined threshold values. Sweeping over the whole length of the signal, the peaks that fulfill the threshold criterion are obtained and considered as the start of the peak and end after a certain predefined period of time.
 # Least Square Fitting + Mean: 
 Least Square fitting is used to calculate the slope of each detected peaks.The calculated slope represents the decay for each peak; the number of decays is same as the number of peaks detected. The number of peak decays is different in different frequency bands. The aim behind this step is to know the environment of the recording. Each detected slope
gives the information about the reverberation properties of sound. Reverberation is important parameter for identifying the environment of recording. In this way, an unknown
acoustic environment can be identified by this reverberation based properties. The decay rate distribution in each frequency bands is computed in terms of mean mt. the mean is used to characterize the distribution of the decay rate over time. The mean over different frequency bands given as

 
The result is a vector mt of length equal to the number of frequency bands Nb, where each vector element represents the mean of the decay distribution within the bands over time mt

# Statistics Over bands: 
There are some more parameters are computed in order to obtain the more information about the decay rate example median, mode, variance, correlation covariance, skewness, kurtosis. By combining all these parameter a feature vector is created is called as Decay rate Distribution (DRD).

Median: The median is a nothing but the center value of a numerical data set when the data is sorted into ascending or descending order. Variance: Variance is the measurement of spread of data. it measures how far is the each data point from mean. The procedure for calculating variance is taking square of difference of each number in dataset and mean and it is divided by the number of values in dataset. The formula for variance is


Standard Deviation: Standard deviation gives idea about the spread of data with respect to mean. if the standard deviation is low that represent most of data point are close to avarage. A high standard deviation means that the numbers are more spread out. The formula for standard deviation is given as

Skewness: Skewness is measure of symmetry or asymmetry in a distribution. Skewness parameters added here in order to explore the asymmetry of the decay rate distribution over
frequency bands. The idea behind the use of this parameter is that decay rate of different  scenes shows different asymmetry of the distribution over frequency bands. The formula for skewness is given as

Kurtosis: kurtosis explains hoe heavy the tails of distribution with respect to normal distribution. In other words, kurtosis identifies whether the tails of a given distribution contain extreme values. The parameter is used here to find out in which frequency band the decay rate distribution has extreme values. The formula for Kurtosis is given as

