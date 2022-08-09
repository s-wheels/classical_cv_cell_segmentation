
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

### Further Improvements
If I were restricted to classical CV methods there are a few more approaches I would investigate:

## Deep Learning Segmentation Approach


### Tools

- HuggingFace
- PyTorch
- Weights & Biases - tracking model/data changes.
- Git - version control
- Black & isort - formatting

### Execution
Where do these jobs get executed? (locally, in the cloud) 

### Pipeline
How automated is the pipeline? (orchestration tools, CI/CD)


### Productisation

- Code maintainablity
- Code Refactoring


● Think about best engineering practice when you prepare the solution (for example code refactoring and productionisation etc.)
