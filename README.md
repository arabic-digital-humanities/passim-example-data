# Example data for working with passim

Example data to understand how [passim](https://github.com/dasmiq/passim) works.

## Data

* `minimal.json` data used in the [github issue](https://github.com/dasmiq/passim/issues/4)
* `lorem.json` data with more text to see how passim works and what text sizes match

## Commands

```
passim --output-format parquet --pairwise data/test.json out
```

* Reading parquet data is more convenient than reading json data (see notebook)
* We are interested in the pairwise matches between texts in the two series
