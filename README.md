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

#### Step 4: Track the dataset file using `dvc add`.
```
dvc add data/data.xml
```

DVC stores information about the added file in a special `.dvc file`, named `data/data.xml.dvc`. This small metadata file serves as a placeholder for the original data for the purpose of Git tracking.
```
git add data/data.xml.dvc data/.gitignore
```

Follow these steps to efficiently version your data using DVC.

### Making Local Changes to the Data
Feel free to modify the data as needed; for example, you can copy and paste the same data into the `data.xml` file to make changes.

#### Track the Modified Data
To track the modified data, use the following commands:
```
dvc add data/data.xml
git commit data/data.xml.dvc -m "Dataset updates"
```
This step ensures that your changes to the data are versioned and can be tracked using DVC.

### Switching between versions
A commonly used workflow is to switch between versions using Git and DVC. Here's how you can do it:
```
git checkout <previous branch/commit>
dvc checkout
```
This sequence of commands allows you to switch to a specific Git branch or commit using git checkout and then synchronize the data in your workspace with the corresponding DVC-tracked version using dvc checkout.