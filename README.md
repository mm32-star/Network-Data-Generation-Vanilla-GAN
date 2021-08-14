# Network Data Generation Vanilla GAN

As part of my 19496 honours project at The University of Strathclyde, a generative deep learning model based on Generative Adversarial Networks (GAN) architecture was designed. The implemented model aimed to generate synthetic network data, both benign and malicious, that was similar to that within the CIC-IDS-2017 dataset. 

By Greig Fotheringham and supervised by Dr Robert Atkinson

## Motivation

Machine learning algorithms find patterns and correlations within training data and then are able to apply what was learned to new, unseen data for tasks such as classification and prediction. However, to ensure a model can correctly identify these patterns and correlations, typically, large amounts of training data are needed. When training data is limited, such as how network data is limited due to privacy concerns, problems arise. If a model is designed as a network intrusion detection system (a system that identifies network malicious traffic from benign network traffic) but is not trained with enough data, the model will not be able to reliably identify the malicious network data potentially leading to the user being vulnerable to network attacks such as denial of service attacks, brute force attacks, botnet attacks and many more. 

To help alleviate this problem, it was proposed that a deep generative model would be used to generate synthetic network data (both benign and malicious). Synthetic data would then be augmented to an existing intrusion detection system dataset, specifically the CICIDS-2017 dataset. If the generated synthetic data was of similar quality to the existing dataset then an unlimited amount of data could be artificially generated and used to train seperate IDS models, removing concerns over lack of high quality training data. 

### Description

To accomplish the objectives set out above, two seperate models were designed and implemented in Python making use of the machine learing library Keras. 

1. A multiclass classifier neural network model was developed to provide a baseline performance score using exclusively non-synthetic data. The model would act as an intrusion detection system and attempt to classify data as one of six different network types (one benign type and five malicious types). Synthetic data could then later be passed through the same model and if performance metrics were similar for both synthetic and non-synthetic data were similar, it would indicate that the synthetic data was of similar quality to the non-synthetic data.

2. A Generative Adversarial Networks model was developed to generate the synthetic network data.