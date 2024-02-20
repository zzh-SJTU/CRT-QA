# CRT-QA: A Dataset of Complex Reasoning Question Answering over Tabular Data (EMNLP2023) 📊

This repository contains the CRT-QA dataset, which includes question-answer pairs that require complex reasoning over tabular data. The dataset is currently undergoing some processes at Microsoft Research Asia, and its release is planned once the process is complete. 🚀

## About the Dataset and Paper

- **Title:** CRT-QA: A Dataset of Complex Reasoning Question Answering over Tabular Data
- **Conference:** EMNLP 2023
- **Authors:** [Zhehao Zhang](https://zzh-sjtu.github.io/zhehaozhang.github.io/), Xitao Li, Yan Gao, Jian-Guang Lou 👩‍💼👨‍💼
- **Affiliation:** Dartmouth College, Xi'an Jiaotong University, Microsoft Research Asia 🏢

The dataset contains question-answer pairs along with metadata for each question. It includes `dataset.json` for the main experiments and `unanswerable.json` for Unanswerable and Indeterminate Questions.

### Data Format

The data is stored in a json file, structured with the following fields for each datapoint (keyed by a .csv file table):

```
Question name, Title, step1, step2, step3, step4, Answer, Directness, Composition Type
```

- `Question name`: The text of the question
- `Title`: The title of the table that the question refers to
- `step1` to `step4`: Steps describing the reasoning process and operations used to answer the question
  - `type`: `Operation` or `Reasoning`
  - `name`: Name of the specific operation or reasoning type
  - `detail`: Additional details about the step
- `Answer`: The answer text
- `Directness`: `Explicit` or `Implicit` question
- `Composition Type`: `Bridging`, `Intersection`, or `Comparison`

### Reasoning and Operations

The reasoning and operations referenced in the `step` fields come from a defined taxonomy:

**Operations:**
- Indexing
- Filtering
- Grouping
- Sorting

**Reasoning:**
- Grounding
- Auto-categorization
- Temporal Reasoning
- Geographical/Spatial Reasoning
- Aggregating
- Arithmetic
- Reasoning with Quantifiers
- Other Commonsense Reasoning

### Status 🚧

The code and data for this project are currently being prepared and reviewed. We aim to release them as soon as the process is completed. Stay tuned for updates!

### Contact 📧

For inquiries or updates about this repository, please contact [zhehao.zhang.gr@dartmouth.edu]. 📬

### Citation

If you use this dataset in your research, please cite the following paper:

```
@inproceedings{zhang-etal-2023-crt,
    title = "{CRT}-{QA}: A Dataset of Complex Reasoning Question Answering over Tabular Data",
    author = "Zhang, Zhehao  and
      Li, Xitao  and
      Gao, Yan  and
      Lou, Jian-Guang",
    editor = "Bouamor, Houda  and
      Pino, Juan  and
      Bali, Kalika",
    booktitle = "Proceedings of the 2023 Conference on Empirical Methods in Natural Language Processing",
    month = dec,
    year = "2023",
    address = "Singapore",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2023.emnlp-main.132",
    doi = "10.18653/v1/2023.emnlp-main.132",
    pages = "2131--2153",
    abstract = "Large language models (LLMs) show powerful reasoning abilities on various text-based tasks. However, their reasoning capability on structured data such as tables has not been systematically explored. In this work, we first establish a comprehensive taxonomy of reasoning and operation types for tabular data analysis. Then, we construct a complex reasoning QA dataset over tabular data, named CRT-QA dataset (Complex Reasoning QA over Tabular data), with the following unique features: (1) it is the first Table QA dataset with multi-step operation and informal reasoning; (2) it contains fine-grained annotations on questions{'} directness, composition types of sub-questions, and human reasoning paths which can be used to conduct a thorough investigation on LLMs{'} reasoning ability; (3) it contains a collection of unanswerable and indeterminate questions that commonly arise in real-world situations. We further introduce an efficient and effective tool-augmented method, named ARC (Auto-exemplar-guided Reasoning with Code), to use external tools such as Pandas to solve table reasoning tasks without handcrafted demonstrations. The experiment results show that CRT-QA presents a strong challenge for baseline methods and ARC achieves the best result.",
}
```
