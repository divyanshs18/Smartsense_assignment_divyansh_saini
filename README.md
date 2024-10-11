# Smartsense_assignment_divyansh_saini
Email Management System


This repository contains an AI-powered email classification and response system designed to streamline the handling of incoming emails from various stakeholders (students, corporate entities, researchers) at IITGN.

Table of Contents
Project Overview
Features
Project Structure
How It Works
Installation
Model
Evaluation
Automated Responses

Project Overview
This project implements a machine learning-based system that classifies incoming emails and responds automatically . The project uses natural language processing (NLP) techniques, and the emails are classified into three categories:

Student Inquiries: Queries related to courses, schedules, and general information.
Research Collaboration: Emails related to academic collaboration, research partnerships, and shared facilities.
Corporate Inquiries: Requests from companies regarding internships, placements, or partnerships.
The system includes two components:

Email Classification: Classifies emails based on their content using a simple neural network.
Automated Response System: Generates automated responses based on the content of the email, or escalates it to HOD if needed.
Features
Automatic email classification into predefined categories.
Pretrained and custom models for classification.
Auto-generated responses for common queries.
Escalation of corporate or sensitive inquiries to HOD.
Extensible design allowing for more categories or automated responses.
Project Structure

Key Files
email_management.py: This contains the complete implementation of the email classifier and automated response system.
requirements.txt: This file lists the Python dependencies required to run the project.

How It Works
The system uses TF-IDF (Term Frequency-Inverse Document Frequency) vectorization to convert email text into numerical representations, followed by a neural network that classifies the email into one of the three categories.

Workflow:
Preprocessing: Email data is vectorized using the TF-IDF method.
Training: The neural network is trained on a labeled dataset of email samples(into 3 categories student resaerch industry).
Classification: Incoming emails are classified as either Student Inquiry, Research Collaboration, or Corporate Inquiry.
Response Generation: If classified as a student inquiry, an automated response is generated based on predefined rules.
Escalation: For corporate or research collaboration inquiries, the email is forwarded to the HOD for manual handling.
Installation
Prerequisites
Python 3.x
PyTorch
scikit-learn


Install the required dependencies:
docker build -t email-manager .
docker run email-manager
Usage
After installation, you can run the system by executing the email_management.ipynb file. This script will train the email classification model and test it on a small dataset.

bash
python email_management.py
Sample Output
The system will train the model and then process a sample email such as:

css

Input Email: "I would like to request the syllabus for the Data Structures course."
Response: "Here is the syllabus for your requested course: [link]"
Model
The project uses a simple feed-forward neural network to classify emails. The neural network has one linear layer that takes the vectorized text input (using TF-IDF) and outputs the classification category (0: Student, 1: Research, 2: Corporate).

Model Training
Loss Function: Cross-Entropy Loss
Optimizer: Adam Optimizer
Training Epochs: 100
Input & Output
Input: Vectorized email text (TF-IDF).
Output: One of three categories (Student, Research, Corporate).
Evaluation
The model is evaluated on the test data using accuracy as the primary metric. After training, the model typically achieves an accuracy of ~90% on a small dataset of 10-15 emails.

You can customize this by increasing the dataset size or changing the model architecture.

Automated Responses
For student inquiries, the system generates automated responses using predefined keywords:

Syllabus Request: "Here is the syllabus for your requested course: [link]"
Exam Schedule: "The exam is on [date]."
If no keyword matches, the system escalates the email.

