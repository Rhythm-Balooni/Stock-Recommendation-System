# Stock-Recommendation-System

Overview
The Stock Recommendation System aims to enhance the performance of stock predictions by creating a multifaceted recommendation system. It combines sentiment analysis of financial news and technical indicators to recommend short-term decisions while leveraging Long Short-Term Memory (LSTM) networks for long-term predictions. This comprehensive system tackles both short- and long-term stock matters, contributing significantly to investors' decision-making processes.

Data Sources
- YFinance API: Collected historical stock data including Open, Close, Adjusted Close, Low, High, and Volume.
- GNews API: Gathered news articles from prominent online news outlets.
- Financial Phrase Bank: Used for news sentiment detection, classifying sentences into positive, negative, and neutral sentiments.

Methodology
1. Long-Term Price Prediction Model
   - Architecture: Four LSTM layers, each followed by a Dropout layer, and a dense layer with one neuron.
   - Parameter Settings: Optimizer: Adam, Loss Function: MSE, Epochs: 50, Batch Size: 32.
   - Evaluation Metrics: MSE, RMSE, MAE, R-squared.
2. Short-Term Recommendation Model
   - News Sentiment Model:
     - Trained using the Financial Phrase Bank dataset.
     - Best-performing model among Multinomial Naive Bayes (MNB), Support Vector Machine (SVM), and Random Forest (RF).
   - Technical Indicators Model:
     - Utilizes four key technical indicators: 50-day Moving Average (MA), Relative Strength Index (RSI), Average Directional Index (ADX), and On-Balance Volume (OBV).
   - Integration:
     - A weighted average of the Sentiment Analysis Model and the Technical Indicators Model.
     - Final recommendation scores: Buy (> 0.33), Sell (< -0.33), Hold (between -0.33 and 0.33).
