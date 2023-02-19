<h1 align=center> MLOps from scratch</h1>

**Note:** First we work on jupyter-notebook and after knowing the alg and everything we come to these steps!

## Steps

* Create an environment and acitvate it
```bash
conda create -n mlops-scratch python=3.7 -y
conda activate mlops-scratch
```

* create req file and install it
```bash
touch requirements.txt
pip install -r requirements.txt
```

* create template.py and specifiy all the files and directory that we are gonna create, finally run it 

* create dir data_given
```bash
 mkdir data_given
```
* get the dataset
```bash
https://drive.google.com/drive/folders/18zqQiCJVgF7uzXgfbIJ-04zgz1ItNfF5?usp=sharing
```


```bash
git init
dvc init
```

 
```bash
dvc add data_given/----.csv
```

```bash
git add . && git commit -m ""
```

* adding params => params.yaml and push the changes to github 

* create a file and add the required code to it, finally push it to github
```bash
touch src/get_data.py
```

* **1.** create load_data
```bash
touch src/load_data.py
```

* add stages in dvc.yaml and run the below command
```bash
dvc repro
```

* **pip/python: normal site-packages is not writeable**
```bash
python3 -m pip install [package_name]
```

* push the changes

* **2.** create a split_data file, add a stage in dvc.yaml and run **dvc repro**
```bash
touch src/split_data.py
```

* push the creation of second stage 

* **3.** create train_and_evaluate file, add a stage in dvc.yaml and run **dvc repro**
```bash
touch src/train_and_evaluate.py
```

* push the working process of third stage 

* create, add some codes in dvc.yaml(metrices:), params.yaml and train_and_evaluate.py
```bash
mkdir report
touch report/params.json
touch report/scores.json
```

* run
```bsah
dvc repro
dvc metrics show
dvc metrics diff
```

* push the changes to github
```bash
git add . && git commit -m "tracker added"
```

* changes the values of alpha and l1_ratio in params.yaml and run the below commands
```bash
dvc repro
dvc metrics diff # to track the old and new values
```

* **Setup of testing part:**

* installing:
    * pytest
    * tox