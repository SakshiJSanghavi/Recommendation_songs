# Song Recommendation with SESRec on CPU

## Introduction

This project adapts the SESRec (Search-Enhanced Sequential Recommendation) model originally designed for e-commerce to the domain of song recommendation. It explores the adaptability of this recommendation system to different application fields and hardware configurations.

### SESRec Model

SESRec leverages user search interests to enhance sequential recommendations. It disentangles distinct search and recommendation behaviors to provide more accurate recommendations.

## Implementation Details

This section provides an overview of the key components of the project:

- **Dataset:** We utilized the Spotify Playlist Dataset, which contains user interactions with songs. This dataset was preprocessed to align with the requirements of the SESRec model.

- **Data Preprocessing:** The dataset was cleaned, unnecessary columns were removed, and the data was converted into a numerical format. The data was split into training, test, and validation sets.

- **CPU-Based Training:** In contrast to the original implementation that often relies on GPU acceleration, we conducted training on a CPU. This approach demonstrated the model's adaptability to resource-constrained environments.

- **Evaluation Metrics:** We used standard recommendation metrics, including NDCG, Hit Ratio, and MRR, to assess the performance of the model.

## Results

The training process led to improvements in the model's recommendation performance over four epochs. Key results include:

- Increasing NDCG values at different cutoffs (e.g., NDCG@5 and NDCG@10), indicating better ranking quality.
- Rising Hit Ratio values (Hit@1, Hit@5, and Hit@10), showing that the model is effectively finding and recommending relevant songs.
- A growing MRR, suggesting the model's ability to rank relevant songs higher in recommendations.

These results collectively demonstrate the model's effectiveness in delivering high-quality song recommendations.

## Conclusion

The project showcases the adaptability of SESRec to a new application domain and hardware configuration. By expanding the model's horizons from e-commerce to music, we unlock its potential for personalized music discovery. This adaptation fosters a synergy between technology and artistry, enhancing digital music experiences.

## How to Use

- **Requirements:** 
```
    python==3.8.13
    torch==1.9.0
    numpy==1.23.2
    pandas==1.4.4
    scikit-learn==1.1.2
    tqdm==4.64.0
    PyYAML==6.0
```
- **Installation:** 
    - #### Download data
        Download and unzip data from this [link](https://www.kaggle.com/datasets/andrewmvd/spotify-playlists). 
    
    - #### Preprocess Data:
        The data has to be processed in three steps: 
        1. Identifying Search and Recommendation Behaviors
        2. Converting to Numerical Format
        3. Splitting the Data
    
        Preprocessed data can be found under the [here](https://drive.google.com/file/d/1FUC8j8TM_L5jL01cS6giYrsYwsEwaZ8s/view?usp=sharing)

- **Training:** 
Run codes in command line:
    ```bash
    python3 main.py --name SESRec --workspace ./workspace/SESRec --epochs 5 --model SESRec --batch_size 256 --dataset_name spotify
    ```
- **Evaluation:** 
    #### Check training and evaluation process:
    After training, check log files, for example, `workspace/SESRec/log/default.log`.


## Citation

```
@inproceedings{si2023SESRec,
author = {Si, Zihua and Sun, Zhongxiang and Zhang, Xiao and Xu, Jun and Zang, Xiaoxue and Song, Yang and Gai, Kun and Wen, Ji-Rong},
title = {When Search Meets Recommendation: Learning Disentangled Search Representation for Recommendation},
year = {2023},
isbn = {9781450394086},
publisher = {Association for Computing Machinery},
address = {New York, NY, USA},
url = {https://doi.org/10.1145/3539618.3591786},
doi = {10.1145/3539618.3591786},
booktitle = {Proceedings of the 46th International ACM SIGIR Conference on Research and Development in Information Retrieval},
pages = {1313–1323},
numpages = {11},
keywords = {search, contrastive learning, disentanglement learning, recommendation},
location = {Taipei, Taiwan},
series = {SIGIR '23}
}
```

## Authors

- Sakshi Sanghavi
- Shivam Patel