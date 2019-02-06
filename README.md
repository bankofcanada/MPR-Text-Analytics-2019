# Canada's Monetary Policy Report: if text could speak, what would it say?
 
André Binette <abinette@bankofcanada.ca>

Dmitri Tchebotarev

-------------------------------------------------------------


This repository contains the code and data necessary to reproduce the Bank of Canada Staff Analytical Note No. 2019-5 titled "Canada's Monetary Policy Report: if text could speak, what would it say?", [available here](https://www.bankofcanada.ca/research/browse/?content_type[]=20191).
 
 
The analytical code is contained in three notebooks:
 
 
`AddMPR` is a simple code that allows us to add a new MPR to the analysis (THIS CODE SHOULD BE RUN ONLY AFTER YOU HAVE MANUALLY CLEAN THE MPR DOCUMENT -- SEE THE DATA SECTION IN THE NOTE);
 
 
`SAN_Figure1_to_5` contains the code to reproduce figure 1 to 5 in the note (History, Language, Readability level, Length, and Lexical innovations);
 
 
`SAN_Figure6_to_7` contains the code to reproduce figure 6 to 7 in the note (Classifier performance and Sentiment).
 
-------------------------------------------------------------

### Environment
 
 
In order to run the code, you need a working Jupyter server. It is recommended that you create an Anaconda environment following the step below.
 
 
```bash
conda create -n mpr python=3.6 jupyter pandas=0.23 scikit-learn=0.19 matplotlib beautifulsoup4 git requests seaborn statsmodels bcolz opencv
source deactivate
source activate mpr
pip install textacy pillow ReadabilityCalculator wordcloud wmd sklearn_pandas graphviz isoweek pandas_summary torch==0.4.1
torchvision==0.2.1 torchtext==0.2.3
python -m spacy download en
python -m spacy download en_core_web_lg
```
 
-------------------------------------------------------------
 
### Data
 
 
The historical "clean" MPR could be found in the folder mpr_text.
 
 
The labelled sentences could be found in the folder data/boc/train (pos.text contains the positive sentences, neg.text contains the negative sentences, meh.text contains the neutral sentences and unsup.text contains all the other sentences in the MPRs).
 
 
The sentences for the test set are in the file 100labeled.csv.
 
-------------------------------------------------------------

### Installation
 
 
This project uses fastai as a submodule.  When downloading use the `--recurse-submodules` option in order to download fastai at the same time. 
 
 
```bash
$ git clone --recurse-submodules <url>
```
 
If you forgot, after cloning you can use the following commands to download fastai
```bash
$ git submodule init
$ git submodule update
```
 
For any other issues please consult the following page - https://forums.fast.ai/t/fastai-v0-7-install-issues-thread/24652




