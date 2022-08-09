
## Running The Code

All the code is in the cell_segmentation.ipynb notebook.

Please use pip to install from the requirements file and [download the data](https://bbbc.broadinstitute.org/BBBC020) and add to the data directory in the following structure:

```
classical_cv_cell_segmentation
│   README.md
│   cell_segmentation.ipynb - Jupyter Notebook containing cell segmentation code 
│   requirements.txt
│
└───data
    │
    └───BBBC020_v1_images
    │   │ folders containing cell images
    │
    └───BBC020_v1_outlines_cells
    │   │ cell masks
    │
    └───BBC020_v1_outlines_nuclei
        │ nuclei masks


```

## Classical CV Segmentation Approach

I tried 4 different methods directly implementable with OpenCV.

| Method  | Mean IoU |
| ------------- | ------------- |
| Binary Threshold | 0.4235  |
| Otsu Threshold  | 0.4439  |
| Gaussian Otsu Threshold  | 0.4439  |
| Adaptive Threshold  | 0.2914  |
<!-- 
### Further Improvements
If I were restricted to classical CV methods there are a few more approaches I would investigate: -->

## Deep Learning Segmentation Approach

### Model & Experiment

1. Investigation - Investigate SOTA approaches that best fit our needs (computational resources, inference time, performance etc). I would use [Papers With Code](https://paperswithcode.com/task/semantic-segmentation) as a first stop to investigate approaches that would be easily implementable.

2. Training Model - After choosing the model, I would ideally use a pretrained model (from HuggingFace, git etc) to start. Pretraining improves performance and reduces training time. I would use PyTorch and augmentation libraries to implement a dataset class for shuffling/augmenting data. This dataset class could be used with either HuggingFace or PyTorch. I would utilise the already developed code for producing inputs (cell images) and the targets (cell masks).

3. Tracking - I would use git for tracking of the code and github for remote storage. I would use Weights & Biases for tracking of: data versioning, model versioning, git commit, environment, experimental results & hyperparameters. I would also use Docker for reproducibility (this can also be used with Weights & Biases).

### Code

I would refactor the code into a sensible directory structure and after the initial experimentation I would utilise python scripts not jupyter notebooks. I would follow standard PEP8 style and I like to use tools such as Black & isort to automate the formatting of my code.


### Tools

- HuggingFace - pretrained models & training.
- PyTorch - data handling & model training.
- Weights & Biases - tracking model/data/experiment.
- Git & Github - version control.
- Black & isort - formatting code.
- Docker - environment control.
- Airflow - orchestration of pipeline.

### Execution & Pipeline

The execution environment would depend on the requirements of the project. For training ideally execution would happen on a server or in the cloud with more powerful resources.

If we wanted to build a pipeline I may utilise an orchestration tool such as Airflow which is open source and can integrate with most cloud providers. I would use Airflow to manage the following stages:

1. Data Ingestion.
2. Data Preprocessing/Transformation.
3. Model Training/Inference.
4. Model Evaluation.

Implementing CI/CD would allow for rapid iterations of development. Implementing a CI/CD workflow would require the creation of robust tests, for ML dev I would consider the specific unit tests, integration tests and data/model tests to create a reliable CI/CD workflow. Data tests would validate the data's properties and model tests would ensure model convergence/fitting as well as any other tests. Previously I have used 'unit tests' for model testing, where we utilised extremely difficult edge cases to test model performance. CI/CD for ML development has a few unique challenges in tracking models & data which Weights & Biases would assist with.
