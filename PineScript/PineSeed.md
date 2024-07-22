### Overview
Pine Seeds is a service to import your custom data and access it via TradingView. This service allows you to:
- connect your series data to TradingView
- open it on the TradingView chart
- use it in the custom indicators

refer: [PineSeed Docs](https://github.com/tradingview-pine-seeds/docs)

Use [TradingView](https://tradingview.com/) as your **frontend** and use a GitHub repository as your **backend**.

Keep in mind that such data (we call them EOD data, short for End-of-Day) has certain limitations:

- the data can only be updated 5 times per day
- only daily-based timeframes (1D and above) can be applied to such data
- the number of data elements (symbols) is [limited](https://github.com/tradingview-pine-seeds/docs/blob/main/faq.md#q-what-are-the-limits-on-the-amount-of-data) to 6000
- such data [will not appear](https://github.com/tradingview-pine-seeds/docs/blob/main/ui.md#symbol-search) in the symbol search box

Setting up the service includes several steps:

1. Setting up a [repository](https://github.com/tradingview-pine-seeds/docs/blob/main/repo.md).
2. [Data preparation](https://github.com/tradingview-pine-seeds/docs/blob/main/data.md).
3. Manipulating data in the [TradingView UI](https://github.com/tradingview-pine-seeds/docs/blob/main/ui.md).

### Example

You can take the [seed_crypto_santiment](https://github.com/tradingview-pine-seeds/seed_crypto_santiment) project as a reference for your repository. The project has the proper structure for symbol data.

You can also open symbols from [seed_crypto_santiment](https://github.com/tradingview-pine-seeds/seed_crypto_santiment) on the [TradingView chart](https://www.tradingview.com/chart) and work with it. For example, `SEED_CRYPTO_SANTIMENT:BTC_DEV_ACTIVITY` is an example of custom data integration. The symbol name is uniquely determined by the GitHub settings.

- `SEED` is a required prefix.
- `CRYPTO` is the account name `github.com/crypto`.
- `SANTIMENT` is the suffix of the GitHib repository name `github.com/crypto/seed_crypto_santiment`. The suffix is needed so that you can use several repositories for different data groups, e.g., `seed_<username>_<suffix1>`, `seed_<username>_<suffix2>`.
- `BTC_DEV_ACTIVITY` is the `BTC_DEV_ACTIVITY.CSV` data file name.

Using the built-in [`request.seed()`](https://www.tradingview.com/pine-script-reference/v5/#fun_request%7Bdot%7Dseed) function from the [Pine Script™ language](https://www.tradingview.com/pine-script-docs/en/v5/index.html) and the available data, you can build a chart.

```js
//@version=5
indicator("BTC Dev Activity", format=format.volume)
//request.seed(source, symbol, expression)
activity = request.seed("seed_crypto_santiment", "BTC_DEV_ACTIVITY", close)
plot(activity, "BTC Dev Activity")
```