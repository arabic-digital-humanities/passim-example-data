# Example data for working with passim

Example data to understand how [passim](https://github.com/dasmiq/passim) works.

## Requirements

* Python >= 3.3
* [jupyter notebook](https://jupyter.readthedocs.io/en/latest/install.html)
* [pyarrow](https://arrow.apache.org/docs/python/install.html) (for reading parquet files)
* [Faker](https://faker.readthedocs.io/en/master/index.html) (for data generation)

## Data

The example data was generated using [notebooks/generate-data.ipynb](notebooks/generate-data.ipynb).

* `lorem25.json` a file containing two series:
	- Series `a`: single sentences containing 1 to 25 words
	- Series `b`: the series `a` sentences concatenated together
* `lorem25-compare_shuffle.json` a file containing two series:
	- Series `a`: text `t325` from `lorem25.json`
	- Series `b`: text `t325` from `lorem25.json` with sentences shuffled

## Commands

```
passim --output-format parquet --pairwise data/test.json out
```

* Reading parquet data is more convenient than reading json data (see notebook)
* We are interested in the pairwise matches between texts in the two series
