# VSG-Safe

This repository is the official implementation of "VSG-Safe: Spotting NSFW Video through Cross-Frame Evidence".

## 📦 Environment Setup

Please install the required dependencies using:

```bash
conda env create -f environment.yaml
```

> Note: Model files and datasets are **not included**.

---

## 🏋️‍♂️ Training Procedure

### Steps:

```bash
#Stage1:scene graph exraction
python tools/train.py #trian segement
python train/reltion_trian.py #trian relation

#Stage2: NSFW Prediction via GNN
python train/trian_gnn.py
```

This will train and save the illumination segmentation model.

---

## 🧪 Testing Procedure

After completing the tasks in the training phase, the testing phase can be conducted by following the procedures in QuickStart.ipynb.



## 📁 File Structure Description

```
|-- QuickStart.ipynb  # test visualization file
|-- README.MD
|-- blip-vqa-base     # Attribute exractor
|-- configs           # Configuration files
|   |-- mask2former   # Entity segmentation
|   `-- unitrack      # Entity track
|-- data              # Data for testing
|-- datasets          #  Data processing files
|   |-- datasets      # Load data
|   `-- pipelines     # Process data
|-- enviorment.yaml   # environment for project
|-- gnn.py            # gnn model
|-- models            # Model files
|   |-- mask2former   # Entity segmentation
|   |-- relation_head # Relation prediction
|   `-- unitrack      # Entity track
|-- result            # Intermediate results storage
|   |-- task1         # Entity segmentation 
|   |-- task2         # relation 
|   `-- task3         # scene graph 
|-- tools             # Training code
|   |-- rel_train.py  # Relation extraction training
|   |-- train.py      # Entity extraction training
|   `-- trian_gnn.py  # Video scene graph detection training
`-- utils             # Utility scripts
    |-- relation_matching.py  # match relation
    `-- ...
