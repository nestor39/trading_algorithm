# Trading Algorithm RSI - Candlestick



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


#### Calculations
![rsi Equation](https://latex.codecogs.com/gif.latex?RSI%20%3D%20100-%5Cfrac%7B100%7D%7B1&plus;RS%7D)

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

##### Backtest result of the RSI-Candlestick strategy
![Backtest EURUSD](https://user-images.githubusercontent.com/80844686/131893466-2c6666ad-63bb-497a-a0d9-993b80a37ca9.png)


![Backtest GBPUSD](https://user-images.githubusercontent.com/80844686/131893238-2eeb9429-ad43-4b7c-8480-0ef7fc82e3dc.png)


![Backtest USDJPY](https://user-images.githubusercontent.com/80844686/131893145-f70c12e3-27ae-45cb-8d01-16276f1dd6c4.png)


![Backtest USDCHF](https://user-images.githubusercontent.com/80844686/131893030-783d6f07-a4fd-4b0d-aeb6-a4daa3e5a477.png)


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
