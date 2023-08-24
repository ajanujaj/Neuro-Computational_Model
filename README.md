# BRATS 2020 Dataset Analysis

Explore and analyze the BRATS 2020 dataset leveraging 2D image data slices and implementing neural network models.

## Dataset Information

This analysis utilizes the BRATS 2020 dataset, which can be sourced from Kaggle:

[BRATS 2020 Training Data on Kaggle](https://www.kaggle.com/datasets/awsaf49/brats2020-training-data)

## Setup Guide

### Prerequisites

To get started, ensure the following Python libraries are installed. If not, they can be added using `pip`:

```bash
pip install python-igraph nilearn torch_geometric pyvis nifti2gif torchvision
```

### Path Configuration

1. Modify the file paths based on your directory structure:

   - In `Config_file.txt`: Update the `rootdir` to reflect your local directory structure.
  
   - In `BratsDatasetclass.ipynb`: Modify the path as follows:

root_dir = get_root_dir_from_config('YOUR_DIRECTORY_PATH/BRATS2020/Code/Config_file.txt')

   - In both `2DImage-ResNet.ipynb` and `CNN-GCN_Model.ipynb`, modify the path:
     path_to_file= 'YOUR_DIRECTORY_PATH/BRATS2020/Code/BratsDatasetClass.ipynb'

2. The user needs to define the ‘BraTS2020_TrainingData’ and ‘BraTS2020_ValidationData’ datasets inside:
‘YOUR_DIRECTORY_PATH/BRATS2020’


3. If you are not running your notebooks on Google Colab, the cell that mounts Google Drive should be commented out or removed from these files:
    BratsDatasetclass.ipynb
    2DImage-ResNet.ipynb
    CNN-GCN_Model.ipynb

   Comment out or remove the following lines:
    from google.colab import drive
    drive.mount('/content/gdrive')
   
4. For multiprocessing, adjust the ‘num_workers’ parameter according to your system's capabilities. It's currently set to 4 in all '.ipynb' files. Modify this value based on your specific requirements.
Modify ‘get_dataloader’ function for multiprocessing.



### File Descriptions

- BratsDatasetclass.ipynb: This serves as the base class for our models. It handles all data preprocessing and dataloader creation.

- 2DImage-ResNet.ipynb: Implements a pre-trained "ResNet18" model, utilized in the initial phase to extract feature maps.

- CNN-GCN_Model.ipynb: Combines the ResNet18 and GCN model. Features are extracted from the ResNet18 and then passed to the GCN, resulting in a predicted mask image.

### Execution

After adjusting the paths in the mentioned files, execute the `CNN-GCN_Model.ipynb` notebook to view the results.



