# Brane Data Visualization Package for the Titanic dataset

The following repository comprises Implementation of a Visualization package in brane for Data Science tasks on a Kaggle competition dataset related to the sinking of the Titanic. This project correspond to Assignment 4.b of the Web Services and Cloud Based Systems at University of Amsterdam (G9).

## The Package (`titanicviz`)
The package definition is inside the `container.yml` file in the root of this repository. The package includes the train and testing datasets in the root of the package. This package is composed of three methods that can be used as building blocks in any [BraneScript](https://wiki.enablingpersonalizedinterventions.nl/user-guide/branescript/introduction.html) pipeline.  

### Create Histogram and KDE plot 

- **Method Global Name**: `plot_distribution` 
- **Description**: This method loads the given `data` into a Pandas dataframe and use the `feature` column to build the plot. The plot will be output with the title given in `plot_title`.
- **INPUT**: 
  - `data (str)`: File name of the data to plot the Histogram plot. On first instance, you only have `'train.csv'` and `'test.csv'` to use. 
  - `feature (str)`: Name of the feature (i.e. column) to use for the plot 
  - `plot_title (str)`: 
- **OUTPUT**:
  - `output`: 

### Create Stacked Barchart

### Create multi-column Barchart

## Usage example


