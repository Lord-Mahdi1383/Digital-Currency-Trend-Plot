# Digital-Currency-Trend-Plot
# 📌 Overview
This python script analysis bitcoin prices trend (or any other digital currency) by fetching 3 months of price history from yahoo finance and identifying significant trend changes using a dynamic threshold (which in this case its 5.7% of highest price - lowest price) and visualizes trends with clear lines in matplotlib

# 🛠️ Features
 - Dynamic Trend Detection: Automatically calculates threshold based on price range
 - Clean Visualization: Professional matplotlib charts with proper formatting
 - Flexible Timeframes: Easily modify to analyze different periods
 - Multiple Asset Support: Code can be adapted for Ethereum or other cryptocurrencies

# 🔍 How It Works
iterates through eaxh day's price change 
  - if trend line is going **'up'** but price starts going **'down'** store the trend line only if its **more than threshold**
    - ```python
      if (curr_direction == 1 and price_change < 0):
            if (hist['Close'].iloc[i-1] - hist['Close'].iloc[i]) > threshold:
                trend_line.append((curr_start, hist.index[i-1], curr_price, hist['Close'].iloc[i-1]))

  - if trend line is going **'down'** but price starts going **'up'** store the trend line only if its **more than threshold**
    - ```python
      elif (curr_direction == -1, price_change > 0):
            if (hist['Close'].iloc[i] - hist['Close'].iloc[i-1]) > threshold:
                trend_line.append((curr_start, hist.index[i-1], curr_price, hist['Close'].iloc[i-1])) 
after each storing each trend line reset starting point and price for next trend line
store all this trend lines in a list and draw them once we're done

# ⚙️ Installation
#### 1- Clone this repository:
```
git clone https://github.com/Lord-Mahdi1383/Digital-Currency-Trend-Plot.git
cd Digital-Currency-Trend-Plot
```
#### 2- Install dependencies:
```
pip install -r requirements.txt
```
