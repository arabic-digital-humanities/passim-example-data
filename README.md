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
passim --output-format parquet --pairwise data/lorem25.json out
```

* Reading parquet data is more convenient than reading json data (see notebook)
* We are interested in the pairwise matches between texts in the two series

## Results

### `lorem25.json`

Running the command using default settings (`passim --output-format parquet --pairwise data/lorem25.json out`)
gives us the following matches (data from file `out/align.parquet`,  [notebook](notebooks/passim-results.ipynb)):

|    | id1   | id2   |   matches |   score |   tok2 |   tok1 |
|---:|:------|:------|----------:|--------:|-------:|-------:|
|  0 | t325  | t21   |       137 |   267.5 |     21 |    325 |
|  1 | t325  | t22   |       137 |   274   |     22 |    325 |
|  2 | t325  | t23   |       140 |   269.5 |     23 |    325 |
|  3 | t325  | t24   |       156 |   301.5 |     24 |    325 |
|  4 | t325  | t25   |       142 |   276.5 |     25 |    325 |

So, the minimal number of words that match is 21.

## Questions

* How does passim tokenize?
