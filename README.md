# Machine Learning Model Documentation

## Used Technologies
To develop this machine learning model, we use a ranking algorithm with TensorFlow. We also used some Python libraries in this project, including:

- **Python 3.7.13 version**
- **TensorFlow 2.8.2 version**
- **Pandas 1.3.5 version**
- **Numpy 1.21.6 version**
- **scikit-learn 0.24.2 version**

## Dataset
We collected our dataset from an Excel file containing various business ideas and corresponding labels. The dataset includes the following features:

- Hobi (Hobbies)
- Pekerjaan (Occupation)
- Lama Pengalaman (Experience Duration)
- Aset (Assets)
- Ide Bisnis (Business Ideas)
- Label (Labels)

### Dataset Source
The dataset was sourced from Kaggle. You can find and download the dataset from the following link:
[Business Ideas](https://docs.google.com/spreadsheets/d/1ZNIXlt_KS4KLEFrf58dKmwccf6nniFYqXo0mq7hnyvU/edit?usp=sharing)

## Data Processing
The dataset was preprocessed using the following steps:

1. **Normalization**: The label column was normalized using `MinMaxScaler`.
2. **TensorFlow Dataset Creation**: The data was converted into a TensorFlow dataset format suitable for model training.

## Model Architecture
We developed a ranking model using TensorFlow with the following architecture:

- **Input Layers**: Inputs for `hobi`, `pekerjaan`, `lama_pengalaman`, `aset`, and `ide_bisnis`.
- **Embedding Layers**: Embedding layers for each categorical input.
- **Text Vectorization and Embedding**: Text vectorization and embedding for `ide_bisnis`.
- **Dense Layers**: Several dense layers to compute similarity and make predictions.

## Model Training
The model was trained with the following configurations:

- **Loss Function**: Mean Squared Error
- **Optimizer**: Adagrad with a learning rate of 0.1
- **Metrics**: Root Mean Squared Error
- **Training and Testing Split**: 80% training, 20% testing

## Model Evaluation
The model was evaluated using the test dataset, and performance metrics were computed.

## Model Saving
The best-performing model was saved in HDF5 format for future use:

```python
model.save('/content/save/')
