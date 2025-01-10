### Twitter Sentiment Analysis Web App

#### Overview
This web application enables users to log in to Twitter, scrape tweets based on a specified subject, and perform sentiment analysis using a pre-trained NLP model. The results are saved to a CSV file and displayed in a user-friendly format.

#### Features
- **Twitter Login and Search**: Automates the process of logging into Twitter and searching for tweets related to a specific topic.
- **Data Scraping**: Extracts tweets, timestamps, and user information while ensuring data uniqueness.
- **Sentiment Analysis**: Utilizes the `cardiffnlp/twitter-roberta-base-sentiment` model to analyze the sentiment (positive, neutral, negative) of the scraped tweets.
- **CSV Export**: Saves scraped tweets and sentiment scores into a CSV file for further analysis.
- **Interactive Results Display**: Presents the analyzed data in a user-friendly format on a web page.

---

#### Requirements
1. **Python Libraries**:
   - Flask
   - Selenium
   - Transformers
   - Pandas
   - Scipy
   - WebDriver Manager
2. **System Requirements**:
   - Chrome browser installed.
   - Compatible WebDriver (`chromedriver`) managed by `webdriver_manager`.

---

#### How to Run
1. **Clone or Download** the repository.
2. **Install Dependencies**:
   Run the following command to install the required libraries:
   ```bash
   pip install flask selenium transformers pandas scipy webdriver-manager
   ```
3. **Run the App**:
   Execute the following command:
   ```bash
   python app.py
   ```
4. **Access the Web App**:
   Open your browser and navigate to `http://127.0.0.1:5000`.

---

#### How It Works
1. **Login**:
   - Enter your Twitter username and password in the login form.
   - Provide a subject to search for tweets.
2. **Scraping**:
   - The app logs into Twitter, searches for the subject, and scrapes up to 100 unique tweets.
3. **Analysis**:
   - Sentiment analysis is performed on the tweets using the pre-trained Roberta sentiment model.
4. **Results**:
   - Sentiments are categorized into positive, neutral, and negative scores.
   - The scraped data and analysis results are saved to a CSV file (`tweet.csv`) and displayed in the app.

---

#### Notes
- **Security**: This app captures sensitive information like Twitter credentials. Ensure secure handling of this data and avoid sharing or exposing it.
- **Rate Limits**: Twitter's API and UI may enforce rate limits or restrictions. Adjust the scraping process to comply with Twitter's policies.

---

#### Troubleshooting
- **Selenium Errors**: Ensure Chrome is installed and updated. Verify `chromedriver` compatibility with your Chrome version.
- **Model Download Issues**: Pre-trained models may need an internet connection for initial download.
- **Timeouts**: Increase `WebDriverWait` time if experiencing loading issues.

---

#### Acknowledgments
This app leverages:
- [Hugging Face Transformers](https://huggingface.co/transformers) for sentiment analysis.
- [Selenium](https://selenium.dev) for web automation.
- [Twitter-Roberta-Base-Sentiment Model](https://huggingface.co/cardiffnlp/twitter-roberta-base-sentiment) for analyzing tweet sentiments.
