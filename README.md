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


*************************************************************************** 

* **Setup of testing part:**

* installing:
    * pytest
    * tox


* create the tox.ini file and add code to it
```bash
touch tox.ini
```

* run
```bash
pytest -v # it will display that their is no test, its pytest command
tox # tox command
```

* create
```bash
mkdir tests
touch tests/conftest.py
touch tests/test_config.py
touch tests/__init__.py
```

* add the following code to test_config.py and then run **pytest -v** for gething the concept
```python
def test_generic():
    a =2
    b = 2
    assert a == b
```

* create file setup.py and add codes to it
```bash
touch setup.py
pip install -e . # setup commands
```
* **just for learn purpose not required in this project:** build your own package commands
```bash
python setup.py sdist bdist_wheel
```

* install jupyterlab 
```bash
 pip install jupyterlab
 ```

* open jupyter-lab and get the min and max for each features

* adding flake8 code to tox.ini for formating the documents


******************************************************************************************

* **flask app** create dir and files and add code to it for test purpose
```bash
mkdir -p prediction_service/model
touch prediction_service/__init__.py
touch prediction_service/prediction.py

mkdir webapp
mkdir -p webapp/static/css
touch webapp/static/css/style.css

mkdir -p webapp/static/script
touch webapp/static/script/index.js

mkdir webapp/templates
touch webapp/templates/index.html
touch webapp/templates/404.html
touch webapp/templates/base.html

touch app.py
```

* create ci-cd 
```bash
mkdir -p .github/workflows/
touch .github/workflows/ci-cd.yaml
```

**Note:** We are not working on deploying to heroku so we just create procfile for extra informatin
```bash
touch Procfile
```
 
 *************************************************************************************


* bring changes in prediction_service

* creating test