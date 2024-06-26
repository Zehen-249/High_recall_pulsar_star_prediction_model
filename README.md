# Pulsar Star Detection Model

## What are Pulsar Stars
Pulsars are “cosmic lighthouses” that appear to be flickering stars, but are actually highly magnetized, rapidly rotating neutron stars. They emit beams of electromagnetic radiation, which can be observed as pulses of radiation when the beam sweeps past Earth. Formed when a massive star runs out of fuel and collapses under its own gravity, causing a supernova explosion. The remaining core of the star, known as a neutron star, is incredibly dense, with the density of a sugar cube that weighs as much as a mountain.

## How to detect a Pulsar
### Pulse Profile
 The integrated pulse profile is a critical concept in pulsar astronomy. A pulsar star pulse profile refers to the shape of the radiation emitted by a pulsar as it rotates averaged over 
 many pulse periods. The shape and characteristics of the pulses can provide information about the pulsar’s magnetic field, spin axis, and any companions it may have.

- Mean of the Integrated Profile: This represents the average value of the pulse profile over a single pulse period. It provides a measure of the overall signal strength.
- Standard Deviation of the Integrated Profile: This measures the variability or spread of the pulse profile. A higher standard deviation indicates more variation in the signal strength over the pulse period.

- Kurtosis of the Integrated Profile: Kurtosis measures the "tailedness" of the profile distribution. A higher kurtosis indicates more outliers, which might suggest the presence of strong, narrow pulses.

- Skewness of the Integrated Profile: Skewness measures the asymmetry of the profile distribution. Positive skewness indicates that the profile has a long tail on the right side, while negative skewness indicates a long tail on the left side.

### DM-SNR (Dispersion Measure - Signal-to-Noise Ratio) 
curve is used in pulsar signal processing to optimize the detection of pulsar signals.
- Mean of the DM-SNR Curve: This represents the average signal-to-noise ratio over different dispersion measures. It gives an overall measure of the signal strength relative to noise across the range of dispersion measures.
- Standard Deviation of the DM-SNR Curve: This measures the variability in the signal-to-noise ratio across different dispersion measures. A higher standard deviation indicates more variation in the signal strength with respect to the dispersion measure.
- Kurtosis of the DM-SNR Curve: Kurtosis measures the "tailedness" of the DM-SNR curve distribution. A higher kurtosis indicates more outliers in the signal-to-noise ratio values, suggesting that some dispersion measures produce significantly stronger signals.
- Skewness of the DM-SNR Curve: Skewness measures the asymmetry of the DM-SNR curve distribution. Positive skewness indicates that there are higher SNR values at higher dispersion measures, while negative skewness indicates higher SNR values at lower dispersion measures.

## Folder Structure
- pulsar_data_train : The csv file contains labeled dataset for training of the classification model. Based on 8 features of a radion impulse detected by a radiotelescope the signal has labeled as Pulasr(1) of Not a Pulsar(0).
Each candidate is described by 8 continuous variables, and a single class variable. The first four are simple statistics obtained from the integrated pulse profile (folded profile). This is an array of continuous variables that describe a longitude-resolved version of the signal that has been averaged in both time and frequency . The remaining four variables are similarly obtained from the DM-SNR curve .

- EDA : The notebook contains initial Exploratary Analysis of the dataset, based on which the data preprocessing is carried out. The key features of the data and the correlation of each feature with the target_class can be seen in the notebook.

- model : Based on the EDA, the training dataset has processed and for a High recall towards the positive class(1), the dataset has made to be biades towards positive class(1) by removing the negative class rows. Naive Beyed Classifier has chose to classify the signals into pulsars and not pulsar because of its capability of handling baised datasets. The problem has solved with Neural Network with even more High recall for positive class.
- pulsar_detection_model : the binary file contains the trained model in joblib format and can be user further projects to classify Pulsars.

## Evaluation of the Model Naive Bayes
- Accuracy Score 0.934
- Precision
  - Pulsar 0.96
  - Not a Pulsar 0.90
- Recall
  - Pulsar 0.92
  - Not a Pulsar 0.96
- f1 Score
  - Pulsar 0.94
  - Not a Pulsar 0.93
 
## Evaluation of the Neural Network
- Accuracy Score 0.9464
- Precision
  - Pulsar 0.95
  - Not a Pulsar 0.95
- Recall
  - Pulsar 0.96
  - Not a Pulsar 0.94
- f1 Score
  - Pulsar 0.95
  - Not a Pulsar 0.94
