Mental-Health-Canada: AI Models for Emotional Support and Mental-Health Insights

This repository contains the full machine learning pipeline for an AI-assisted mental-health support system designed to understand user emotions, detect cognitive distortions, classify user needs and intent, and ensure safety in sensitive conversations.
The project uses several DistilBERT-based classifiers trained on curated datasets. The goal is to eventually integrate these models into an AI Emotional Support Assistant that provides structured, empathetic, and psychologically informed responses.

Project Overview
This project explores whether AI-driven conversational systems can help address unmet mental-health needs among Canadians. While the Statistics Canada MHACS dataset does not reference chatbots directly, it provides behavioral and psychological indicators that help model mental-health gaps and support needs.

The system includes four core NLP model components:

1. Emotion Classifier
Classifies user messages into emotional categories such as stress, sadness, fear, anger, and others.

2. Safety Classifier
Detects content related to self-harm, suicidal ideation, or other high-risk situations and categorizes messages based on safety level.

3. Need–Intent Classifier
Identifies the purpose or need behind a message, such as validation, guidance, emotional regulation, information seeking, or crisis escalation.

4. Cognitive Distortion Classifier
Detects cognitive distortions such as catastrophizing, overgeneralization, and black-and-white thinking. The model also maps each distortion to an evidence-based reframing strategy.

Repository Structure
Mental-Health-Canada/

1. MentalHealth_Canada.ipynb -- This file explores the Mental Health and Access to Care Survey (MHACS) dataset for understanding of the problem space
2. Data_Normalization.ipynb -- This file contains the normalization of dataset coming from Kaggle and HuggingFace such as: GoEmotion; DailyDialog; Empathetic Dialogues Facebook AI; Mental HEalth Counselling Conversation; Suicide and Depression Detection; Mental Chat 16 K; and Evidence Based Prorietary which contains synthetic data created by me that complements the training of the model.
3. 02_Inspect_Normalized_Datasets.ipynb -- This file finalizes the structure of all the datasets. 
4. Train_DistilBERT_Emotion_Classifier.ipynb
5. Train_DistilBERT_Emotion_Safety_Classifier.ipynb
6. Train_DistilBERT_NeedIntent_Classifier.ipynb
7. Train_DistilBERT_Strategy_Classifier.ipynb

How to Use This Repository:

- Open any of the training notebooks.
- Install required libraries including Transformers, PyTorch, Pandas, and Scikit-learn.
- Load and preprocess datasets.
- Fine-tune the DistilBERT model for the respective task.
- Export and save model weights.
- Use the testing cells inside each notebook to evaluate models on real sample text.

Model Pipeline Overview:

The four models are designed to operate sequentially within a chatbot architecture. The pipeline is structured as follows:
- User Message → Safety Classifier
- If the message is high risk, the system follows a crisis escalation protocol.
- If low risk, processing continues:
→ Emotion Classifier
→ Need–Intent Classifier
→ Cognitive Distortion Classifier
→ Response Synthesis Layer
→ AI Emotional Support Response

Together, these models provide the classification backbone for a mental-health chatbot capable of safe, context-aware, and empathetic messaging.

Motivation and Context:
Mental-health service access in Canada remains limited.
One in five Canadians experience mental-health challenges each year, and two in three individuals report being unable to access the support they need. Long waitlists, cost barriers, and stigma contribute to significant unmet needs.

This project aims to explore how AI can support early-stage reflection, emotional processing, and guided coping strategies in a safe and responsible manner.

Ethical Considerations:
This system is not designed to replace clinical mental-health care.
The project follows principles informed by:
- The Canadian Code of Ethics for Psychologists
- Responsible Artificial Intelligence frameworks
- Privacy, anonymization, and secure data handling practices
- Safety-first design and crisis protocol logic
- All outputs are intended to supplement, not diagnose or treat, mental-health concerns.


Jorge Martinez
Focus: AI-assisted mental-health technologies, UX strategy, and human-centered AI systems.
