# Disfl-QA: A Benchmark Dataset for Understanding Disfluencies in Question Answering

Disfl-QA is a targeted dataset for contextual disfluencies in an information seeking  setting, namely question answering over Wikipedia passages.  Disfl-QA builds upon the SQuAD-v2 ([Rajpurkar et al., 2018](https://www.aclweb.org/anthology/P18-2124/)) dataset, where each question in the dev set is annotated to add a contextual disfluency using the paragraph as a source of distractors.

The final dataset consists of ~12k (disfluent question, answer) pairs. Over 90\% of the disfluencies are corrections or restarts, making it a much harder test set for disfluency correction. Disfl-QA aims to fill a major gap between speech and NLP research community. We hope the dataset can serve as a benchmark dataset for testing robustness of models against disfluent inputs. 

Our expriments reveal that the state-of-the-art models are brittle when subjected to disfluent inputs from Disfl-QA. Detailed experiments and analyses can be found in our [paper](https://arxiv.org/pdf/2106.04016.pdf).

## Dataset Description
Disfl-QA consists of ~12k disfluent questions with the following train/dev/test splits:
| File      | Questions   |
|-----|-----|
|train.json  | 7182  |
|dev.json  | 1000   |
|test.json  | 3643  |

Each JSON file consists of original question (SQuAD-v2) and disfluent question (Disfl-QA) in the following format:
```
{ 
  "squad_v2_id":
  {
    "original": Original question from SQuAD-v2,
    "disfluent": Disfluent question from Disfl-QA
  }, ...
}
```
**Note**: The `squad_v2_id` corresponds to the unique  `data.paragraphs.qas.id` in SQuAD-v2 development set.  

Here's an example from the dataset:
```json
 {
  "56ddde6b9a695914005b9628": {
    "original": "In what country is Normandy located?",
    "disfluent": "In what country is Norse found no wait Normandy not Norse?"
  },
  "56ddde6b9a695914005b9629": {
    "original": "When were the Normans in Normandy?",
    "disfluent": "From which countries no tell me when were the Normans in Normandy?"
  },
  "56ddde6b9a695914005b962a": {
    "original": "From which countries did the Norse originate?",
    "disfluent": "From which Norse leader I mean countries did the Norse originate?"
  },
  "56ddde6b9a695914005b962b": {
    "original": "Who was the Norse leader?",
    "disfluent": "When I mean Who was the Norse leader?"
  },
  "56ddde6b9a695914005b962c": {
    "original": "What century did the Normans first gain their separate identity?",
    "disfluent": "When no what century did the Normans first gain their separate identity?"
  },
 }
```

## Citation
If you use or discuss this dataset in your work, please cite it as follows:

```
@inproceedings{gupta-etal-2021-disflqa,
    title = "{Disfl-QA: A Benchmark Dataset for Understanding Disfluencies in Question Answering}",
    author = "Gupta, Aditya and Xu, Jiacheng and Upadhyay, Shyam and Yang, Diyi and Faruqui, Manaal",
    booktitle = "Findings of ACL",
    year = "2021"
}
```

## License
Disfl-QA dataset is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

## Contact

If you have a technical question regarding the dataset or publication, please create an issue in this repository.
