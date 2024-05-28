# Steel defect detection
This repo contains a mulitple trained U-Nets for multiclass image segmentation. The dataset comes from the Kaggle competition [Severstal: Steel Defect Detection](https://www.kaggle.com/competitions/severstal-steel-defect-detection/overview). A detailed description of the problem can be found on the Kaggle website. 

## Kaggle
To make it easier to set up the different libraries, here are links to the Jupyter Notebooks on Kaggle. The import paths have been adapted for the use on Kaggle. You must be invited first to have access to the files.
* [Model training](https://www.kaggle.com/code/lremane/train-model-steel-defect-detection)
* [Model evaluation](https://www.kaggle.com/code/lremane/evaluate-model-steel-defect-detection)

## Local Setup
### Prerequisites
Make sure you have Python 3.11 installed on your system, as it is required to run TensorFlow version 2.15.0 correctly.

### Installing Required Libraries
All the required libraries for this project are listed in the `requirements.txt` file. You can install these libraries using pip. Run the following command in your terminal:
```
pip install -r requirements.txt
```


## Understanding the Project Files
The project consists of several Jupyter notebook files and other resources:

- `train_model_steel_defect_detection.ipynb`: This notebook provides insights into how the model was trained. It's primarily for reading and understanding the model training process.
- `evaluate_model_steel_defect_detection.ipynb`: Use this notebook to interact with the model, visualize the results, and test its performance.

## Models
Two different models have been trained and can be found in the `models` directory:

- `steel_defect_detection_4000_images.h5`: This model was trained with 4,000 images.
- `steel_defect_detection_12000_images.h5`: This model was trained with 12,000 images.

Both models were trained with almost the same setup. Despite the U-Net architecture's high performance on small datasets, the model trained with 12,000 images performs slightly better. You can find the loss and metrics functions for both models in the `plots` subdirectory for comparison.

## Training Data
All the training data used for this project is accessible in the `data` directory.

## Commiting new models
Committing New Models

Since the models exceed GitHub's 100MB file size limit, 
you need to set up Git LFS to push new models to this repository.
1. **Download and Install Git LFS**
   * Navigate to [git-lfs](https://git-lfs.github.com/) and click Download.
   Alternatively, you can install Git LFS using a package manager.

2. **Locally setup Git LFS**
   * Run the following command in your terminal. You only need to do this once per user account.
   ```
   git lfs install
   ```

3. **Track Large Files** 
   * Change your current working directory to the repository where you want to use Git LFS.
   * To associate a file type in your repository with Git LFS, enter the following command in your terminal.
   This command tells Git LFS to manage all `*.h5` files.
   ```
   git lfs track "*.h5"
   ```

4. **Commit and Push Changes**
   * After running the `git lfs track` command, you need to commit the changes and push them to your repository.
      You can do this with the following commands:
   ```
   git add .gitattributes
   git commit -m "Track .h5 files using Git LFS"
   git push
   ```
