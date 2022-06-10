# Experiment_CV
Cross-validation on Holo4k Dataset folds

### Build used for CV:

https://github.com/rdk/p2rank/tree/836cb0189db3d6253372d60b896d7fa4b828b1bd

Memory in `local-env.sh` set to `"-Xmx128G"`

### Datasets:

* `holo4k_fold_0_train-fpocket.ds`
* `holo4k_fold_0_val-fpocket.ds`
* `holo4k_fold_1_train-fpocket.ds`
* `holo4k_fold_1_val-fpocket.ds`
* `holo4k_fold_2_train-fpocket.ds`
* `holo4k_fold_2_val-fpocket.ds`

[Download Dataset Folds](https://github.com/AndreaSoltes/Experiment_CV/files/8878015/holo4k_cv_folds.zip)

### Configurations:

Train and evaluation without conservation: `config/train-deafult.groovy`

Train and evaluation with conservation: `config/train-conservation.groovy`

[Download Configuration files](https://github.com/AndreaSoltes/Experiment_CV/files/8879723/configurations.zip)

### Training prediction P2Rank model 0 without conservation information

~~~bash
./prank.sh traineval -t ../p2rank-datasets/holo4k_fold_0_train-fpocket.ds -e ../p2rank-datasets/holo4k_fold_0_val-fpocket.ds -config config/train-default.groovy -rf_depth 12 -visualizations 0 -rf_threads 10 -rf_trees 100 -delete_models 0 -loop 1 -seed 42
~~~

### Results

`MCC_0=0.4220`

[Further Details](https://github.com/AndreaSoltes/Experiment_CV/files/8879666/results_with_conservation_fold0.zip)

### Training prediction P2Rank model 1 without conservation information

~~~bash
./prank.sh traineval -t ../p2rank-datasets/holo4k_fold_1_train-fpocket.ds -e ../p2rank-datasets/holo4k_fold_1_val-fpocket.ds -config config/train-default.groovy -rf_depth 12 -visualizations 0 -rf_threads 10 -rf_trees 100 -delete_models 0 -loop 1 -seed 42
~~~

### Results

`MCC_1=0.4356`

[Further Details](https://github.com/AndreaSoltes/Experiment_CV/files/8879664/results_without_conservation_fold1.zip)

### Training prediction P2Rank model 2 without conservation information

~~~bash
./prank.sh traineval -t ../p2rank-datasets/holo4k_fold_2_train-fpocket.ds -e ../p2rank-datasets/holo4k_fold_2_val-fpocket.ds -config config/train-default.groovy -rf_depth 12 -visualizations 0 -rf_threads 10 -rf_trees 100 -delete_models 0 -loop 1 -seed 42
~~~

### Results

`MCC_2=0.4318`

[Further Details](https://github.com/AndreaSoltes/Experiment_CV/files/8879665/results_without_conservation_fold2.zip)

### Mean MCC for training without conservation information = 0.4298

### Training prediction P2Rank model 0 with conservation information

~~~bash
./prank.sh traineval -t ../p2rank-datasets/holo4k_fold_0_train-fpocket.ds -e ../p2rank-datasets/holo4k_fold_0_val-fpocket.ds -config config/train-conservation.groovy -rf_depth 12 -visualizations 0 -rf_threads 10 -rf_trees 100 -delete_models 0 -loop 1 -seed 42 -label conservation -conservation_dirs holo4k/conservation/e5i1/scores/
~~~

### Results

`MCC_0_c=0.4479`

[Further Details](https://github.com/AndreaSoltes/Experiment_CV/files/8879669/results_without_conservation_fold0.zip)

### Training prediction P2Rank model 1 with conservation information

~~~bash
./prank.sh traineval -t ../p2rank-datasets/holo4k_fold_1_train-fpocket.ds -e ../p2rank-datasets/holo4k_fold_1_val-fpocket.ds -config config/train-conservation.groovy -rf_depth 12 -visualizations 0 -rf_threads 10 -rf_trees 100 -delete_models 0 -loop 1 -seed 42 -label conservation -conservation_dirs holo4k/conservation/e5i1/scores/
~~~

### Results

`MCC_1_c=0.4693`

[Further Details](https://github.com/AndreaSoltes/Experiment_CV/files/8879667/results_with_conservation_fold1.zip)

### Training prediction P2Rank model 2 with conservation information

~~~bash
./prank.sh traineval -t ../p2rank-datasets/holo4k_fold_2_train-fpocket.ds -e ../p2rank-datasets/holo4k_fold_2_val-fpocket.ds -config config/train-conservation.groovy -rf_depth 12 -visualizations 0 -rf_threads 10 -rf_trees 100 -delete_models 0 -loop 1 -seed 42 -label conservation -conservation_dirs holo4k/conservation/e5i1/scores/
~~~

### Results

`MCC_2_c=0.4659`

[Further Details](https://github.com/AndreaSoltes/Experiment_CV/files/8879668/results_with_conservation_fold2.zip)

### Mean MCC for training with conservation information = 0.4610
