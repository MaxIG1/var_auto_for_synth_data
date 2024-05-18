# README
# Welcome to my approach of recreating tabular data with a VAE

![Optimal Model](/reports/figures/optimal_model.png)

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
