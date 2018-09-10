# Example data for working with passim

Example data to understand how [passim](https://github.com/dasmiq/passim) works.

## Requirements

* Python >= 3.3
* [jupyter notebook](https://jupyter.readthedocs.io/en/latest/install.html)
* [pyarrow](https://arrow.apache.org/docs/python/install.html) (for reading parquet files)
* [Faker](https://faker.readthedocs.io/en/master/index.html) (for data generation)

## Data

* `minimal.json` data used in the [github issue](https://github.com/dasmiq/passim/issues/4)
* `lorem.json` data with more text to see how passim works and what text sizes match

## Commands

```
passim --output-format parquet --pairwise data/test.json out
```

* Reading parquet data is more convenient than reading json data (see notebook)
* We are interested in the pairwise matches between texts in the two series
