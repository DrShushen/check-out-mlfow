# Synopsis
Checking out [MLFlow](https://mlflow.org/).

### Note
Run quickstart stuff from `[repo_root]/mlflow/examples`.

### Setting up Tracking Server locally
* OS assumed to be Ubuntu.
* Install `sqlite`
```bash
$ sudo apt update
$ sudo apt install sqlite3
$ sqlite3 --version
```
* Launch `mlflow server` in the background (use a separate shell, `tmux`, `&`, or any other method).
```
$ cd ./server
$ mlflow server --backend-store-uri sqlite:///mlflow.db --default-artifact-root $(pwd)/mlflow --host 0.0.0.0  
```
* Set environment variable to point all your runs to this server:
```bash
$ export MLFLOW_TRACKING_URI='http://0.0.0.0:5000'
```
* All your experiments **and models** will now be tracked on this server (navigate to `http://0.0.0.0:5000` in browser). 
