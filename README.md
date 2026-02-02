# Automated Wine quality prediction Pipeline on AWS Lambda

A serverless machine learning pipeline that automatically trains Random Forest models on wine quality data using AWS Lambda and S3 storage, and predict the score of the wine with different composition of different elements.

## 🎯 Project Overview

This project demonstrates an end-to-end automated ML workflow in a serverless environment. The pipeline reads data from S3, trains a Random Forest Regressor model, evaluates its performance, and saves the trained model back to S3 - all without managing any servers.

## 🏗️ Architecture
```
┌─────────────┐      ┌──────────────┐      ┌─────────────┐
│   S3 Bucket │─────▶│ AWS Lambda   │─────▶│  S3 Bucket  │
│ (Input Data)│      │  (Training)  │      │   (Model)   │
└─────────────┘      └──────────────┘      └─────────────┘
                            │
                            ▼
                     ┌──────────────┐
                     │  CloudWatch  │
                     │     Logs     │
                     └──────────────┘
```

## ✨ Features

- **Serverless Architecture**: No server management, scales automatically
- **Automated Training**: Triggered training pipeline with minimal manual intervention
- **Data Processing**: Automatic data loading, splitting, and feature extraction
- **Model Persistence**: Trained models saved to S3 for future use
- **Cost Efficient**: Pay only for execution time (typically pennies per run)
- **Secure Access**: Custom IAM policies following least-privilege principle

## 🛠️ Tech Stack

- **AWS Lambda** - Serverless compute
- **Amazon S3** - Data and model storage
- **AWS IAM** - Access management and security
- **Python 3.13** - Programming language
- **scikit-learn** - Machine learning library
- **boto3** - AWS SDK for Python
- **pickle** - Model serialization
