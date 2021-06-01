# Time series forecasting for NSE:DMART

## Install and load required packages
```r
install.packages(tidyquant)
library(tidyquant)
library(ggplot2)
```

## Fetch the data
```r
# Get training data
train_set = tq_get('DMART.NS', from='2014-01-01', to='2019-12-31', get='stock.prices')
test_set = tq_get('DMART.NS', from='2020-05-01', to='2020-05-31', get='stock.prices')
```

## View dataset
```r
head(train_set)
```
![Train Head](./train_head.png)

```r
head(test_set)
```
![Test Head](./test_head.png)

## Plot the datasets
```r
train_set %>%
  ggplot(aes(x = date, y = adjusted)) +
  geom_line() +
  theme_classic() +
  labs(x = 'Date',
       y = "Adjusted Price",
       title = "[train] DMART price chart") +
  scale_y_continuous(breaks = seq(0,300,10))
```
![Train Plot](./train_plot.png)
```r
test_set %>%
  ggplot(aes(x = date, y = adjusted)) +
  geom_line() +
  theme_classic() +
  labs(x = 'Date',
       y = "Adjusted Price",
       title = "[test] DMART price chart") +
  scale_y_continuous(breaks = seq(0,300,10))
```
![Test Plot](./test_plot.png)

## Identify the parameters for the ARIMA model
Time plot for ACF and PACF need to be made
```r

```