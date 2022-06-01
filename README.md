# Brane Data Visualization Package for the Titanic dataset

The following repository contains the implementation of a **visualization package in brane** for Data Science tasks on a Kaggle competition dataset related to the sinking of the Titanic. This project correspond to Assignment 4.b of the Web Services and Cloud Based Systems at University of Amsterdam (G9).

## The Package (`titanicviz`)
The package uses Python 3.8 as programming language for this task. In addition to this, it uses Pandas to manage the datasets and matplotlib and seaborn for generating the visual plots. 
The package definition is inside the `container.yml` file in the root of this repository. The package includes the train and testing datasets in the root of the package. This package is composed of three methods that can be used as building blocks in any [BraneScript](https://wiki.enablingpersonalizedinterventions.nl/user-guide/branescript/introduction.html) pipeline. 
- Create Histogram and KDE plot
- Create Stacked Barchart
- Create multi-column Barchart  

### Create Histogram and KDE plot 

- **Method Global Name**: `plot_distribution` 
- **Description**: This method loads the given `data` into a Pandas dataframe and use the `feature` column to build the plot. The plot will be output with the title given in `plot_title`.
- **INPUT**: 
  - `data`(str): File name of the data to plot the Histogram plot. On first instance, you only have `'train.csv'` and `'test.csv'` to use. 
  - `feature`(str): Name of the feature (i.e. column) to use for the plot 
  - `plot_title`(str): Title of the plot
- **OUTPUT**:
  - `output`(str): Name of the file that was generated with the plot image

### Create Stacked Barchart
- **Method Global Name**: `feature_group_bar_chart` 
- **Description**: This method loads the given `data` into a Pandas dataframe and builds a stacked barchart using `feature` for counting and a binary feature columns `feature_y_binary` to segregate each bar into two stacked groups. The plot will be output with the y-axis title given in `y_label`. The plot will be output with the title given in `plot_title`. The plot will be output with the x-axis labels given in `feature_y_index`.
- **INPUT**: 
  - `data`(str): File name of the data to plot the stacked bar chart. On first instance, you only have `'train.csv'` and `'test.csv'` to use. 
  - `feature`(str): Name of the feature (i.e. column) to use for the bar heights 
  - `feature_y_binary`(str): Name of the binary feature (i.e. column) to use for the stacking the bars 
  - `plot_title`(str): Title of the plot
  - `y_label`(str): Label of the plot y-axis
  - `feature_y_index`(List[str]): Labels of the plot x-axis. Must be of length 2.
- **OUTPUT**:
  - `output`(str): Name of the file that was generated with the plot image

### Create grouped bar chart
- **Method Global Name**: `bar_chart_compare` 
- **Description**: This method loads the given `data` into a Pandas dataframe and builds a multi-column barchart. The height of the bars is determined by `feature_y`. Each group of bars is separated by each possible value of `feature_1`. Inside each group, bars are separated by each possible value of `feature_2`. The latter is optional. The plot will be output with the y-axis title given in `y_label`. The plot will be output with the title given in `plot_title`. 
- **INPUT**: 
  - `data`(str): File name of the data to plot the stacked bar chart. On first instance, you only have `'train.csv'` and `'test.csv'` to use. 
  - `feature_1`(str): Name of the categorical feature (i.e. column) to separate each group of bars.
  - `feature_2`(str): Name of the categorical feature (i.e. column) to separate the bars of each group. If `'None'`, then no groups are formed.
  - `feature_y`(str): Name of the feature (i.e. column) that determines the height of the bars. 
  - `plot_title`(str): Title of the plot
  - `y_label`(str): Label of the plot y-axis
- **OUTPUT**:
  - `output`(str): Name of the file that was generated with the plot image
  

## Unit Tests (locally)
Unit tests were implemented in [Pytest](https://docs.pytest.org/en/6.2.x/contents.html). There are three tests that needs to pass. Each test checks the correctness YAML output of each method. These methods only check if the output have a correct format. To execute locally you can execute the following commands:
1. Install pipenv `pip3 install pipenv`
2. Run the tests `pipenv run test`


## Building with Brane (locally)
1. [Install](https://onnovalkering.gitbook.io/brane/getting-started/installation) Brane CLI.
2. Run `brane build container.yml`

The repository is built in such a way that a `brane import` can also be done using the following command:  

```
brane import Web-Services-and-Cloud-Based-Systems-G9/brane-titanic-visualization
```

## Automated Tests
This repository a **GitHub Action** workflows configured that runs automated tests to ensure that the methods of the packages work correctly (`.github/workflows/pytest.yml`). In addition to this, it makes sure that the package can be built in Brane successfully by implementing a test which tries to do the building process of the package (`.github/workflows/ci.yml`).

## Usage example
Once you have build the package with Brane, you can use the following examples to try the package. 

TODO


## DOI

TODO

