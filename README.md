# Star Trek Recsys
Star Trek Recommender System

This repository contains the necessary files to reproduce the experiments from the paper:

"An Ontology-based Recommender System with an Application to the Star Trek Television Franchise"

## To get the Star Trek data:
1. Episode transcripts are in the "transcripts" directory
2. The hierarchy of the Literary Theme Ontology can be found as a data structure in the file star_trek_recsys_08.py
3. Annotations of the Star Trek episodes with the themes in the ontology can be found in the same file.

## To reproduce the experiments
Install Anaconda 3.6 or higher
Linux users need to install Mono from https://www.mono-project.com/docs/about-mono/supported-platforms/linux/
MyMediaLite binaries are in the "mymedialite" directory
### For the content-based filtering approaches
1. Unzip the files in the "transcripts" directory.
2. Run `python baseline_02_recsys.py` program. This program reads the episode transcripts and generates Item-K nearest neighbors models files for MyMediaLite in the "mymedialite" directory. An example of the model filename is "BASELINE_LSI-40.model"
3. To run the models in MyMediaLite, move to the "mymedialite" directory and run in the command line the testmodel.bat file. For instance, type `testmodel.bat BASELINE_LSI-40 20`. The second parameter (20) is the number k of neighbors. For linux users type `sh testmodel.sh BASELINE_LSI-40 20`.
4. Find the results in the directory "mymedialite/results" in the file "knn_BASELINE_LSI-40_K20.txt
### For knowledge-based and ontology-based approaches
1. Run `python star_treck_recsys_08.py` program. This program uses the thematic annotations of the episodes and the ontology to generate Item-K nearest neighbors models files for MyMediaLite in the "mymedialite" directory. An example of the model filename is "knn_DICE.model"
3. To run the models in MyMediaLite, move to the "mymedialite" directory and run in the command line the testmodel.bat file. For instance, type `testmodel.bat knn_DICE 20`. The second parameter (20) is the number k of neighbors. For linux users type `sh testmodel.sh knn_DICE 20`.
4. Find the results in the directory "mymedialite/results" in the file "knn_DICE_K20.txt






