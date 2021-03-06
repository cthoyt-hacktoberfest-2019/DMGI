# Preprocessing datasets

### How to Run (DBLP dataset)

- Download DBLP-Citation-network V8 dataset from https://www.aminer.cn/citation, and name the downloaded file ``dblp.txt``
- Preprocess DBLP dataset (num_trai: number of labels for training)
```
python preprocess_dblp.py num_train
```
- After generating ```dblp_$num_train.pkl```, save it to ```data```.
- Then run
  - ````python main.py --embedder DMGI --dataset dblp_$num_train --metapaths PAP,PPP,PATAP --isAttn````
- Note that ACM dataset can be downloaded from https://github.com/Jhy1993/HAN/tree/master/data
  - ````python main.py --embedder DMGI --dataset acm --metapaths PAP,PLP --isAttn````

### Data format
- A dictionary containing the following keys
  - ``train_idx``: training index, ``val_idx``: validation index, ``test_idx``: test index, ``feature``: feature matrix, ``label``: labels
  - Relations
    - IMDB: ``MDM``, ``MAM`` 
    - DBLP: ``PAP``, ``PPP``, ``PATAP``
    - ACM: ``PAP``,``PLP``

#### Please note that the preprocessing code is not well organized.

