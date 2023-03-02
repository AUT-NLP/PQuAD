# PQuAD

PQuAD is a crowd- sourced reading comprehension dataset on Persian Language. It includes 80,000 
questions along with their answers, with 25% of the questions being unanswerable. As a reading 
comprehension dataset, it requires a system to read a passage and then answer the given questions 
from the passage. PQuAD's questions are based on Persian Wikipedia articles and cover a wide 
variety of subjects. Articles used for question generation are quality checked and include few 
number of non-Persian words. 

The dataset is divided into three categories including train, validation, and test sets and the 
statistics of these sets are as follows:

```
+----------------------------+-------+------------+------+-------+
|                            | Train | Validation | Test | Total |
+----------------------------+-------+------------+------+-------+
|      Total Questions       | 63994 |    7976    | 8002 | 79972 |
|   Unanswerable Questions   | 15721 |    1981    | 1914 | 19616 |
| Mean # of paragraph tokens |  125  |    121     | 124  |  125  |
| Mean # of question tokens  |   10  |     11     |  11  |   10  |
|  Mean # of answer tokens   |   5   |     6      |  5   |   5   |
+----------------------------+-------+------------+------+-------+
```

Workers were encouraged to use paraphrased sentences in their questions and avoid choosing the 
answers comprising non-Persian words. Another group of crowdworkers validated the questions and 
answers in the test and validation set to ensure their quality. They also provided additional 
answers to the questions in test and validation sets if possible. This helps to consider all 
possible types of answers and have a better evaluation of models.

PQuAD is stored in the JSON format and consists of passages where each passage is linked to a 
set of questions. Answer(s) of the questions is specified with answer's span (start and end 
point of answer in paragraph). Also, the unanswerable questions are marked as unanswerable.

The estimated human performance on the test set is 88.3% for F1 and 80.3% for EM. We have 
evaluated PQuAD using two pre-trained transformer-based language models, namely ParsBERT 
(Farahani et al., 2021) and XLM-RoBERTa (Conneau et al., 2020), as well as BiDAF (Levy et 
al., 2017) which is an attention-based model proposed for MRC.

```
+-------------+------+------+-----------+-----------+-------------+
|    Model    |  EM  |  F1  | HasAns_EM | HasAns_F1 | NoAns_EM/F1 |
+-------------+------+------+-----------+-----------+-------------+
|     BNA     | 54.4 | 71.4 |    43.9   |    66.4   |     87.6    |
|   ParsBERT  | 68.1 | 82.0 |    61.5   |    79.8   |     89.0    |
| XLM-RoBERTa | 74.8 | 87.6 |    69.1   |    86.0   |     92.7    |
|    Human    | 80.3 | 88.3 |    74.9   |    85.6   |     96.8    |
+-------------+------+------+-----------+-----------+-------------+
```

PQuAD is developed by Mabna Intelligent Computing at Amirkabir Science and Technology Park with 
collaboration of the NLP lab of the Amirkabir University of Technology and is supported by the 
Vice Presidency for Scientific and Technology. By releasing this dataset, we aim to ease research 
on Persian reading comprehension and the development of Persian question answering systems.

To use the dataset, please cite the following paper:

https://www.sciencedirect.com/science/article/abs/pii/S0885230823000050

@article{DARVISHI2023101486,

author = {Kasra Darvishi and Newsha Shahbodaghkhan and Zahra Abbasiantaeb and Saeedeh Momtazi},

title = {PQuAD: A Persian question answering dataset},

journal = {Computer Speech & Language},

volume = {80},

pages = {101486},

year = {2023},

issn = {0885-2308},

doi = {https://doi.org/10.1016/j.csl.2023.101486},

url = {https://www.sciencedirect.com/science/article/pii/S0885230823000050}

}

Shield: [![CC BY-SA 4.0][cc-by-sa-shield]][cc-by-sa]

This work is licensed under a
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg
