# README
# Welcome to my approach of recreating tabular data with a VAE





# Central Findings
This project investigates the use of variational autoencoders (VAEs) to reproduce heavily imbalanced and sensitive data, specifically focusing on credit card fraud data. Key findings include:

VAEs demonstrate the capability to reproduce data effectively, particularly through the Data-generation process, as can be seen here:
Green = Original test data; Blue is syntethic data.
![Optimal Model](/reports/figures/optimal_model.png)
Challenges arise in reproducing minority classes, especially through the S-generation process. Yet with oversampling, this is possible as well:
![Optimal Model](/reports/figures/optimal_model_sample.png)

Hyperparameter tuning improves model performance, with VAEs showing promising results in replicating minority classes after oversampling.

Comparison with conditional generative adversarial networks (CGANs) suggests VAEs offer better utility scores, especially when oversampling is not an option.
Privacy analysis indicates VAE-generated data can provide higher privacy levels, particularly with increased latent dimensions.
Limitations and Further Research

Challenges exist in adapting attacks like the Monte Carlo attack to tabular data, suggesting the need for further research.
VAEs tend to overlook minority classes, prompting exploration into architectures that better address this issue.
Understanding the point at which VAEs overfit remains an open question.
Future research directions include exploring differential privacy, incorporating time dimension with recurrent neural networks, and investigating conditional VAEs.

# Recommendations and Evaluation
Well-trained VAEs, especially through the D-generation process, offer promising solutions for synthetic data generation.
Consideration of oversampling and model selection based on use case requirements is crucial.
VAEs demonstrate potential for synthetic data generation while preserving privacy and providing high utility.
Usage

# Usage

Data Preparation: Refer to data_preparation.ipynb for steps involved in data preprocessing and preparation.
Model Training: Utilize notebook Base_updated_data.ipynb or CGAN_Approach.ipynb for training VAE and CGAN models, respectively.
Hyper Paramter Training: Use the VAE_hyper_parameter_search.ipynb for further hyper paramter tuning using the Tensorboard.
start the Tensorboard with logs with 
```plaintext 
tensorboard --logdir=logs/hparam_tuning_vae_2

Evaluation: Assess model performance using Classifications.ipynb for classification evaluation and K_Level_Analysis.ipynb for privacy analysis
and Monte_Carlo_Attack.ipynb for the membership inference attack




```plaintext
data/
│
├── interim/
│   ├── generated/
│   │   ├── base/
│   │   ├── D-Generation/
│   │   ├── S-Generation/
│   └── privacy_testing/
│       ├── K_Level_data/
│       ├── Monte_Carlo_Attack_Data/
├── processed/
├── raw
models/
│
├── CGAN/
├── Claassifier
├── VAE
notebooks/
│
├── logs/ # contains the logs of hyperparameter tuning
├── autoencoder.ipynb # 
├── Base_Experiment.ipynb # the base experiment that shows that a VAE would capable of generating tabular data
├── Base_updated_data.ipynb # this is the VAE with the custom test step.
├── CGAN_Approach.ipynb # the CGAN approach, yet not finetune compared to VAE
├── Classifications.ipynb # the classification to evaluate the utility of the syntethic data.
├── data_preparation.ipynb # the preparation steps for different data sets.
├── EDA_and_Visualizations.ipynb # the note book were most of the visualizations happen
├── K_Level_Analysis.ipynb # according to Li et al. (2019).
├── Monte_Carlo_Attack.ipynb # according to (Hilprecht et al. 2019)
├── VAE_hyper_parameter_search.ipynb # grid search for optimal hyperparamters, see also the logs folder
