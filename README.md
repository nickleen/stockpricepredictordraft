# stockpricepredictordraft
import matplotlib.pyplot as plt

# Fetch latest data
latest_data = yf.download('AAPL', period='1d', interval='1m')  # intraday data

# Generate predictions
predicted_price = model.predict(X[-1].reshape(1, 60, 1))  # latest sequence
predicted_price = scaler.inverse_transform(predicted_price)

# Plot
plt.plot(data['Close'], label='Actual')
plt.plot(predicted_price, label='Predicted', linestyle='--')
plt.title('AAPL Stock Price Prediction')
plt.legend()
plt.savefig('stock_prediction.png')  # Include in portfolio/docs
