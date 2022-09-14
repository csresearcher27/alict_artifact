# S<sup>2</sup>LCT

S<sup>2</sup>LCT is an automated linguistic capability-based testing framework for NLP models. In this implementation, we generate testcases for sentiment analysis task. Seed test cases are generated from SST dataset(https://nlp.stanford.edu/sentiment/).
In the future, multiple tasks and multiple searching datasets are implemented for the S<sup>2</sup>LCT. 

## Prerequisites
This application is written for ```Python>3.7.11```. All requirements are listed in ```requirements.txt```, and they are installed by pip with the following command.
```bash
pip install -r requirements.txt
```

## Usage
### 1. Seed and expanded test case generation
This step is to search/generate seeds. In this work, we use Stanford Sentiment Treebank (SST) sentiment analysis dataset for the generation. The test cases are generated with the following command. ```NUM_SEEDS``` is the number of seed test cases to be used for generating expanded test cases. All seed test cases are used without the argument.
```bash
cd s2lct
python -m python.sa.main \
       --run template \
       --search_dataset sst \
       --search_selection random \
       --num_seeds {NUM_SEEDS}
```
After running it, multiple ```{PROJ_DIR}/_results/templates_sa_{search_dataset}_{search_selection}_{NUM_SEEDS}seeds/{cfg_expanded_inputs_{CKSUM}.json,seeds_{CKSUM}.json,exps_{CKSUM}.json}``` is generated. ```seeds_{CKSUM}.json``` and ```exps_{CKSUM}.json``` have results of seed and expanded test cases respectively, and they are generated from the intermediate result in ```cfg_expanded_inputs_{CKSUM}.json```. The intermediate result has context-free grammar (CFG) of the seeds and expanded production rule from the seed CFGs and words expanded from the seeds.\
```CKSUM``` is the checksum value, which represents each linguistic capability (LC). You can see the map between the checksum value and its corresponding LC description in the ```cksum_map.txt``` in the same directory of ```cfg_expanded_inputs_{CKSUM}.json```.

### 2. Testcase generation
This step is to convert test cases in .json into .pkl files. It is because of testing models using huggingface pipelines with the format of checklist test cases. You can run it by typing the following command.
```bash
cd s2lct
python -m python.sa.main \
       --run testsuite \
       --search_dataset sst \
       --search_selection random \
       --num_seeds {NUMBER OF SEEDS}
```
Then, you will have ```{PROJ_DIR}/_results/test_results_sa_{search_dataset}_{search_selection}_{NUM_SEEDS}seeds/{sa_testsuite_seeds_{CKSUM}.pkl,sa_testsuite_exps_{CKSUM}.pkl}```.

### 3. Run model on the generated tescases
This step is to run the model on our generated test cases. You can run it by the following command.
```bash
cd s2lct
python -m python.sa.main \
       --run testmodel \
       --search_dataset sst \
       --search_selection random \
       --num_seeds {NUMBER OF SEEDS}
```
Then, the result file ```{PROJ_DIR}/_results/test_results_sa_{search_dataset}_{search_selection}_{NUM_SEEDS}seeds/test_results.txt``` will be generated.


### 4. Get the testing results
This step is to analyze the reults from Step 3 and get the test results. You can run it by the following command.
```bash
cd s2lct
python -m python.sa.main \
       --run analyze \
       --search_dataset sst \
       --search_selection random \
       --num_seeds {NUMBER OF SEEDS}
```
Then, you will have ```{PROJ_DIR}/_results/test_results_sa_{search_dataset}_{search_selection}_{NUM_SEEDS}seeds/test_result_analysis.json``` The file is parsed version of ```test_results.txt```

