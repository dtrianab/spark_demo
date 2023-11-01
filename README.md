# Configure local environment (Ubuntu)

## JRE
```bash
sudo apt update
sudo apt upgrade
sudo apt install default-jre
```

## install conda
- For Miniconda – Minimum 400 MB disk space
- For Anaconda – Minimum 3 GB disk space
https://docs.conda.io/projects/miniconda/en/latest/

```bash
mkdir -p ~/miniconda3
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda3/miniconda.sh
bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
rm -rf ~/miniconda3/miniconda.sh
```

```
~/miniconda3/bin/conda init bash
~/miniconda3/bin/conda init zsh
```

## Configure conda env

- New env
```bash
conda create -n my_pyspark_env38 python=3.8 
conda activate my_pyspark_env38
conda install -c conda-forge -y pyspark notebook nb_conda_kernels jupyterlab jupyter_contrib_nbextensions findspark
jupyter notebook
```
- Remove env
```bash
conda deactivate
conda remove -n my_pyspark_env39 --all
```
https://jupyter-contrib-nbextensions.readthedocs.io/en/latest/install.html

## Install Spark 3.2.4 - Hadoop 3.2
https://spark.apache.org/releases/spark-release-3-2-4.html

```bash
wget https://archive.apache.org/dist/spark/spark-3.2.4/spark-3.2.4-bin-hadoop3.2.tgz
tar -xvf spark-3.2.4-bin-hadoop3.2.tgz
export SPARK_HOME=/home/dtriana/apache/spark_demo/spark-3.2.4-bin-hadoop3.2
./spark-3.2.4-bin-hadoop3.2/bin/spark-shell
```



https://sparkbyexamples.com/pyspark-tutorial/

https://github.com/spark-examples/pyspark-examples/blob/master/README.md