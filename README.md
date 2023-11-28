# Flight Price Prediction

The fundamental goal of this project centers around the predictive forecasting of flight ticket prices, intending to equip travelers with the necessary tools to streamline their journey planning while ensuring economic feasibility. Commencing this journey involved the meticulous extraction of data from the Kayak platform (https://www.kayak.com/) to form the foundation for constructing a robust and adaptable regression model capable of forecasting flight ticket prices.

# Contents
- [Project Proposal pdf](https://github.com/maitreyee290897/FlightPricePrediction/blob/master/Documents/Proposal.pdf)
- [Presentation pptx](https://github.com/maitreyee290897/FlightPricePrediction/tree/master/Documents/Presentations)
- [Project Report pdf](https://github.com/maitreyee290897/FlightPricePrediction/blob/master/Documents/Report_FlightPricePrediction.pdf)
- [Kayak Scraper Notebook](https://github.com/maitreyee290897/FlightPricePrediction/blob/master/kayak-scraper.ipynb)
- [Scraped Data in CSVs](https://github.com/maitreyee290897/FlightPricePrediction/tree/master/data)
- [Flight Prediction Project Notebook](https://github.com/maitreyee290897/FlightPricePrediction/blob/master/flight-price-prediction.ipynb)
- [Final Model zip](https://github.com/maitreyee290897/FlightPricePrediction/tree/master/model)


## Project Proposal

The project aims to create a predictive model enabling travelers to select cost-effective flight options. It involves using a linear regression model built on data from platforms like Momondo, Kayak, and Expedia. Input factors like past flight prices, destination, departure specifics, class, and airline data will drive the model. The dataset will be compiled by scraping data from various travel sites and integrating insights from the "Search Engine Results - Flights & Tickets Keywords Dataset." Tools like Selenium, BeautifulSoup, Scikit-learn, Statsmodels, Numpy, Pandas, Matplotlib, Seaborn, and Tableau will be used for web scraping, regression modeling, data manipulation, and visualization. The project aims to empower travelers by providing tools for informed decision-making to find optimal flight prices and schedules.
#### The project proposal can be found [here](https://github.com/maitreyee290897/FlightPricePrediction/blob/master/Documents/Proposal.pdf).

## Project Abstract

This project aims to predict flight ticket prices, leveraging innovative data-driven methods from Kayak and Python libraries. It starts with meticulous data scraping from https://www.kayak.com to create a dataset covering diverse routes and dates. Rigorous preprocessing and outlier handling refine this dataset. Using techniques like categorical data handling and one-hot encoding, the project undergoes comprehensive feature analysis and model development. Among multiple regression models, the RandomForestRegressor excels, predicting prices within an approximate $61.87 range. This empowers travelers to make informed and cost-effective decisions.

## Scraping

The data extraction from Kayak (https://www.kayak.com/) stands as a cornerstone in our project, playing a pivotal role in building a comprehensive dataset essential for rigorously testing and validating our regression model's effectiveness. This dataset serves as more than just a compilation of flight information; it forms the backbone for our model's adaptability and accuracy across diverse flight scenarios. Our project's main goal is to empower travelers by facilitating informed decisions, optimizing travel plans, and ensuring access to the most economically viable flight options available.

The meticulous data extraction process from Kayak was crucial for obtaining a dataset essential for testing the regression model's effectiveness across diverse flight scenarios. This dataset acts as a foundation, ensuring the model's adaptability and accuracy. Our dedication to utilizing data-driven insights to empower travelers remains unwavering.

The scraping methodology involved user interaction to input specific routes and dates. It commenced by prompting users to input origin and destination cities for desired flight routes, allowing multiple routes to be entered until completion was indicated. Subsequently, the system prompted users to input start and end dates in "YYYY-MM-DD" format to define the desired flight data collection duration. The scraping process, meticulously architected to target specific routes and date ranges, utilized Selenium and BeautifulSoup to navigate Kayak's web interface accurately. User-defined parameters enabled the extraction of relevant flight information for targeted analysis and future reference.

#### The Kayak Scraper Notebook can be found [here](https://github.com/maitreyee290897/FlightPricePrediction/blob/master/kayak-scraper.ipynb).

The data extraction from Kayak (https://www.kayak.com/) is crucial, forming the foundation for our regression model's testing and adaptability across various flights. It's more than flight information; it's key to empowering travelers with informed decisions and cost-effective options.

Our meticulous data extraction involved user input for routes and dates, ensuring a targeted approach. Using Selenium and BeautifulSoup, we precisely navigated Kayak's interface for relevant flight data. This user-defined approach allows for focused analysis and future reference.

The outcome of our scraping efforts was a comprehensive dataset spanning from February 1, 2024, to April 30, 2024, covering 12 specific routes. These routes included significant flight paths such as RUH => NYC, NYC => PAR, and PAR => SVO, among others. This meticulously curated dataset serves as the foundational bedrock essential for training and refining our predictive models, paving the way for precise flight price predictions.

#### The scraped data can be found [here](https://github.com/maitreyee290897/FlightPricePrediction/tree/master/data).

#### In total, the data consists of 55,363 rows and 7 columns.

## Analysis and Results

#### The project notebook can be found [here](https://github.com/maitreyee290897/FlightPricePrediction/blob/master/flight-price-prediction.ipynb).

#### Selected features are:

- Source (4 Sources were selected for this project)
- Destination (4 Destinations were selected for this project)
- Total Stops
- Average Price per Airline
- Duration
- Price (Target)

#### Features Analysis and Importance

In correlation Matrix, we found that flight duration moderately correlates with the total number of stops, and a strong link exists between actual price and average price, indicating how these tend to vary together. These findings have significantly contributed to our understanding of flight patterns and pricing behavior.
However, our analysis didn't stop there. We delved deeper to determine which features play a crucial role in predicting flight prices. By employing the Extra Trees Regressor, we uncovered a key revelation. The 'Average Price' stood out as the most influential factor in predicting flight prices, exerting a considerable impact on determining the final ticket cost.
To sum up, our correlation analysis and feature importance assessments have pinpointed the pivotal role of the 'Average Price' feature in forecasting flight costs. This pivotal insight is instrumental in refining our predictive models, revolutionizing how we comprehend and estimate flight expenses.

### Data Modeling and Model Selection

Our dataset was split into three segments: 60% for Training, 20% for Validation, and 20% for Testing.
We delved into various regression models, exploring Polynomial regression up to 5 degrees. While higher degrees showed improvement, there was a risk of overfitting.
Amidst our evaluations, the standout performer was the Random Forest Regression. Its robustness and exceptional predictive accuracy surpassed other models.
To enhance our models, we applied Feature Scaling techniques. However, despite our efforts, we didn't observe a significant performance boost.
After an extensive analysis of regression models, the Random Forest algorithm emerged as the frontrunner. Its favorable performance metrics deemed it the optimal choice for our predictive model.

#### The final selected model is the random forest regression model with:

| Metric |  Score   |
| :----: | :------: |
|  MAE   |  61.87   |
|  MSE   | 40409.87 |
|  RMSE  |  201.02  |

#### Therefore, the final model is able to predict flight ticket prices within around ≈ $61.87.

#### The final model can be found [here](https://github.com/maitreyee290897/FlightPricePrediction/tree/master/model).

### Results

Our Random Forest model underwent a crucial retraining phase, incorporating both training and validation datasets to boost its predictive capabilities.
Following this, we implemented Hyperparameter tuning using Randomized Search CV. This method rigorously explored various hyperparameter combinations through 5-fold cross-validation, aiming to minimize mean squared error.
However, our findings revealed that the model's performance did not notably improve. This suggests that the initial model configuration may already be quite close to its optimal settings.
In conclusion, our RandomForestRegressor model exhibited remarkable predictive performance. As shown, The final model displayed outstanding accuracy, forecasting ticket prices within an approximate range of $61.87 on the test set.

## Presentation

#### The presentation can be found [here](https://github.com/maitreyee290897/FlightPricePrediction/tree/master/Documents/Presentations).


## Report
#### The Project Report can be found [here](https://github.com/maitreyee290897/FlightPricePrediction/blob/master/Documents/Report_FlightPricePrediction.pdf).

## Authors <a name="authors"/>

- ### [Maitreyee Gadwe](https://github.com/maitreyee290897)
- ### [Divya Mahajan](https://github.com/divaamahajan)
