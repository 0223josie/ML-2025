# Lecture Topic Overview: End-to-End Machine Learning Workflow

## Learning Objectives
Students will be able to:
- Understand and apply the complete 11-step ML workflow from problem definition to monitoring
- Conduct comprehensive exploratory data analysis using visualization techniques
- Build robust data preprocessing pipelines using scikit-learn transformers and pipelines
- Handle diverse data quality issues including missing values, outliers, and mixed data types
- Implement proper train/test splits, stratification, and cross-validation strategies
- Compare multiple ML models and select optimal performers using systematic evaluation
- Tune hyperparameters using automated search methods (Grid Search and Randomized Search)
- Construct advanced scikit-learn pipelines with ColumnTransformers for complex data preprocessing
- Evaluate final model performance with statistical confidence measures

## Topics Covered
**Complete ML Workflow (11 Steps):**
1. Problem Definition and stakeholder analysis
2. Data Collection strategies and considerations
3. Exploratory Data Analysis with effective visualizations
4. Data Cleaning and Preprocessing techniques
5. Feature Engineering approaches
6. Model Selection based on problem type
7. Model Training with proper validation
8. Model Evaluation using appropriate metrics
9. Model Tuning and Optimization
10. Model Deployment considerations
11. Monitoring and Maintenance strategies

**Hands-on Implementation with California Housing Dataset:**
- Complete end-to-end project implementation
- Real-world data challenges and solutions
- Geographic data visualization and analysis

**Advanced Data Preprocessing:**
- Train/test splitting with stratification techniques
- Missing value handling with multiple imputation strategies
- Outlier detection and removal techniques
- Categorical encoding (ordinal, one-hot, target encoding)
- Feature scaling (MinMax, StandardScaler, robust scaling)
- Custom transformers and function transformers
- Pipeline construction for reproducible preprocessing

**Scikit-learn Advanced Concepts:**
- Transformer API design patterns
- Pipeline composition and debugging
- ColumnTransformer for mixed data type handling
- Cross-validation strategies and implementation
- Hyperparameter tuning with GridSearchCV and RandomizedSearchCV

## Practical Skills
After completing this section, students can:
- Execute complete ML projects from problem definition to model evaluation
- Create sophisticated data preprocessing pipelines
- Handle real-world data quality issues systematically
- Build and compare multiple ML models effectively
- Use cross-validation to obtain reliable performance estimates
- Optimize model hyperparameters using automated search
- Implement proper evaluation procedures to avoid data leakage
- Create reproducible ML workflows using scikit-learn pipelines

## Prerequisites
- Lecture 01: Python ML ecosystem and basic programming skills
- Basic understanding of statistical concepts (mean, variance, distributions)
- Familiarity with Pandas and NumPy for data manipulation

## Key Materials
**Core Notebooks:**
- `1-ml-workflow-overview.ipynb`: Complete 11-step ML workflow explanation and motivation
- `2-problem-data-eda.ipynb`: Problem definition, data exploration, and visualization techniques  
- `3-data-preparation.ipynb`: Comprehensive preprocessing pipelines and transformers
- `4-model-training.ipynb`: Model selection, training strategies, and initial evaluation
- `5-model-evaluation.ipynb`: Cross-validation, proper evaluation techniques, and metrics
- `6-model-tuning.ipynb`: Hyperparameter optimization and final model selection
- `7-sklearn-pipelines.ipynb`: Advanced pipeline construction and debugging

**Supporting Materials:**
- `data/housing.csv`: California housing dataset for hands-on practice
- `data/titanic.csv`: Alternative dataset for additional exercises
- `assets/california.png`: Geographic visualization reference
- `extra/`: Supplementary notebooks on pipelines, data leakage, and advanced topics

## Time Estimate
- Workflow overview: 1-2 hours
- EDA and visualization: 3-4 hours
- Data preprocessing: 4-5 hours
- Model training and evaluation: 3-4 hours
- Hyperparameter tuning: 2-3 hours
- **Total: 13-18 hours**

## Assessment Preparation
This section prepares students for:
- All subsequent course assignments requiring systematic ML workflows
- Project implementation using structured methodology
- Data preprocessing challenges in real-world datasets
- Model comparison and selection decisions
- Professional ML development practices