# Dataframe: `hw2:fed_funds_futures` - 30-Day Fed Funds Futures

Daily open, high, low, close, and volume bars (schema ohlcv-1d) for 30-Day Fed Funds futures from the CME Globex dataset (GLBX.MDP3), pulled with the Databento Python client using the parent symbol ZQ.FUT. Columns: date (trading date), symbol, open, high, low, close, volume. Recall that, per the notes, a contract settles at 100 minus the calendar-day average effective federal funds rate over its month, so 100 - close is the market's expected average rate for that month. Outright monthly contracts have symbols like ZQU6 (month code U = September, last digit of the year); the file also holds calendar spreads (ZQU6-ZQZ6) and butterflies, whose prices are price differences rather than rates, so keep only outrights (fedwatch.filter_outright_contracts) before computing rates. Thinly traded months can be missing bars on some days. The window defaults to the trailing 180 days; refresh with `doit forget pull && doit`. The pull is free under the course subscription and checks that the cost estimate is $0.00 before downloading.


## DataFrame Glimpse

```
Rows: 11862
Columns: 7
$ date   <datetime[ns]> 2026-10-23 00:00:00
$ symbol          <str> 'ZQZ6'
$ open            <f64> 95.965
$ high            <f64> 95.965
$ low             <f64> 95.945
$ close           <f64> 95.965
$ volume          <u64> 12677


```

## Dataframe Manifest

| Dataframe Name                 | 30-Day Fed Funds Futures                                                          |
|--------------------------------|--------------------------------------------------------------------------------------|
| Dataframe ID                   | [fed_funds_futures](../dataframes/hw2/fed_funds_futures.md)                                       |
| Sources                        | CME Globex                                          |
| Providers                      | Databento                                        |
| Provider Links                 | https://databento.com/                                   |
| Tags                           | Monetary Policy, Futures, Fed Funds                                             |
| Access Types                   |                                       |
| How is data pulled?            | Databento API via Python                                                   |
| Data available up to (min)     | 2026-10-23 00:00:00                                                             |
| Data available up to (max)     | 2026-10-23 00:00:00                                                             |
| Dataframe Path                 | /Users/jamesrosenberger/Desktop/FINM32800/hw2-JamesRosenberger-Github/_data/fed_funds_futures.parquet                                             |


**Linked Charts:**


- [hw2:fedwatch_latest_forecast](../../charts/hw2.fedwatch_latest_forecast.md)



## Pipeline Manifest

| Pipeline Name                   | HW 2: The Yield Curve and the Policy Path                       |
|---------------------------------|--------------------------------------------------------|
| Pipeline ID                     | [hw2](../../../index.md)              |
| Maintainer                      | Jeremiah Bejarano               |
| Contributors                    | Jeremiah Bejarano |
| Repository                     | https://github.com/hw-finm-32800/hw2                  |
| Pipeline Web Page               | <a href="file:///Users/jamesrosenberger/Desktop/FINM32800/hw2-JamesRosenberger-Github/docs/index.html">Pipeline Web Page      |
| Date of Last Code Update        | 2026-10-24 16:37:58           |
| OS Compatibility                | Windows, Linux, macOS |
| Linked Dataframes               |  [hw2:crsp_treasury_consolidated](../../dataframes/hw2/crsp_treasury_consolidated.md)<br>  [hw2:fed_yield_curve](../../dataframes/hw2/fed_yield_curve.md)<br>  [hw2:fed_funds_futures](../../dataframes/hw2/fed_funds_futures.md)<br>  |


**Build Commands:**
```
doit

```

