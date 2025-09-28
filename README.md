# Azure Car Price Prediction MLOps Project

## Project Overview
This project implements an end-to-end MLOps pipeline for car price prediction using Azure Machine Learning services. The system automates the training, evaluation, and deployment of machine learning models in a production environment.

## Project Structure
````plaintext
CICD-project-FullCode/
├── data-science/
│   └── src/
│       ├── prep.py           # Data preparation script
│       ├── train.py          # Model training script
│       └── register.py       # Model registration script
├── mlops/
│   └── azureml/
│       └── train/
│           ├── newpipeline.yml   # Main pipeline definition
│           └── train.yml         # Training component definition
├── config-infra-prod.yml     # Production infrastructure config
└── README.md
````

## Infrastructure Configuration
- **Environment**: Production
- **Location**: East US
- **Workspace**: demoworkspace
- **Compute**: Azure ML Compute Cluster
- **Security**: Enabled secure workspace

## Pipeline Components
1. **Data Preparation**
   - Input: Raw car pricing dataset
   - Output: Processed training and test datasets
   - Features: Segment, Kilometers_Driven, Mileage, Engine, Power, Seats

2. **Model Training**
   - Algorithm: Random Forest Regressor
   - Hyperparameter Tuning:
     - n_estimators: [10, 20, 30, 50]
     - max_depth: [5, 10, 15, 20, 25, 30]

3. **Model Registration**
   - Model Name: used_cars_price_prediction_model
   - Tracking: MLflow

## Getting Started
1. **Setup Environment**
````bash
# Install required packages
pip install -r requirements.txt

# Login to Azure
az login
````

2. **Configure Azure ML Workspace**
````bash
# Set workspace variables
export WORKSPACE_NAME="carpricingml_workspace"
export RESOURCE_GROUP="default_resource_group"
````

3. **Run Pipeline**
````bash
az ml pipeline create --file mlops/azureml/train/newpipeline.yml
````

## Contributing
1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License
This project is licensed under the MIT License - see the LICENSE file for details.

## Contact
For questions and support, please contact the development team.

---
*Note: Update version numbers and requirements as needed.*
