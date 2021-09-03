# Trading Algorithm RSI, Candlestick and Simple Moving Averages.

This algorithm was created with the purpose of seeing how japanese candlesticks, RSI indicator and Simple Moving Averages behave together in a trading strategy.

This code was developed on a backtesting algorithm base from the past data of the four major currency pairs (EURUSD, GBPUSD, USDJPY, USDCHF).

We forcasted entries and exits based on the indicators mentioned above and with this we could see if there would be any gain or loss using them as signals for our trading operations.

## Technologies

This project leverages python3.7 with the following packages

* [yfinance](https://pypi.org/project/yfinance/)- it is completely open source and free. It  offers a reliable, threaded, and Pythonic way to download historical market data from Yahoo! finance.

* [pandas-ta](https://pypi.org/project/pandas-ta/)- It's a Pandas Extension with 130+ Technical Analysis Indicators. Can be called from a Pandas DataFrame or standalone like TA-Lib. Correlation tested with TA-Lib.

* [TA-lib](http://mrjbq7.github.io/ta-lib/doc_index.html)- Technical analysis library with indicators

* [plotly](https://en.wikipedia.org/wiki/Plotly) - provides online graphing, analytics, and statistics tools for individuals and collaboration

* [seaborn](https://seaborn.pydata.org/) - Seaborn is a Python data visualization library based on matplotlib. It provides a high-level interface for drawing attractive and informative statistical graphics.

* [hvplot](https://hvplot.holoviz.org/) - provides a high-level plotting API built on HoloViews and Bokeh that provides a general and consistent API for plotting data in many different formats.

## Installation Guide

Before running the application we have to follow the next steps:

First create an environment in your Git Bash:

* Download [anaconda](https://www.anaconda.com/)

* Open GitBash and create an environment called ```dev``` by typing ```conda create -n dev python=3.7 anaconda```

* Activate the environment byt typing ```conda activate dev```

* Enable the terminal commands for conda by typing ```conda init bash``` 


Second, after creating the environment, install the following dependencies.
```
pip install yfinance
pip install pandas-ta
pip install TA-Lib
pip install plotly
pip install hvplot
pip install seaborn
```
Third, clone the repository and open the code onto your jupyter lab:

* Go to my repository in GitHub and open the repository called ```trading_algorithm```

* Copy the repository's link.

* Open Git Bash in your computer 

* Clone the repository by typing ```git clone``` and paste the link ```git@github.com:nestor39/Trading_Algorithm.git```.

* Type ```jupyter lab`` from your Git Bash in order to launch your jupyter lab which comes installed with Anaconda.
*

### Data collection and preparation

#### Collecting the data
![Collecting the data from yfinance](https://user-images.githubusercontent.com/80844686/131901938-5c9a857f-6de4-4ba2-8ed0-2a516968b3d1.png)

#### Preparing the data
In order to calculate the correlation, indicators, backtest and plot the data. We had to prepare the data in different ways for each step: 

Dropping columns for taking away extra unneccesary columns

![dropping columns](https://user-images.githubusercontent.com/80844686/131904415-ce65c6ea-cd8c-48af-86ee-c85fa3bc3464.png)

Slicing the data for calculating the correlation

![slicing the data](https://user-images.githubusercontent.com/80844686/131903174-748252e6-f784-441f-85a2-91a96d5ecd8b.png)

Reseting the index for plotting the candlestick bar charts

![reset the index](https://user-images.githubusercontent.com/80844686/131904614-96cb7794-0bc0-4c7b-8724-5f371e06b3ac.png)

Annualized Return: A metric that represents the expected Return On Investment (ROI) over a time period of one year. We calculate it by first averaging the daily return values over the time period of the dataset. We then multiply that average daily return value by 252, or the number of trading days in a year.

![image](https://user-images.githubusercontent.com/80844686/131931762-e8d69e2c-4110-4088-9914-f02d8cf3fc0b.png)


Cumulative Returns: The aggregate percentage return (that is, the percentage gain or percentage loss) for an investment. We measure the cumulative return across the entire investment rather than for a particular time period. 

![Cumulative retunr](https://latex.codecogs.com/gif.latex?Cumulative%20return%20%3D%20%5Cfrac%7B%28Currrent%20Price%29-%28Original%20price%29%7D%7BOriginal%20price%7D)

Annual Volatility: The amount that each daily return value differs from the asset's average daily return value (that is, the standard deviation of the asset’s daily return values), measured over one year. The annual volatility helps determine the amount that the stock will potentially gain or lose vs. the expected amount.

[![image](https://user-images.githubusercontent.com/80844686/131931019-f25cd0e0-3c28-4ecf-a7aa-f377fb05a025.png)(https://www.learntocalculate.com/calculate-daily-volatility/)


Sharpe Ratio: A measurement of an asset's outperformance as compared to the asset’s volatility. The outperformance is measured by the difference between the asset's ROI and the return expected from an asset assumed to have no risk, like a three-month US Treasury bill. The asset's volatility is characterized by the standard deviation of its daily return values.

![image](https://user-images.githubusercontent.com/80844686/131930985-e4764266-49b1-47f3-bcc0-73bbdb30eb4d.png)


Sortino Ratio: A variation of the Sharpe ratio that differentiates an asset’s harmful volatility from its overall volatility. The Sharpe ratio measures an investment’s ROI vs. its volatility, treating positive or negative results the same way. By contrast, the [Sortino ratio](https://www.investopedia.com/terms/s/sortinoratio.asp)  focuses on the downside standard deviation, which measures the downside volatility of the asset. The distinction has relevance, because investors tend to have more concern about negative surprises than positive ones.

![image](https://user-images.githubusercontent.com/80844686/131930898-17779b87-65cc-489d-94bb-1719dbd5461d.png)



#### Calculations

[Relativae Strength Index](https://www.investopedia.com/terms/r/rsi.asp) (RSI) it's a momentum indicator used in technical analysis that measures the magnitude of recent price changes to evaluate overbought or oversold conditions in the price of a stock or other asset.

![rsi Equation](https://latex.codecogs.com/gif.latex?RSI%20%3D%20100%20-%20%5Cfrac%7B100%7D%7B1&plus;%5Cfrac%7BAverage%20Gain%7D%7BAverage%20loss%7D%7D)

[Simple Moving Average (SMA)](https://www.investopedia.com/terms/m/movingaverage.asp)  it's a calculation used to analyze data points by creating a series of averages of different subsets of the full data set.

![SMA equation](https://latex.codecogs.com/gif.latex?SMA%20%3D%20%5Cfrac%7BA_%7B1%7D%20&plus;%20A_%7B2%7D%20&plus;%20...&plus;A_%7Bn%7D%7D%7Bn%7D)




### Results

##### Daily return plot

![bokeh_plot (3)](https://user-images.githubusercontent.com/80844686/131893643-06862277-7450-430a-9c81-9a2c282fd37a.png)


![daily return plot](https://user-images.githubusercontent.com/80844686/131893708-dc94bfde-70b3-48e3-8f31-82c24f1787a8.png)

##### Correlation between the for major pair of currencies

![correlation](https://user-images.githubusercontent.com/80844686/131893853-c3e93269-05d2-4993-badb-14020cd65016.png)


##### Signal chart

![bokeh_plot (4)](https://user-images.githubusercontent.com/80844686/131894263-9f0f8a5b-4b37-4c28-9682-8883bebb643e.png)

![bokeh_plot (5)](https://user-images.githubusercontent.com/80844686/131894298-9764b80e-8100-4341-9f63-1457c1f4f6cb.png)

![bokeh_plot (6)](https://user-images.githubusercontent.com/80844686/131894304-d8285ea8-baab-4a74-9c6d-8d2315d6ba8a.png)

![bokeh_plot (7)](https://user-images.githubusercontent.com/80844686/131894314-67a52185-2d83-4ff7-9a0b-1f965de8bb08.png)

![bokeh_plot (8)](https://user-images.githubusercontent.com/80844686/131949764-e809fbd8-8b4d-4bc8-adb5-2e7176961eec.png)


##### Backtest result of the RSI-Candlestick strategy

![Backtest EURUSD](https://user-images.githubusercontent.com/80844686/131893466-2c6666ad-63bb-497a-a0d9-993b80a37ca9.png) ![Backtest GBPUSD](https://user-images.githubusercontent.com/80844686/131893238-2eeb9429-ad43-4b7c-8480-0ef7fc82e3dc.png)


![Backtest USDJPY](https://user-images.githubusercontent.com/80844686/131893145-f70c12e3-27ae-45cb-8d01-16276f1dd6c4.png) ![Backtest USDCHF](https://user-images.githubusercontent.com/80844686/131893030-783d6f07-a4fd-4b0d-aeb6-a4daa3e5a477.png)

![backtest google](https://user-images.githubusercontent.com/80844686/131949715-ca1f76c5-0a75-4c98-bff2-d8d04a71b817.png)

## Contributors

Brought to you by:

* [Nestor Ramirez](https://github.com/nestor39)
* [Matt Hennis](https://github.com/mhennis7)
* [Brett Hudson](https://github.com/Hudzen72)
* [Victor](https://github.com/vikorng)

## Disclosure
The content contained in this project is for informational purposes only. You should not construe any such information or other material provided pursuant to the Course (the “Materials”) as investment, ﬁnancial, tax, legal or other advice. The Materials are not investment advice and any observations concerning any security, trading algorithm or investment strategy provided in this project is not a recommendation to buy, sell or hold such investment or security or to make any other investment decisions. The contributors do not provide any advice regarding the nature, potential value, risk or suitability of any particular investment strategy, trading algorithm, transaction, security or investment. Any use of the Materials, and any decisions made in reliance thereon, including any trading or investment decisions or strategies, are made at your own risk. You should seek the advice of a competent, licensed professional if you require investment, trading or other advice.The contributors do not provide any professional advice in connection with this project. Nothing contained in the Materials constitutes a solicitation, recommendation, endorsement, or offer by the contributors to buy or sell any securities or other ﬁnancial instruments in this or in in any other jurisdiction whether or not such solicitation or offer would be unlawful under the securities laws of such jurisdiction.

## License

[MIT](https://github.com/nestor39/Trading_bot_project/blob/main/LICENSE)
