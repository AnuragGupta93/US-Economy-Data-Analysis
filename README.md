# US-Economy-Data-Analysis
## Analyzing-US-Economic-Data-and-Building-a-Dashboard Using Python, Numpy and Pandas

### Prerequisites

* [Python](https://www.python.org/downloads/release/python-360/)
* [Numpy](https://pypi.org/project/numpy/)
* [Pandads](https://pandas.pydata.org/getpandas.html)

### Project Flow:
#### Description
In this project, I am examining how changes in GDP impact the unemployment rate using US Economy Data with the help of Python, Numpy and Pandas.

* Importing Libraries
  ```
  from bokeh.plotting import figure, output_file, show,output_notebook
  output_notebook() 
  ```
* Defining the Dashboard
```
    def make_dashboard(x, gdp_change, unemployment, title, file_name):
    output_file(file_name)
    p = figure(title=title, x_axis_label='year', y_axis_label='%')
    p.line(x.squeeze(), gdp_change.squeeze(), color="firebrick", line_width=4, legend="% GDP change")
    p.line(x.squeeze(), unemployment.squeeze(), line_width=4, legend="% unemployed")
    show(p)
```
* The dictionary  links contain the CSV files with all the data. The value for the key GDP is the file that contains the GDP data. The value for the key unemployment contains the unemployment data.
```
links={'GDP':'https://s3-api.us-geo.objectstorage.softlayer.net/cf-courses-data/CognitiveClass/PY0101EN/projects/coursera_project/clean_gdp.csv',\
       'unemployment':'https://s3-api.us-geo.objectstorage.softlayer.net/cf-courses-data/CognitiveClass/PY0101EN/projects/coursera_project/clean_unemployment.csv'}
```

* Created a dataframe that contains the GDP data and displaying using the method head.
![alt_text](https://github.com/AnuragGupta93/US-Economy-Data-Analysis/blob/master/gdp_df.png)
* Created a dataframe that contains the unemployment data. Displaying the first five rows 
  of the dataframe using the method head().
  ![alt_text](https://github.com/AnuragGupta93/US-Economy-Data-Analysis/blob/master/unemployment_df.png)
* Displayed a dataframe where unemployment was greater than 8.5% . 
![alt_text](https://github.com/AnuragGupta93/US-Economy-Data-Analysis/blob/master/high_employment.png)
* Use the function make_dashboard to make a dashboard.
![alt_text](https://github.com/AnuragGupta93/US-Economy-Data-Analysis/blob/master/dash_board.png)


