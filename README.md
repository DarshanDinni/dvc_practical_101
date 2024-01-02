## 101: Data Versioning using DVC.

Learn the essentials of Data Version Control (DVC) with this project.

This project follows the steps outlined in the DVC documentation to help you get started quickly. [Click here to visit DVC documentation](https://dvc.org/doc/start/data-management/data-versioning)

### Getting Started

#### Step 1: Install DVC library.
```
pip install dvc
```

#### Step 2: Initialize DVC.
```
dvc init
```

#### Step 3: Download the data to work with.

**Note:** You can skip the Step 3, if you already have data that you want to track.
```
dvc get https://github.com/iterative/dataset-registry get-started/data.xml -o data/data.xml
```

#### Step 4: Track the dataset file using 'dvc add'.
```
dvc add data/data.xml
```

DVC stores information about the added file in a special .dvc file, named data/data.xml.dvc. This small metadata file serves as a placeholder for the original data for the purpose of Git tracking.
```
git add data/data.xml.dvc data/.gitignore
```

Follow these steps to efficiently version your data using DVC. Happy versioning!