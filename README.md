# Classifying 2024 MLB Pitches
## *Alexander J. Sutherland* [(website)](https://www.alexandersutherland.com/data-science)

### (1) Overview  
No two pitchers truly throw the same pitch the same way. For example, Tim Hill threw his four-seam fastball with an average of 17.9in of arm-side movement, 4.4in of vertical movement, and at 90.7 MPH. Mason Miller, on the other hand, threw his four-seam fastball with 9.7in of arm-side movement, 16.6in of vertical movement, and at 100.9 MPH. In this project, we classify pitch types using observable data, paying special attention to the inclusion/exclusion of pitcher IDs and the differences between classical machine learning models and a simple neural network.  

### (2) Project Stakeholders
MLB, MiLB, Professional baseball organizations, Professional baseball players, Baseball fans.

### (3) Methods  
For our classical models, we considered k-nearest neighbors, decision trees, and several ensemble methods with 10-fold cross validation and hyperparameter tuning via grid search. These models were compared against each other and a baseline model, where the odds of a pitch being predicted as a given class where given by the overall distribution of the test dataset.  
  
For the neural network, we constructed a basic neural network with multiple linear layers using pytorch.

### (4) Key Performance Indicators (KPIs)  
For all our models, we prioritize model accuracy. We additionally track precision, recall, and F1-score as secondary metrics.

### (5) Files and Data

#### (5.1) Jupyter Notebooks (.IPYNB)
The main files for this project are Jupyter notebooks, of which there are five:
+ `Classifying 2024 MLB Pitches - Executed` is the primary file with all cells executed and saved.
+ `Classifying 2024 MLB Pitches - Unexecuted` is the primary file with no cells executed.
+ `2024 MLB Pitch Data - Month by Month Queries using Pybaseball` uses `Pybaseball` to directly query *Baseball Savant*. Running this notebook accesses the original data and exports the data locally as CSVs. This notebook is included for completeness, but does not need to be ran, as the data is included with this project.
+ `2024 MLB Pitch Data - Merging, Cleaning, and Processing` imports the data that was exported from *Baseball Savant* and does all of the necessary steps with the data before importing into the main project. This notebook does need to be ran, as the primary data file was too large to include in this repository. 
  
The data collection and processing is discussed further in `Appendix A` of `Classifying 2024 MLB Pitches - Executed`.

#### (5.2) Microsoft Word Documents (.DOC)
The `Executive Summary` is essentially a shorter version of this README file detailing the most important parts of this project.

#### (5.3) Adobe Acrobat Documents (.PDF)
For greater accessibility, we include a PDF version of the Word document `Executive Summary`.

#### (5.4) Comma Separated Values Files (.CSV)

##### (5.4.1) Data Collection Imports and Exports

###### (5.4.1.1) `2024month?`
CSV files titled in the style `2024month?` contain MLB pitch data exported from the `2024 MLB Pitch Data - Month by Month Queries using Pybaseball` notebook.

###### (5.4.1.2) `int_???_grid_results`  
CSV files titled in the style `int_???_grid_results` are exports from hyperparameter tuning from various models that are imported into `Classifying 2024 MLB Pitches - Unexecuted` to avoid having to re-run the grid searches.

###### (5.4.1.3) `no_pitcher_grid_results`
This is the export from the hyperparameter tuning done for the `k`-nearest neighbors model in `Section 4` to be imported into `Classifying 2024 MLB Pitches - Unexecuted`.  

### (6) Conclusions and Future Work
When using a pitcher identifier, almost all classical models performed very well  - four of the five (non-baseline) models had an accuracy over 95%. Without the pitcher identifier, our one classical model still performed well (with an accuracy of 84%), but with a noticeable drop in accuracy. The specific neural network in question did not perform as well (with an accuracy of 67%), but there is reason to believe that a more sophisticated architecture could lead to better results.

### (7) References
+ LeDoux, J., & Schorr, M. (2024, Oct 03). *Pybaseball Github Repository Readme.* Retrieved from Pybaseball Github Repository: https://github.com/jldbc/pybaseball
+ MLB Advanced Media, LP. (2024, Oct 03). *Statcast Search.* Retrieved from Baseball Savant: https://baseballsavant.mlb.com/statcast_search
