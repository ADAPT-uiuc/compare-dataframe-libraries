## AWS configuration

- Ubuntu 22.04
- c5.24xlarge (96 vCPUs, 192 GiB of RAM)
- 400GB SSD

## Reproducing the environment

```bash
sudo apt-get update
git clone https://github.com/ADAPT-uiuc/compare-dataframe-libraries
```

### Install Python

```bash
# We use version 3.10.6
sudo apt install python3.10
```

### Install `pip`, `venv`
```bash
sudo apt install python3-pip
sudo apt install python3.10-venv
```

### Create environment (named `env`) and activate it
```bash
python3 -m venv env
source env/bin/activate
```

### Install dependencies
```bash
cd compare-dataframe-libraries
pip install -r requirements.txt
```

### Download datasets
```bash
cd datasets
./download_datasets.sh
```

Make sure that you see both `iris.csv` and `yellow_tripdata_2015-01.csv`.

### Running notebooks

You should be able to run any of the notebooks. However, running them with `ipython` through the terminal will not be useful. You need to run it through a notebook environment. Below are some alternatives:
- Launch Jupyter remotely ([tutorial](https://medium.com/finbox/connecting-jupyter-notebook-to-aws-ec2-instance-bba0af52a6b8))
- Run notebooks through VSCode directly.

## Reproducing numbers
You should run a notebook multiple times because Jupyter virtualizes many things, including e.g., the disk.
Note that the numbers may be quite different from run to run and from the paper. We could not avoid this variability.
However, the _conclusions_ should be the same, namely the orders of magnitude of slowdowns and speedups 
mentioned in the paper should be the same.
