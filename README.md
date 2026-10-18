# GPT-2 Phishing Email Classifier

## Overview

For my CS4390R mini-project I originally planned to build a different project, but after looking at the time requirements and technical complexity I decided to pivot to a phishing email classifier instead. This project still let me work with a pretrained GPT-2 model while staying within the scope of the class.

The goal is simple: classify an email as either legitimate or phishing using a fine-tuned GPT-2 sequence classification model running locally. No external AI APIs were used during training.

The notebook walks through the entire machine learning pipeline, from loading the dataset all the way through evaluation and saving the trained model.

---

## What the notebook does

The notebook:

- Loads and cleans the email dataset.
- Combines the available email text into a single input.
- Splits the data into training, validation, and testing sets.
- Tokenizes the text using the GPT-2 tokenizer.
- Fine-tunes a pretrained DistilGPT-2 model.
- Evaluates the model using several common classification metrics.
- Saves graphs, predictions, and the trained model for later use.
- Includes a small function that can classify new emails after training.

---

## Dataset

For the final project I used the public **Phishing Email Dataset** from Kaggle.

- Dataset: Phishing Email Dataset
- Uploader: Naser Abdullah Alam
- Platform: Kaggle
- https://www.kaggle.com/datasets/naserabdullahalam/phishing-email-dataset

The notebook expects the dataset to be located at:

```text
data/phishing_emails.csv
```

A small demo dataset is also included so the notebook can still run if the larger dataset is missing.

---

## Project Structure

```text
CS4390 MINI PROJECT/
│
├── phishing_email_classifier.ipynb
├── README.md
├── REFLECTION.md
├── EVALUATION_EVIDENCE.md
├── requirements.txt
│
├── data/
│   ├── demo_emails.csv
│   └── phishing_emails.csv
│
├── outputs/
│
└── saved_model/
```

---

## Requirements

The project was developed using Python and the Hugging Face Transformers library.

Main packages include:

- PyTorch
- Transformers
- scikit-learn
- pandas
- matplotlib
- numpy

Everything needed can be installed with:

```bash
pip install -r requirements.txt
```

---

## Running the project

Open the notebook and run all cells.

The notebook automatically:

- loads the dataset
- trains the classifier
- evaluates the results
- saves the model
- generates evaluation graphs

The trained model and tokenizer are saved inside the `saved_model` folder.

---

## Results

The notebook generates several files inside the `outputs` folder, including:

- Classification report
- Confusion matrix
- Learning curves
- Test predictions
- False positive examples
- False negative examples
- Training history
- JSON metrics
- Run configuration

These files were used as evidence for the project report.

---

## Limitations

This project is mainly intended as an educational exercise.

A few limitations I noticed:

- The model was trained on a relatively small subset of the full dataset because training was done on CPU.
- Freezing most of the transformer kept training time reasonable, but also limited performance.
- The classifier only uses email text. It doesn't consider URLs, attachments, sender reputation, or metadata.
- Performance could likely be improved by training on more data or allowing more of the transformer weights to update.

---

## Future Improvements

If I continued working on this project I would probably:

- Train on the complete dataset.
- Use a GPU instead of CPU.
- Experiment with larger GPT-2 models.
- Compare GPT-2 against models like BERT or RoBERTa.
- Add URL and header features instead of relying only on email text.

---

## Responsible Use

This project was created for educational purposes as part of CS4390R (Introduction to Large Language Models).

It is not intended to replace commercial phishing detection software or be used as a production security system.