# Entity Sentiment Analysis and Stock Headline Scraper

## Overview
This repository contains key components used in a web application I developed that displays sentiment analysis of recent stock headline news. The application scrapes the latest stock-related headlines, analyzes the sentiment of entities mentioned in those headlines using a fine-tuned BERT model, and presents the results on a user-friendly dashboard. This setup allows users to quickly gauge market sentiment and make informed financial decisions based on real-time data.

This repository contains two key components that are useful for financial data analysis:

1. **Entity Sentiment Model**: A machine learning model designed to analyze the sentiment associated with specific entities (e.g., companies, individuals) mentioned in financial news and social media (Twitter) data.
2. **Stock Headline Scraper**: A web scraping tool that collects stock-related headlines from the Benzinga website for further analysis.

## Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/YourUsername/Entity-Sentiment-Analysis-and-Stock-Headline-Scraper.git
cd Entity-Sentiment-Analysis-and-Stock-Headline-Scraper
```
### 2. Create a Virtual Environment
```bash
python3 -m venv venv
source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
```
### 3. Install Required Packages
```bash
pip install -r requirements.txt
```

## 1. Entity Sentiment Model

### Introduction

The Entity Sentiment Model focuses on analyzing the sentiment towards specific entities within text data. This analysis is valuable in finance, where understanding market sentiment can provide insights into stock performance and public opinion.

### Datasets

- **Financial News Dataset (`SEntFiN-v1.1.csv`)**: Contains financial news articles with labeled sentiment.
- **Twitter Datasets**:
  - `twitter_training.csv`: Training data with labeled tweets.
  - `twitter_validation.csv`: Validation data for testing the model.

### Methodology

1. **Data Preparation**: The datasets are preprocessed to extract entities and their associated sentiments. The financial sentiment data is converted into a format that can be used by the machine learning model.
  
2. **Modeling**: The BERT model, a transformer-based model for NLP tasks, is fine-tuned to classify the sentiment of entities mentioned in the text.

3. **Evaluation**: The model's performance is evaluated using accuracy and other relevant metrics to ensure it effectively predicts sentiment.

### Usage

To run the entity sentiment model:
- Ensure that you have all necessary libraries installed (`transformers`, `torch`, etc.).
- Load the datasets and run the provided notebook cells sequentially.

### Downloading My Pretrained Model
Training the entity sentiment model takes a long time, I managed to achieve an accuracy of around 91%. If you would like to use my model, simply download it from here: [Google Drive](https://drive.google.com/drive/folders/1WSHzK9bkSFi3_NfE9TWQmEIuGhUkaPoF?usp=sharing) and make sure the files are within the same directory as the notebook (make sure you unzip the 'tokenizer_directory'). Afterwards, simply follow the steps in the notebook until you read the subsection 'Load Model' and carry on accordingly. 

## 2. Stock Headline Scraper

### Introduction

The Stock Headline Scraper is designed to automate the collection of stock-related headlines from the Benzinga website using Selenium. The scraped data can then be used for sentiment analysis, trend observation, or other financial analyses.

### Prerequisites

- **Selenium**: Used for automating browser interactions. Make sure the appropriate WebDriver (e.g., GeckoDriver for Firefox) is installed and accessible via your system's PATH.
- **Pandas**: Used for processing the scraped data.
- **Datetime**: For managing date and time data in Python.
- **WebDriver Setup**: You must have a working WebDriver for your browser (e.g., GeckoDriver for Firefox - which is used in this notebook).

### Setup Instructions
This notebook uses GeckoDriver for firefox, of course you can use another driver but make sure you change the code to your needs.
1. Install Browser WebDriver
For Selenium to control your web browser, you'll need to install the appropriate WebDriver. For Firefox, download GeckoDriver:
- [Download GeckoDriver](https://github.com/mozilla/geckodriver/releases)
- Ensure the 'geckodriver' executable is in your system's PATH.

2. Install Firefox
- Make sure your GeckoDriver and Firefox versions are compatible. 


### Scraping Process

1. **Setup**: Define the stock ticker symbol and the date range for scraping headlines.
2. **Execution**: The scraper navigates to the relevant Benzinga page and collects the headlines.
3. **Data Handling**: The scraped headlines are processed and stored in a DataFrame for further analysis.

### Usage

To use the scraper:
- Ensure your WebDriver is correctly installed and accessible.
- Run the notebook, specifying the ticker symbol and end date to stop scraping.

### Additional Notes
- Ensure you have an active internet connection when running the scraper.
- Check that the ticker symbol you intend to scrape is valid by manually visiting https://www.benzinga.com/quote/(YOUR TICKER HERE)/news.

## Conclusion

This repository provides tools for both collecting and analyzing financial data, specifically through entity sentiment analysis and web scraping of stock headlines. These tools are valuable for gaining insights into market sentiment and making informed financial decisions.

## Author

Ganel R. Nallamilli


