# Stock Tile

There's currently 2 types of stock tiles supported in HD+ described below:

1. Basic Stock Tile
   1. HD+ fetches the current stock price (high/low/current) at a user defined refresh interval
2. Stock Ticker
   1. Hubitat Hub fetches the stock price every X minutes (5/15/etc) and keeps track of each result. HD+ will display all of the prices for the current day in an animated spark view (line graph)

Both of these tiles support 1 or more stocks. If multiple stock symbols are added, HD+ will rotate between each one every few seconds.

The biggest difference between the 2 is the Stock Ticker keeps track of the price over a day where the basic stock tile just displays the last price without any history.

***

## Basic Stock Tile

* Put HD+ into Edit mode
* Hit the "+" sign to add a new tile
* Select Stock from the list
* Enter Stock Symbol and hit OK

<figure><img src="../.gitbook/assets/image (259).png" alt="" width="375"><figcaption></figcaption></figure>

## Stock Ticker

The Stock Ticker requires a Hubitat device driver which can be installed via HPM (it's part of the "HD+ Tile" app)

Once installed via HPM, add a new virtual Stock Ticker device to your devices page

* Get a free Finnhub API Key ([link](https://finnhub.io/dashboard))

<figure><img src="../.gitbook/assets/image (17).png" alt="" width="375"><figcaption></figcaption></figure>

* Enter the Finnhub API key into the driver along with the stock symbols you want to track

<figure><img src="../.gitbook/assets/image (18).png" alt="" width="375"><figcaption></figcaption></figure>

* Save and add this new device to MakerAPI so HD+ can access it
* HD+ should automatically display the stock

<figure><img src="../.gitbook/assets/image (19).png" alt="" width="375"><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (20).png" alt="" width="375"><figcaption></figcaption></figure>
