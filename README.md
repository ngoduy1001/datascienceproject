
### COGS 108 - Final Project

# Gun Laws and Mass Shootings




### Group Member Names & IDs

Duy Ngo - A14695298
 <br>Hanyang(Patrick) Liu - A13924097
 <br>Behnam Shamloufard - A15708967
 <br>Josephine Reyes - A13850298
 <br>Caleb Lopez - A14899660
 <br>Fatin Pasha - A14577145




# Introduction & Background








### Overview

Mass shootings in the United States have prompted controversial debates over the main cause of gun violence. In our project, we explore the relationship between the frequency of mass shootings and the strictness of gun laws for each state. We pulled four data sets that include the incident date, state, city or county, address, # of people killed, and # of people injured. We also utilize a data set providing the gun laws strength score for 2018 based off a letter grade from A to F, with A being more strict and F being more lenient. 

### Research Question

What is the relationship between the local gun policy and the number of mass shootings that occur within each state? More specifically, does a state with a strict gun policy typically have fewer mass shootings?


### Background & Prior Work

The recent mass shootings in El Paso, Texas, and Dayton, Ohio – along with many others throughout the year of 2019 alone, have brought our group’s attention to research about mass shootings in the United States. With the US having the highest levels of gun violence compared to any other developed country, we decided to research if having a stricter gun policy will help decrease the number of mass shootings.

Gun ownership in the United States is a unique right that is guaranteed by this nation's Second Amendment. This is unique because most developed countries in the world have various forms of stricter gun laws. The concept of gun ownership as a right in the United States is rooted in the nation’s historic background and the revolutionary war, as it played a major role in colonial and independent United States. However, this right has recently been under scrutiny as an increasing number of incidents involving guns end in tragedy. Cases such as the Orlando Pulse Nighclub shooting, San Bernardino shooting, Las Vegas Harvest Festival shooting, Stoneman Douglas High School shooting and recently the school shooting at Santa Clarita are all instances which shook the nation as a whole. Such incidents fueled different groups in society to question the purpose and existence of the Second Amendment of the Constitution.

The concept of gun ownership is expected to be a topic of debate this year because of the upcoming presidential election in 2020. In the previous presidential election season of 2016, gun laws had been a subject of serious debate considering how certain mass shootings had occurred recently. This project aims to analyze the relationship between the gun laws of individual states and the number of mass shootings that occurred in those respective states. The purpose of this project is to potentially establish a pattern between gun laws and cases of mass shootings by analyzing a relationship between gun laws, population, and number of mass shootings in individual American states in comparison to other states.

While mass shootings are the focus of our data and data analysis, it is important to note that there are various definitions and occurances within the category of gun deaths. It is significant to define considering most cases of existing research on this topic is taking into account these other forms of gun death (i.e. violent crime, suicide). It is also significant to state that correlation with mass shootings might be different from the correlation to gun deaths in general. In fact the majority of gun deaths are not due to mass shootings but rather to suicides.

The motivating factor that further fueled this project are the conflicting research and findings which contradicted the relationship between gun laws and mass shootings. For this project, the concept of correlation between stricter gun laws and mass shootings have been discussed in two papers. The first research concluded that there is a relationship between mass shootings and gun law (Reeping, Cerdá, Kalesan, Wiebe, Galea & Branas, 2019). The second research found no correlation between gun regulation and occurence of mass shooting (Lewis, 2018). The conflicting research regarding the subject prompted us to investigate the relationship between mass shooting and gun regulations.

Citations: <br>
Lewis, J. S. (2018). The Relationship between Gun Control Strictness and Mass Murder in the United States: A National Study 2009-2015. International Social Science Review, 94(2). Retrieved from https://digitalcommons.northgeorgia.edu/cgi/viewcontent.cgi?article=1287&context=issr <br><br>
Reeping, P. M., Cerdá, M., Kalesan, B., Wiebe, D. J., Galea, S., & Branas, C. C. (2019). State gun laws, gun ownership, and mass shootings in the US: cross sectional time series. Bmj, l542. doi: 10.1136/bmj.l542

Links: 
<br>https://www.gunviolencearchive.org/methodology

https://www.businessinsider.com/gun-control-research-how-policies-can-reduce-deaths-2019-8#in-2017-the-most-recent-year-for-which-data-is-available-39773-people-in-the-us-died-from-firearms-according-to-the-centers-for-disease-control-and-prevention-cdc-1

https://www.nytimes.com/interactive/2017/10/05/upshot/how-to-reduce-mass-shooting-deaths-experts-say-these-gun-laws-could-help.html

https://www.hbs.edu/faculty/Publication%20Files/16-126_ce055015-fc1c-4a8c-9a8a-8a9361d808bb.pdf

https://www.bmj.com/content/364/bmj.l542


### Hypothesis

Since gun regulation policies vary from state to state across the U.S. , we predict that the number of mass shootings in a state is strongly correlated with how strict its gun policy is. 

We will assume that gun laws that are more restrictive will make it less likely for criminals, people with mental health illnesses, and people with histories of violence to have access to guns. Thus, states with permissive gun laws will have a higher rate of mass shootings than other states on the restrictive end.



# Datasets

### a) Mass shootings record from 2015-2018 
Link: https://www.gunviolencearchive.org/reports
Number of Observations: 1,450 observations

Description: This dataset contains the record of every mass shooting in the U.S from 2015 to 2018.
Each data row has the following columns: Incident Date, State, City/County, Address, #(of people) Killed, #Injured, and Operations (Used to provide links to sources). 
<br>For our research question, we choose to use these columns:
- Incident Date
- State
- City/County
- #Killed 
- #Injured

Definition of mass shooting: Four or more shot and/or killed in a single event [incident], at the same general time and location, not including the shooter.

### b) State Population Totals and Components of Change: 2010-2018
Link: https://www.census.gov/data/datasets/time-series/demo/popest/2010s-state-total.html
<br>Number of Observations: 57

Description: This dataset contains a record of population estimates from 2010-2018. 
<br>For our research question, we choose to use these columns:
- NAME: of state
- POPESTIMATE2015: population estimate for 2015
- POPESTIMATE2016: population estimate for 2016
- POPESTIMATE2017: population estimate for 2017
- POPESTIMATE2018: population estimate for 2018

### c) Gun Law Score Card
Link: https://lawcenter.giffords.org/scorecard/#MT
<br> Number of Observations: 50

Description: This data set contains a record of each state's gun death rate, along with a corresponding "score" associated with how strong each respective state's gun laws are. Each data row has the following columns: Gun Law Strength(Ranked), State, 2018 Grade, Gun Death Rate (Ranked), Gun Death Rate Per 100K. All columns were used in our analysis. 

# 1. Project Setup







### 1.1 Import Libraries


```python
# !pip install --user geopandas
# !pip install --user libpysal
# !pip install --user descartes

```


```python
# Display plots directly in the notebook instead of in a new window
%matplotlib inline
# Import libraries
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
# Erase warnings
import warnings
warnings.filterwarnings("ignore")
#For geo infomation processing
import geopandas as gpd
import libpysal
from shapely.geometry import Point
from scipy.stats import chi2_contingency
from scipy import stats
```

### 1.2 Configure Libraries


```python
# Configure libraries
# The seaborn library makes plots look nicer
sns.set()
sns.set_context('talk')

# Don't display too many rows/cols of DataFrames
pd.options.display.max_rows = 15
pd.options.display.max_columns = 20

# Round decimals when displaying DataFrames
pd.set_option('precision', 2)
```

### 1.3 Read data from csv file


```python
data_2018 = pd.read_csv('2018.csv')
data_2017 = pd.read_csv('2017.csv')
data_2016 = pd.read_csv('2016.csv')
data_2015 = pd.read_csv('2015.csv')
```


```python
data_2018
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Incident Date</th>
      <th>State</th>
      <th>City Or County</th>
      <th>Address</th>
      <th># Killed</th>
      <th># Injured</th>
      <th>Operations</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>December 31, 2018</td>
      <td>Ohio</td>
      <td>Cleveland</td>
      <td>4462 Denison Ave</td>
      <td>3</td>
      <td>2</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>December 29, 2018</td>
      <td>Ohio</td>
      <td>Lima</td>
      <td>904 S Main St</td>
      <td>1</td>
      <td>3</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>December 28, 2018</td>
      <td>Missouri</td>
      <td>Saint Charles</td>
      <td>150 Whetstone Dr</td>
      <td>4</td>
      <td>1</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>December 24, 2018</td>
      <td>Louisiana</td>
      <td>Lutcher</td>
      <td>2176 Main St</td>
      <td>2</td>
      <td>2</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>December 23, 2018</td>
      <td>Missouri</td>
      <td>Springfield</td>
      <td>1042 W College St</td>
      <td>1</td>
      <td>6</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>332</th>
      <td>January 7, 2018</td>
      <td>Alabama</td>
      <td>Union Springs</td>
      <td>US-29</td>
      <td>1</td>
      <td>5</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>333</th>
      <td>January 7, 2018</td>
      <td>Florida</td>
      <td>Plantation</td>
      <td>5225 W Broward Blvd</td>
      <td>0</td>
      <td>4</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>334</th>
      <td>January 5, 2018</td>
      <td>Mississippi</td>
      <td>Hattiesburg</td>
      <td>6168 US 49</td>
      <td>0</td>
      <td>6</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>335</th>
      <td>January 4, 2018</td>
      <td>Arkansas</td>
      <td>Brinkley</td>
      <td>615 W 6th St</td>
      <td>1</td>
      <td>3</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>336</th>
      <td>January 1, 2018</td>
      <td>Alabama</td>
      <td>Huntsville</td>
      <td>2025 Sparkman Dr NW</td>
      <td>1</td>
      <td>3</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
<p>337 rows × 7 columns</p>
</div>




```python
data_2017
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Incident Date</th>
      <th>State</th>
      <th>City Or County</th>
      <th>Address</th>
      <th># Killed</th>
      <th># Injured</th>
      <th>Operations</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>December 31, 2017</td>
      <td>Colorado</td>
      <td>Littleton (Highlands Ranch)</td>
      <td>3404 E County Line Rd</td>
      <td>2</td>
      <td>6</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>December 31, 2017</td>
      <td>Illinois</td>
      <td>Chicago</td>
      <td>2335 Howard St</td>
      <td>0</td>
      <td>4</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>December 31, 2017</td>
      <td>New Jersey</td>
      <td>Long Branch</td>
      <td>635 Wall St</td>
      <td>4</td>
      <td>0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>December 27, 2017</td>
      <td>Nevada</td>
      <td>Las Vegas</td>
      <td>3750 E Bonanza Rd</td>
      <td>2</td>
      <td>2</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>December 26, 2017</td>
      <td>Florida</td>
      <td>Miami</td>
      <td>NW 18th Ave and 86th Ter</td>
      <td>0</td>
      <td>5</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>341</th>
      <td>January 4, 2017</td>
      <td>California</td>
      <td>Fontana</td>
      <td>14520 Village Drive</td>
      <td>3</td>
      <td>1</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>342</th>
      <td>January 3, 2017</td>
      <td>Texas</td>
      <td>Allen</td>
      <td>500 block of Hawthorne Drive</td>
      <td>0</td>
      <td>4</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>343</th>
      <td>January 1, 2017</td>
      <td>Mississippi</td>
      <td>Winstonville</td>
      <td>114 North Greyer Street</td>
      <td>0</td>
      <td>5</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>344</th>
      <td>January 1, 2017</td>
      <td>Texas</td>
      <td>Dallas</td>
      <td>9220 Skillman Street</td>
      <td>1</td>
      <td>3</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>345</th>
      <td>January 1, 2017</td>
      <td>Florida</td>
      <td>Miami</td>
      <td>8000 block of NW 14th Ave</td>
      <td>0</td>
      <td>7</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
<p>346 rows × 7 columns</p>
</div>




```python
data_2016
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Incident Date</th>
      <th>State</th>
      <th>City Or County</th>
      <th>Address</th>
      <th># Killed</th>
      <th># Injured</th>
      <th>Operations</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>December 31, 2016</td>
      <td>Georgia</td>
      <td>Lenox (El Dorado)</td>
      <td>27 Briarwood Ct</td>
      <td>2</td>
      <td>2</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>December 31, 2016</td>
      <td>Texas</td>
      <td>Houston</td>
      <td>3704 Fannin Street</td>
      <td>1</td>
      <td>3</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>December 30, 2016</td>
      <td>Ohio</td>
      <td>Mansfield</td>
      <td>3230 Possum Run Rd</td>
      <td>0</td>
      <td>5</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>December 30, 2016</td>
      <td>Connecticut</td>
      <td>Wallingford</td>
      <td>95 S Turnpike Rd</td>
      <td>2</td>
      <td>3</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>December 28, 2016</td>
      <td>Georgia</td>
      <td>Columbus</td>
      <td>2914 10th Street</td>
      <td>1</td>
      <td>4</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>377</th>
      <td>January 11, 2016</td>
      <td>Delaware</td>
      <td>Wilmington</td>
      <td>900 block of Brown Street</td>
      <td>1</td>
      <td>4</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>378</th>
      <td>January 8, 2016</td>
      <td>District of Columbia</td>
      <td>Washington</td>
      <td>1700 E Capitol St NE</td>
      <td>0</td>
      <td>4</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>379</th>
      <td>January 8, 2016</td>
      <td>Illinois</td>
      <td>Chicago</td>
      <td>1500 block of South Kedzie</td>
      <td>1</td>
      <td>4</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>380</th>
      <td>January 7, 2016</td>
      <td>Tennessee</td>
      <td>Memphis</td>
      <td>3800 block of Kerwood Avenue</td>
      <td>1</td>
      <td>3</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>381</th>
      <td>January 6, 2016</td>
      <td>Florida</td>
      <td>Lakeland</td>
      <td>2312 East Magnolia Street</td>
      <td>3</td>
      <td>1</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
<p>382 rows × 7 columns</p>
</div>




```python
data_2015
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Incident ID</th>
      <th>Incident Date</th>
      <th>State</th>
      <th>City Or County</th>
      <th>Address</th>
      <th># Killed</th>
      <th># Injured</th>
      <th>Operations</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>476321</td>
      <td>December 31, 2015</td>
      <td>Louisiana</td>
      <td>New Orleans</td>
      <td>1900 block of Amelia Street</td>
      <td>0</td>
      <td>6</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>473882</td>
      <td>December 27, 2015</td>
      <td>Tennessee</td>
      <td>Jackson</td>
      <td>North Parkway</td>
      <td>0</td>
      <td>4</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>472268</td>
      <td>December 26, 2015</td>
      <td>Pennsylvania</td>
      <td>Philadelphia</td>
      <td>4210 Macalester St</td>
      <td>0</td>
      <td>4</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>471867</td>
      <td>December 25, 2015</td>
      <td>Florida</td>
      <td>Jacksonville</td>
      <td>Franklin and Odessa</td>
      <td>0</td>
      <td>4</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>471860</td>
      <td>December 25, 2015</td>
      <td>Alabama</td>
      <td>Mobile</td>
      <td>785 Schillinger Rd S</td>
      <td>0</td>
      <td>4</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>330</th>
      <td>274867</td>
      <td>January 6, 2015</td>
      <td>Florida</td>
      <td>Miami</td>
      <td>1300 block of NW 62nd Street</td>
      <td>1</td>
      <td>3</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>331</th>
      <td>273535</td>
      <td>January 4, 2015</td>
      <td>Virginia</td>
      <td>Roanoke</td>
      <td>3634 Shenandoah Ave NW</td>
      <td>2</td>
      <td>4</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>332</th>
      <td>273397</td>
      <td>January 4, 2015</td>
      <td>Texas</td>
      <td>Dallas</td>
      <td>2000 block of Ben Hur St.</td>
      <td>3</td>
      <td>1</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>333</th>
      <td>273965</td>
      <td>January 2, 2015</td>
      <td>Georgia</td>
      <td>Savannah</td>
      <td>500 block of W. 54th Street</td>
      <td>1</td>
      <td>4</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>334</th>
      <td>272016</td>
      <td>January 1, 2015</td>
      <td>Tennessee</td>
      <td>Memphis</td>
      <td>Interstate 240 and Poplar Avenue</td>
      <td>0</td>
      <td>5</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
<p>335 rows × 8 columns</p>
</div>



# 2. Data Wrangling/Cleaning & Pre-Processing

In this section, we reviewed the dataset we have and clean it based on what we need. In the orginal dataset, there are Incident ID#, Icident Date, State, City or county, Address, #killed, #injured and operations. Some of the features are not useful to us. 

For example, column Operations is unknown to us, there is no information on what type of data is included in this column and most of the data points in this feature are NaN, so we choose to drop this feature. 

In addition, to protect the privacy of the victims, we are not including detalied address in this study. Also we believe the city or county can provide us enough geological information we need for this project, that's why we also dropped that column. 





### 2.1 Transform everything into dataframe



```python
#
df2015 = pd.DataFrame(data_2015)
df2016 = pd.DataFrame(data_2016)
df2017 = pd.DataFrame(data_2017)
df2018 = pd.DataFrame(data_2018)
```

### 2.2 Remove and/or rename unnecessary columns

As discussed above, we think it is reasonable to drop both Operations and Address columns.

As for Incident ID, we do not need that information in our project either and we choose to remove this column from our dataset too.


```python
#Drop the incident ID column from year 2015
df2015 = df2015.drop(columns=['Incident ID'])
#Drop the Operations and Address columnn in all the datasets
dfs = [df2015, df2016, df2017, df2018]
for df in dfs:
    df.drop(['Operations', 'Address'], inplace=True, axis=1, errors='ignore')

```


```python

```


```python
df2015
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Incident Date</th>
      <th>State</th>
      <th>City Or County</th>
      <th># Killed</th>
      <th># Injured</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>December 31, 2015</td>
      <td>Louisiana</td>
      <td>New Orleans</td>
      <td>0</td>
      <td>6</td>
    </tr>
    <tr>
      <th>1</th>
      <td>December 27, 2015</td>
      <td>Tennessee</td>
      <td>Jackson</td>
      <td>0</td>
      <td>4</td>
    </tr>
    <tr>
      <th>2</th>
      <td>December 26, 2015</td>
      <td>Pennsylvania</td>
      <td>Philadelphia</td>
      <td>0</td>
      <td>4</td>
    </tr>
    <tr>
      <th>3</th>
      <td>December 25, 2015</td>
      <td>Florida</td>
      <td>Jacksonville</td>
      <td>0</td>
      <td>4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>December 25, 2015</td>
      <td>Alabama</td>
      <td>Mobile</td>
      <td>0</td>
      <td>4</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>330</th>
      <td>January 6, 2015</td>
      <td>Florida</td>
      <td>Miami</td>
      <td>1</td>
      <td>3</td>
    </tr>
    <tr>
      <th>331</th>
      <td>January 4, 2015</td>
      <td>Virginia</td>
      <td>Roanoke</td>
      <td>2</td>
      <td>4</td>
    </tr>
    <tr>
      <th>332</th>
      <td>January 4, 2015</td>
      <td>Texas</td>
      <td>Dallas</td>
      <td>3</td>
      <td>1</td>
    </tr>
    <tr>
      <th>333</th>
      <td>January 2, 2015</td>
      <td>Georgia</td>
      <td>Savannah</td>
      <td>1</td>
      <td>4</td>
    </tr>
    <tr>
      <th>334</th>
      <td>January 1, 2015</td>
      <td>Tennessee</td>
      <td>Memphis</td>
      <td>0</td>
      <td>5</td>
    </tr>
  </tbody>
</table>
<p>335 rows × 5 columns</p>
</div>



### 2.3 Sort the datasets by ascending date

We also sort the date of the incients so it's easier to look at later.


```python
for df in dfs:
    # keep the index order
    idx=df.index.values
    df.iloc[:] = df.iloc[::-1].values
    df.index = idx
df2018
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Incident Date</th>
      <th>State</th>
      <th>City Or County</th>
      <th># Killed</th>
      <th># Injured</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>January 1, 2018</td>
      <td>Alabama</td>
      <td>Huntsville</td>
      <td>1</td>
      <td>3</td>
    </tr>
    <tr>
      <th>1</th>
      <td>January 4, 2018</td>
      <td>Arkansas</td>
      <td>Brinkley</td>
      <td>1</td>
      <td>3</td>
    </tr>
    <tr>
      <th>2</th>
      <td>January 5, 2018</td>
      <td>Mississippi</td>
      <td>Hattiesburg</td>
      <td>0</td>
      <td>6</td>
    </tr>
    <tr>
      <th>3</th>
      <td>January 7, 2018</td>
      <td>Florida</td>
      <td>Plantation</td>
      <td>0</td>
      <td>4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>January 7, 2018</td>
      <td>Alabama</td>
      <td>Union Springs</td>
      <td>1</td>
      <td>5</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>332</th>
      <td>December 23, 2018</td>
      <td>Missouri</td>
      <td>Springfield</td>
      <td>1</td>
      <td>6</td>
    </tr>
    <tr>
      <th>333</th>
      <td>December 24, 2018</td>
      <td>Louisiana</td>
      <td>Lutcher</td>
      <td>2</td>
      <td>2</td>
    </tr>
    <tr>
      <th>334</th>
      <td>December 28, 2018</td>
      <td>Missouri</td>
      <td>Saint Charles</td>
      <td>4</td>
      <td>1</td>
    </tr>
    <tr>
      <th>335</th>
      <td>December 29, 2018</td>
      <td>Ohio</td>
      <td>Lima</td>
      <td>1</td>
      <td>3</td>
    </tr>
    <tr>
      <th>336</th>
      <td>December 31, 2018</td>
      <td>Ohio</td>
      <td>Cleveland</td>
      <td>3</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
<p>337 rows × 5 columns</p>
</div>



### 2.4 Combine the data from the four years together

Merge all the data from four years together with the form we just made. After this step, the dataset is ready to go with all the useful features we need for this project.


```python
df = pd.concat([df2015, df2016, df2017, df2018], join="inner", ignore_index = True)
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Incident Date</th>
      <th>State</th>
      <th>City Or County</th>
      <th># Killed</th>
      <th># Injured</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>January 1, 2015</td>
      <td>Tennessee</td>
      <td>Memphis</td>
      <td>0</td>
      <td>5</td>
    </tr>
    <tr>
      <th>1</th>
      <td>January 2, 2015</td>
      <td>Georgia</td>
      <td>Savannah</td>
      <td>1</td>
      <td>4</td>
    </tr>
    <tr>
      <th>2</th>
      <td>January 4, 2015</td>
      <td>Texas</td>
      <td>Dallas</td>
      <td>3</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>January 4, 2015</td>
      <td>Virginia</td>
      <td>Roanoke</td>
      <td>2</td>
      <td>4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>January 6, 2015</td>
      <td>Florida</td>
      <td>Miami</td>
      <td>1</td>
      <td>3</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1395</th>
      <td>December 23, 2018</td>
      <td>Missouri</td>
      <td>Springfield</td>
      <td>1</td>
      <td>6</td>
    </tr>
    <tr>
      <th>1396</th>
      <td>December 24, 2018</td>
      <td>Louisiana</td>
      <td>Lutcher</td>
      <td>2</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1397</th>
      <td>December 28, 2018</td>
      <td>Missouri</td>
      <td>Saint Charles</td>
      <td>4</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1398</th>
      <td>December 29, 2018</td>
      <td>Ohio</td>
      <td>Lima</td>
      <td>1</td>
      <td>3</td>
    </tr>
    <tr>
      <th>1399</th>
      <td>December 31, 2018</td>
      <td>Ohio</td>
      <td>Cleveland</td>
      <td>3</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
<p>1400 rows × 5 columns</p>
</div>



# 3. Data Visualization & Analysis


In this section, we will visualize the dataset and see what we can discover from the dataset itself. 




### 3.1 Pre-visualization

We are trying to get the number of mass shootings in each state and save it into a new dataframe.


```python
#Create a dataframe to store number of mass shootings in each state
count_df = df[['State']].copy()
#Create a new count column
count_df['Shootings'] = count_df.groupby(['State'])['State'].transform('count')
#drop duplicate rows
count_df = count_df.drop_duplicates(subset=['State'], keep='first')
#Sort by descending number of shootings 
count_df.sort_values(by=['Shootings'], ascending=False)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>State</th>
      <th>Shootings</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>7</th>
      <td>California</td>
      <td>145</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Illinois</td>
      <td>138</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Florida</td>
      <td>109</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Texas</td>
      <td>88</td>
    </tr>
    <tr>
      <th>18</th>
      <td>New York</td>
      <td>62</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>138</th>
      <td>Rhode Island</td>
      <td>1</td>
    </tr>
    <tr>
      <th>204</th>
      <td>Vermont</td>
      <td>1</td>
    </tr>
    <tr>
      <th>251</th>
      <td>South Dakota</td>
      <td>1</td>
    </tr>
    <tr>
      <th>437</th>
      <td>West Virginia</td>
      <td>1</td>
    </tr>
    <tr>
      <th>904</th>
      <td>Maine</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
<p>45 rows × 2 columns</p>
</div>




```python
#plot the number of mass shottings per state in the graph
# Seaborn barplot
fig=plt.figure(figsize=(20,10))
chart = sns.countplot(
    data=df,
    x='State',
    palette='Set1', order = df['State'].value_counts().index
)
plt.xlabel("State Name")
plt.ylabel('Mass Shootings Count')
# rotate x label to look cleaner
chart.set_xticklabels(chart.get_xticklabels(), rotation=70, horizontalalignment='right')
plt.show(fig)

```


![png](FinalProject_files/FinalProject_40_0.png)


## Number of Mass Shootings by State from 2015-2018
### Interpretation

This bar plot shows the number of mass shootings in each state from 2015-2018 in descending order. The x-axis represents the name of the states, the y-axis represents the count of mass shootings.

### Data Analysis

This is just a pre-visualization that helps us to make sense of the raw data as it stands. From this plot, we can see that California, Illinois, and Florida are the top 3 states in number of mass shootings.

However, we also acknowledge the fact that these top states also have more population than other states. Simply compare the absolute number is not justify and we would like to get the information on the population of each state.





### 3.2 Population

In this part, we would like to get the population information of each state into this dataset and then plot the mass shootings distribution in the U.S from 2015-2018 under population density. In order to do that, we need to get the geometry information of each city and add it to our dataframe, then we calculate the mean population of each city from 2015-2018 and add that information to the dataframe too. This will tell us if there is coorelation between population dencity and mass shotting indicent numbers.

The first variable that we decided to explore is the population of each state from 2015-2018.


```python
#Prepare a geotable for geospatial graph
geo_table = gpd.read_file(libpysal.examples.get_path('us48.shp'))
geo_table
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>AREA</th>
      <th>PERIMETER</th>
      <th>STATE_</th>
      <th>STATE_ID</th>
      <th>STATE_NAME</th>
      <th>STATE_FIPS</th>
      <th>SUB_REGION</th>
      <th>STATE_ABBR</th>
      <th>geometry</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>20.75</td>
      <td>34.96</td>
      <td>1</td>
      <td>1</td>
      <td>Washington</td>
      <td>53</td>
      <td>Pacific</td>
      <td>WA</td>
      <td>MULTIPOLYGON (((-122.40075 48.22540, -122.4615...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>45.13</td>
      <td>34.53</td>
      <td>2</td>
      <td>2</td>
      <td>Montana</td>
      <td>30</td>
      <td>Mtn</td>
      <td>MT</td>
      <td>POLYGON ((-111.47463 44.70224, -111.48001 44.6...</td>
    </tr>
    <tr>
      <th>2</th>
      <td>9.57</td>
      <td>18.90</td>
      <td>3</td>
      <td>3</td>
      <td>Maine</td>
      <td>23</td>
      <td>N Eng</td>
      <td>ME</td>
      <td>MULTIPOLYGON (((-69.77779 44.07407, -69.86044 ...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>21.87</td>
      <td>21.35</td>
      <td>4</td>
      <td>4</td>
      <td>North Dakota</td>
      <td>38</td>
      <td>W N Cen</td>
      <td>ND</td>
      <td>POLYGON ((-98.73006 45.93830, -99.00645 45.939...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>22.60</td>
      <td>22.75</td>
      <td>5</td>
      <td>5</td>
      <td>South Dakota</td>
      <td>46</td>
      <td>W N Cen</td>
      <td>SD</td>
      <td>POLYGON ((-102.78793 42.99532, -103.00541 42.9...</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>43</th>
      <td>7.79</td>
      <td>16.13</td>
      <td>45</td>
      <td>45</td>
      <td>South Carolina</td>
      <td>45</td>
      <td>S Atl</td>
      <td>SC</td>
      <td>MULTIPOLYGON (((-81.75976 33.19523, -81.77004 ...</td>
    </tr>
    <tr>
      <th>44</th>
      <td>13.52</td>
      <td>20.88</td>
      <td>46</td>
      <td>46</td>
      <td>Arkansas</td>
      <td>05</td>
      <td>W S Cen</td>
      <td>AR</td>
      <td>POLYGON ((-94.46148 34.19666, -94.45241 34.508...</td>
    </tr>
    <tr>
      <th>45</th>
      <td>11.22</td>
      <td>32.57</td>
      <td>47</td>
      <td>47</td>
      <td>Louisiana</td>
      <td>22</td>
      <td>W S Cen</td>
      <td>LA</td>
      <td>MULTIPOLYGON (((-93.70736 30.23937, -93.69921 ...</td>
    </tr>
    <tr>
      <th>46</th>
      <td>13.35</td>
      <td>41.09</td>
      <td>48</td>
      <td>48</td>
      <td>Florida</td>
      <td>12</td>
      <td>S Atl</td>
      <td>FL</td>
      <td>MULTIPOLYGON (((-80.78589 28.78493, -80.76264 ...</td>
    </tr>
    <tr>
      <th>47</th>
      <td>16.93</td>
      <td>40.82</td>
      <td>51</td>
      <td>51</td>
      <td>Michigan</td>
      <td>26</td>
      <td>E N Cen</td>
      <td>MI</td>
      <td>MULTIPOLYGON (((-88.49746 48.17392, -88.62525 ...</td>
    </tr>
  </tbody>
</table>
<p>48 rows × 9 columns</p>
</div>




```python
#Merge count_df and geo_table
count_df = count_df.rename(columns={'State': 'STATE_NAME'})
count_df = count_df.merge(geo_table,on='STATE_NAME')

```


```python
# Load population into a dataframe 
df_population = pd.read_csv('population.csv')
df_population

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>SUMLEV</th>
      <th>REGION</th>
      <th>DIVISION</th>
      <th>STATE</th>
      <th>NAME</th>
      <th>CENSUS2010POP</th>
      <th>ESTIMATESBASE2010</th>
      <th>POPESTIMATE2010</th>
      <th>POPESTIMATE2011</th>
      <th>POPESTIMATE2012</th>
      <th>...</th>
      <th>RDOMESTICMIG2017</th>
      <th>RDOMESTICMIG2018</th>
      <th>RNETMIG2011</th>
      <th>RNETMIG2012</th>
      <th>RNETMIG2013</th>
      <th>RNETMIG2014</th>
      <th>RNETMIG2015</th>
      <th>RNETMIG2016</th>
      <th>RNETMIG2017</th>
      <th>RNETMIG2018</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>10</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>United States</td>
      <td>308745538</td>
      <td>308758105</td>
      <td>309326085</td>
      <td>311580009</td>
      <td>313874218</td>
      <td>...</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>2.55</td>
      <td>2.75</td>
      <td>2.70</td>
      <td>2.99</td>
      <td>3.33</td>
      <td>3.32</td>
      <td>2.94</td>
      <td>3.00</td>
    </tr>
    <tr>
      <th>1</th>
      <td>20</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>Northeast Region</td>
      <td>55317240</td>
      <td>55318430</td>
      <td>55380645</td>
      <td>55600532</td>
      <td>55776729</td>
      <td>...</td>
      <td>-5.65</td>
      <td>-5.22</td>
      <td>0.85</td>
      <td>0.04</td>
      <td>-0.40</td>
      <td>-0.92</td>
      <td>-2.01</td>
      <td>-2.43</td>
      <td>-1.80</td>
      <td>-1.13</td>
    </tr>
    <tr>
      <th>2</th>
      <td>20</td>
      <td>2</td>
      <td>0</td>
      <td>0</td>
      <td>Midwest Region</td>
      <td>66927001</td>
      <td>66929743</td>
      <td>66974749</td>
      <td>67152631</td>
      <td>67336937</td>
      <td>...</td>
      <td>-2.37</td>
      <td>-2.30</td>
      <td>-1.04</td>
      <td>-0.90</td>
      <td>0.04</td>
      <td>-0.72</td>
      <td>-1.36</td>
      <td>-1.23</td>
      <td>-0.52</td>
      <td>-0.43</td>
    </tr>
    <tr>
      <th>3</th>
      <td>20</td>
      <td>3</td>
      <td>0</td>
      <td>0</td>
      <td>South Region</td>
      <td>114555744</td>
      <td>114563045</td>
      <td>114867066</td>
      <td>116039399</td>
      <td>117271075</td>
      <td>...</td>
      <td>2.96</td>
      <td>2.78</td>
      <td>5.38</td>
      <td>5.84</td>
      <td>5.29</td>
      <td>6.21</td>
      <td>7.33</td>
      <td>7.23</td>
      <td>6.25</td>
      <td>6.15</td>
    </tr>
    <tr>
      <th>4</th>
      <td>20</td>
      <td>4</td>
      <td>0</td>
      <td>0</td>
      <td>West Region</td>
      <td>71945553</td>
      <td>71946887</td>
      <td>72103625</td>
      <td>72787447</td>
      <td>73489477</td>
      <td>...</td>
      <td>1.48</td>
      <td>1.35</td>
      <td>2.69</td>
      <td>3.23</td>
      <td>3.34</td>
      <td>4.15</td>
      <td>5.13</td>
      <td>5.37</td>
      <td>4.16</td>
      <td>3.97</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>52</th>
      <td>40</td>
      <td>4</td>
      <td>9</td>
      <td>53</td>
      <td>Washington</td>
      <td>6724540</td>
      <td>6724540</td>
      <td>6742902</td>
      <td>6821655</td>
      <td>6892876</td>
      <td>...</td>
      <td>8.79</td>
      <td>6.22</td>
      <td>6.18</td>
      <td>4.99</td>
      <td>4.92</td>
      <td>7.65</td>
      <td>10.70</td>
      <td>13.26</td>
      <td>13.03</td>
      <td>10.31</td>
    </tr>
    <tr>
      <th>53</th>
      <td>40</td>
      <td>3</td>
      <td>5</td>
      <td>54</td>
      <td>West Virginia</td>
      <td>1852994</td>
      <td>1853001</td>
      <td>1854214</td>
      <td>1856074</td>
      <td>1856764</td>
      <td>...</td>
      <td>-5.54</td>
      <td>-3.88</td>
      <td>1.82</td>
      <td>0.87</td>
      <td>-0.80</td>
      <td>-1.76</td>
      <td>-2.56</td>
      <td>-4.36</td>
      <td>-5.36</td>
      <td>-3.67</td>
    </tr>
    <tr>
      <th>54</th>
      <td>40</td>
      <td>2</td>
      <td>3</td>
      <td>55</td>
      <td>Wisconsin</td>
      <td>5686986</td>
      <td>5687282</td>
      <td>5690479</td>
      <td>5704755</td>
      <td>5719855</td>
      <td>...</td>
      <td>-0.57</td>
      <td>-0.17</td>
      <td>-0.84</td>
      <td>-0.77</td>
      <td>0.11</td>
      <td>-0.39</td>
      <td>-1.06</td>
      <td>-0.65</td>
      <td>0.72</td>
      <td>1.21</td>
    </tr>
    <tr>
      <th>55</th>
      <td>40</td>
      <td>4</td>
      <td>8</td>
      <td>56</td>
      <td>Wyoming</td>
      <td>563626</td>
      <td>563773</td>
      <td>564483</td>
      <td>567224</td>
      <td>576270</td>
      <td>...</td>
      <td>-14.69</td>
      <td>-6.37</td>
      <td>-0.50</td>
      <td>10.16</td>
      <td>4.95</td>
      <td>-4.76</td>
      <td>0.29</td>
      <td>-7.15</td>
      <td>-13.62</td>
      <td>-5.34</td>
    </tr>
    <tr>
      <th>56</th>
      <td>40</td>
      <td>X</td>
      <td>X</td>
      <td>72</td>
      <td>Puerto Rico</td>
      <td>3725789</td>
      <td>3726157</td>
      <td>3721525</td>
      <td>3678732</td>
      <td>3634488</td>
      <td>...</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>-14.53</td>
      <td>-14.98</td>
      <td>-13.80</td>
      <td>-18.26</td>
      <td>-18.48</td>
      <td>-19.85</td>
      <td>-23.23</td>
      <td>-37.85</td>
    </tr>
  </tbody>
</table>
<p>57 rows × 136 columns</p>
</div>




```python
# Keep the populations from 2015-2018
df_population = df_population[['NAME','POPESTIMATE2015', 'POPESTIMATE2016','POPESTIMATE2017','POPESTIMATE2018']]
df_population

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>NAME</th>
      <th>POPESTIMATE2015</th>
      <th>POPESTIMATE2016</th>
      <th>POPESTIMATE2017</th>
      <th>POPESTIMATE2018</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>United States</td>
      <td>320742673</td>
      <td>323071342</td>
      <td>325147121</td>
      <td>327167434</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Northeast Region</td>
      <td>56047587</td>
      <td>56058789</td>
      <td>56072676</td>
      <td>56111079</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Midwest Region</td>
      <td>67869139</td>
      <td>67996917</td>
      <td>68156035</td>
      <td>68308744</td>
    </tr>
    <tr>
      <th>3</th>
      <td>South Region</td>
      <td>121037542</td>
      <td>122401186</td>
      <td>123598424</td>
      <td>124753948</td>
    </tr>
    <tr>
      <th>4</th>
      <td>West Region</td>
      <td>75788405</td>
      <td>76614450</td>
      <td>77319986</td>
      <td>77993663</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>52</th>
      <td>Washington</td>
      <td>7163543</td>
      <td>7294680</td>
      <td>7425432</td>
      <td>7535591</td>
    </tr>
    <tr>
      <th>53</th>
      <td>West Virginia</td>
      <td>1841996</td>
      <td>1830929</td>
      <td>1817048</td>
      <td>1805832</td>
    </tr>
    <tr>
      <th>54</th>
      <td>Wisconsin</td>
      <td>5761406</td>
      <td>5772958</td>
      <td>5792051</td>
      <td>5813568</td>
    </tr>
    <tr>
      <th>55</th>
      <td>Wyoming</td>
      <td>585668</td>
      <td>584290</td>
      <td>578934</td>
      <td>577737</td>
    </tr>
    <tr>
      <th>56</th>
      <td>Puerto Rico</td>
      <td>3473166</td>
      <td>3406495</td>
      <td>3325001</td>
      <td>3195153</td>
    </tr>
  </tbody>
</table>
<p>57 rows × 5 columns</p>
</div>




```python
# Calculate the mean population from 2015-2018
df_population['MEAN_POPULATION'] = df_population.mean(axis=1)
df_population = df_population[['NAME', 'MEAN_POPULATION']]
df_population
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>NAME</th>
      <th>MEAN_POPULATION</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>United States</td>
      <td>3.24e+08</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Northeast Region</td>
      <td>5.61e+07</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Midwest Region</td>
      <td>6.81e+07</td>
    </tr>
    <tr>
      <th>3</th>
      <td>South Region</td>
      <td>1.23e+08</td>
    </tr>
    <tr>
      <th>4</th>
      <td>West Region</td>
      <td>7.69e+07</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>52</th>
      <td>Washington</td>
      <td>7.35e+06</td>
    </tr>
    <tr>
      <th>53</th>
      <td>West Virginia</td>
      <td>1.82e+06</td>
    </tr>
    <tr>
      <th>54</th>
      <td>Wisconsin</td>
      <td>5.78e+06</td>
    </tr>
    <tr>
      <th>55</th>
      <td>Wyoming</td>
      <td>5.82e+05</td>
    </tr>
    <tr>
      <th>56</th>
      <td>Puerto Rico</td>
      <td>3.35e+06</td>
    </tr>
  </tbody>
</table>
<p>57 rows × 2 columns</p>
</div>




```python
# Merge population dataframe with the geo table
population = df_population.rename(columns={'NAME': 'STATE_NAME'})
population = population.merge(geo_table, on='STATE_NAME')
```


```python
population
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>STATE_NAME</th>
      <th>MEAN_POPULATION</th>
      <th>AREA</th>
      <th>PERIMETER</th>
      <th>STATE_</th>
      <th>STATE_ID</th>
      <th>STATE_FIPS</th>
      <th>SUB_REGION</th>
      <th>STATE_ABBR</th>
      <th>geometry</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Alabama</td>
      <td>4.87e+06</td>
      <td>12.90</td>
      <td>17.24</td>
      <td>42</td>
      <td>42</td>
      <td>01</td>
      <td>E S Cen</td>
      <td>AL</td>
      <td>POLYGON ((-85.07014 31.98055, -85.11522 31.907...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Arizona</td>
      <td>7.00e+06</td>
      <td>28.86</td>
      <td>23.26</td>
      <td>36</td>
      <td>36</td>
      <td>04</td>
      <td>Mtn</td>
      <td>AZ</td>
      <td>POLYGON ((-114.51984 33.02767, -114.55830 33.0...</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Arkansas</td>
      <td>3.00e+06</td>
      <td>13.52</td>
      <td>20.88</td>
      <td>46</td>
      <td>46</td>
      <td>05</td>
      <td>W S Cen</td>
      <td>AR</td>
      <td>POLYGON ((-94.46148 34.19666, -94.45241 34.508...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>California</td>
      <td>3.93e+07</td>
      <td>41.53</td>
      <td>42.26</td>
      <td>24</td>
      <td>24</td>
      <td>06</td>
      <td>Pacific</td>
      <td>CA</td>
      <td>MULTIPOLYGON (((-121.66415 38.16937, -121.7813...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Colorado</td>
      <td>5.58e+06</td>
      <td>28.04</td>
      <td>22.02</td>
      <td>31</td>
      <td>31</td>
      <td>08</td>
      <td>Mtn</td>
      <td>CO</td>
      <td>POLYGON ((-102.04400 37.64146, -102.04156 37.3...</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>43</th>
      <td>Virginia</td>
      <td>8.44e+06</td>
      <td>10.51</td>
      <td>31.20</td>
      <td>34</td>
      <td>34</td>
      <td>51</td>
      <td>S Atl</td>
      <td>VA</td>
      <td>MULTIPOLYGON (((-79.14433 36.54606, -79.21706 ...</td>
    </tr>
    <tr>
      <th>44</th>
      <td>Washington</td>
      <td>7.35e+06</td>
      <td>20.75</td>
      <td>34.96</td>
      <td>1</td>
      <td>1</td>
      <td>53</td>
      <td>Pacific</td>
      <td>WA</td>
      <td>MULTIPOLYGON (((-122.40075 48.22540, -122.4615...</td>
    </tr>
    <tr>
      <th>45</th>
      <td>West Virginia</td>
      <td>1.82e+06</td>
      <td>6.49</td>
      <td>18.20</td>
      <td>29</td>
      <td>29</td>
      <td>54</td>
      <td>S Atl</td>
      <td>WV</td>
      <td>POLYGON ((-79.23190 38.48037, -79.27260 38.437...</td>
    </tr>
    <tr>
      <th>46</th>
      <td>Wisconsin</td>
      <td>5.78e+06</td>
      <td>16.48</td>
      <td>21.89</td>
      <td>7</td>
      <td>7</td>
      <td>55</td>
      <td>E N Cen</td>
      <td>WI</td>
      <td>MULTIPOLYGON (((-87.74845 44.96163, -87.83989 ...</td>
    </tr>
    <tr>
      <th>47</th>
      <td>Wyoming</td>
      <td>5.82e+05</td>
      <td>27.97</td>
      <td>21.99</td>
      <td>6</td>
      <td>6</td>
      <td>56</td>
      <td>Mtn</td>
      <td>WY</td>
      <td>POLYGON ((-104.05311 41.69825, -104.05499 41.5...</td>
    </tr>
  </tbody>
</table>
<p>48 rows × 10 columns</p>
</div>




```python
# Load the cities' coordinates into a dataframe
dfcoord = pd.read_csv('uscities.csv')
dfcoord = dfcoord[['city','lat', 'lng']]
dfcoord = dfcoord.drop_duplicates(subset='city', keep="first")
dfcoord

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>city</th>
      <th>lat</th>
      <th>lng</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>South Creek</td>
      <td>47.00</td>
      <td>-122.39</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Roslyn</td>
      <td>47.25</td>
      <td>-121.10</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Sprague</td>
      <td>47.30</td>
      <td>-117.97</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Gig Harbor</td>
      <td>47.34</td>
      <td>-122.60</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Lake Cassidy</td>
      <td>48.06</td>
      <td>-122.09</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>28878</th>
      <td>Lake Norden</td>
      <td>44.58</td>
      <td>-97.21</td>
    </tr>
    <tr>
      <th>28880</th>
      <td>Colome</td>
      <td>43.26</td>
      <td>-99.72</td>
    </tr>
    <tr>
      <th>28881</th>
      <td>Okreek</td>
      <td>43.35</td>
      <td>-100.38</td>
    </tr>
    <tr>
      <th>28883</th>
      <td>Willow Lake</td>
      <td>44.63</td>
      <td>-97.64</td>
    </tr>
    <tr>
      <th>28885</th>
      <td>Spearfish</td>
      <td>44.49</td>
      <td>-103.82</td>
    </tr>
  </tbody>
</table>
<p>19387 rows × 3 columns</p>
</div>




```python
# Merge df with the cities' coordinates 
temp = df.rename(columns={'City Or County': 'city'})
temp = temp.merge(dfcoord, on='city')
```


```python
# Remove outlier
temp = temp[temp.lng > -125]
```


```python
# Add a geometry column, a requirement for geospatial graph 
geometry = pd.Series()
for i in temp.index:
    geometry.loc[i] = Point((temp.loc[i,'lng'],temp.loc[i,'lat']))
temp['geometry'] = geometry
temp
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Incident Date</th>
      <th>State</th>
      <th>city</th>
      <th># Killed</th>
      <th># Injured</th>
      <th>lat</th>
      <th>lng</th>
      <th>geometry</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>January 1, 2015</td>
      <td>Tennessee</td>
      <td>Memphis</td>
      <td>0</td>
      <td>5</td>
      <td>27.54</td>
      <td>-82.56</td>
      <td>POINT (-82.5607 27.5435)</td>
    </tr>
    <tr>
      <th>1</th>
      <td>August 30, 2015</td>
      <td>Tennessee</td>
      <td>Memphis</td>
      <td>1</td>
      <td>4</td>
      <td>27.54</td>
      <td>-82.56</td>
      <td>POINT (-82.5607 27.5435)</td>
    </tr>
    <tr>
      <th>2</th>
      <td>October 10, 2015</td>
      <td>Tennessee</td>
      <td>Memphis</td>
      <td>0</td>
      <td>6</td>
      <td>27.54</td>
      <td>-82.56</td>
      <td>POINT (-82.5607 27.5435)</td>
    </tr>
    <tr>
      <th>3</th>
      <td>January 7, 2016</td>
      <td>Tennessee</td>
      <td>Memphis</td>
      <td>1</td>
      <td>3</td>
      <td>27.54</td>
      <td>-82.56</td>
      <td>POINT (-82.5607 27.5435)</td>
    </tr>
    <tr>
      <th>4</th>
      <td>April 9, 2016</td>
      <td>Tennessee</td>
      <td>Memphis</td>
      <td>0</td>
      <td>4</td>
      <td>27.54</td>
      <td>-82.56</td>
      <td>POINT (-82.5607 27.5435)</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1276</th>
      <td>November 13, 2018</td>
      <td>New Mexico</td>
      <td>Gallup</td>
      <td>4</td>
      <td>1</td>
      <td>35.52</td>
      <td>-108.74</td>
      <td>POINT (-108.7423 35.5183)</td>
    </tr>
    <tr>
      <th>1277</th>
      <td>November 25, 2018</td>
      <td>Alabama</td>
      <td>Demopolis</td>
      <td>2</td>
      <td>2</td>
      <td>32.50</td>
      <td>-87.83</td>
      <td>POINT (-87.82980000000001 32.498)</td>
    </tr>
    <tr>
      <th>1278</th>
      <td>November 26, 2018</td>
      <td>Tennessee</td>
      <td>Powell</td>
      <td>0</td>
      <td>4</td>
      <td>44.80</td>
      <td>-108.77</td>
      <td>POINT (-108.7682 44.7963)</td>
    </tr>
    <tr>
      <th>1279</th>
      <td>December 11, 2018</td>
      <td>Louisiana</td>
      <td>Natchitoches</td>
      <td>1</td>
      <td>3</td>
      <td>31.73</td>
      <td>-93.10</td>
      <td>POINT (-93.0979 31.7317)</td>
    </tr>
    <tr>
      <th>1280</th>
      <td>December 24, 2018</td>
      <td>Louisiana</td>
      <td>Lutcher</td>
      <td>2</td>
      <td>2</td>
      <td>30.06</td>
      <td>-90.71</td>
      <td>POINT (-90.7124 30.0646)</td>
    </tr>
  </tbody>
</table>
<p>1280 rows × 8 columns</p>
</div>




```python
#Add a count of shootings col for each city
temp['city_count'] = temp.groupby(['city'])['city'].transform('count')
```


```python
fig, ax = plt.subplots(nrows=1, ncols=1,figsize = (20,12)) # figsize to be changed
gpd_population = gpd.GeoDataFrame(population)
# tempgpd = gpd.GeoDataFrame(temp)
base = gpd_population.plot(ax=ax, column= 'MEAN_POPULATION', cmap='GnBu', legend=True,
                          legend_kwds={'label': "Population by State"})
leg = ax.get_legend()
plt.scatter(y=temp["lat"], x = temp["lng"], alpha = 0.5, marker='o', color='red', s=6*np.sqrt(temp['city_count'])) #adjust size of dot by city count
plt.axis('off')
plt.title('Mass shootings distribution from 2015-2018 under population density')
plt.show()
```


![png](FinalProject_files/FinalProject_57_0.png)



```python
t_value, p_value = stats.ttest_ind(temp['lat'], temp['# Injured'])
t_value
```




    84.55069463187749



## Mass shootings distribution from 2015-2018 under population density

### Interpretation

This geospatial plot shows the mass shootings distribution in the U.S from 2015-2018 under population density. A single red dot represents a city that has a mass shooting in the above period, with the size scaled up if there are multiple shootings. The shades of blue and green represent each state' population: states with bluer color has more population. <br>
The dots are not uniformly distributed. There are states with a lot of mass shootings such as California and Florida, and others with no shootings such as Nevada and Utah.

### Data Analysis

So in the geospatial plot above we could have a sense that there actually is a correlation between population and number of mass shootings. We could see that states with more population has a high rate of mass shootings. It makes sense because with more people there will be more chances for everything including gun violence. That is why usually for stating mass shootings in each states they do it per 100k or per million people. So a state like Alaska with more lenient gun policy has 180 death rate by guns and a state like california has 3184 gun violence but since the population of california is 39,747,267 and the population of Alaska is 735,720, Death Rate (per 100k people) for Alaska is 24.50% and for Clifornia is 7.90%. http://worldpopulationreview.com/states/gun-violence-by-state/




### 3.3 Gun Policy



```python
# Read data of gun law by state into a dataframe
df_gunpolicy = pd.read_csv('gunlawstrength.csv')
df_gunpolicy
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>GUN LAW STRENGTH (RANKED)</th>
      <th>STATE</th>
      <th>2018 GRADE</th>
      <th>GUN DEATH RATE (RANKED)</th>
      <th>GUN DEATH RATE (PER 100K)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>California</td>
      <td>A</td>
      <td>44</td>
      <td>7.8</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>New Jersey</td>
      <td>A</td>
      <td>45</td>
      <td>5.3</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Connecticut</td>
      <td>A-</td>
      <td>46</td>
      <td>5.1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Maryland</td>
      <td>A-</td>
      <td>29</td>
      <td>12.3</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>Massachusetts</td>
      <td>A-</td>
      <td>49</td>
      <td>3.7</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>45</th>
      <td>46</td>
      <td>Arizona</td>
      <td>F</td>
      <td>18</td>
      <td>15.7</td>
    </tr>
    <tr>
      <th>46</th>
      <td>47</td>
      <td>Missouri</td>
      <td>F</td>
      <td>6</td>
      <td>21.3</td>
    </tr>
    <tr>
      <th>47</th>
      <td>48</td>
      <td>Idaho</td>
      <td>F</td>
      <td>15</td>
      <td>16.4</td>
    </tr>
    <tr>
      <th>48</th>
      <td>48</td>
      <td>Wyoming</td>
      <td>F</td>
      <td>8</td>
      <td>18.7</td>
    </tr>
    <tr>
      <th>49</th>
      <td>50</td>
      <td>Mississippi</td>
      <td>F</td>
      <td>5</td>
      <td>21.5</td>
    </tr>
  </tbody>
</table>
<p>50 rows × 5 columns</p>
</div>




```python
# Merge df_gunpolicy with geo_table, required for geospatial plot
df_gunpolicy = df_gunpolicy.rename(columns={'STATE': 'STATE_NAME'})
df_gunpolicy = df_gunpolicy.merge(geo_table, on='STATE_NAME')

```


```python
#Add a coordinate column in order to add labels to the states
df_gunpolicy['coords'] = df_gunpolicy['geometry'].apply(lambda x: x.representative_point().coords[:])
df_gunpolicy['coords'] = [coords[0] for coords in df_gunpolicy['coords']]
df_gunpolicy
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>GUN LAW STRENGTH (RANKED)</th>
      <th>STATE_NAME</th>
      <th>2018 GRADE</th>
      <th>GUN DEATH RATE (RANKED)</th>
      <th>GUN DEATH RATE (PER 100K)</th>
      <th>AREA</th>
      <th>PERIMETER</th>
      <th>STATE_</th>
      <th>STATE_ID</th>
      <th>STATE_FIPS</th>
      <th>SUB_REGION</th>
      <th>STATE_ABBR</th>
      <th>geometry</th>
      <th>coords</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>California</td>
      <td>A</td>
      <td>44</td>
      <td>7.8</td>
      <td>41.53</td>
      <td>42.26</td>
      <td>24</td>
      <td>24</td>
      <td>06</td>
      <td>Pacific</td>
      <td>CA</td>
      <td>MULTIPOLYGON (((-121.66415 38.16937, -121.7813...</td>
      <td>(-120.00924331104378, 37.29582595825195)</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>New Jersey</td>
      <td>A</td>
      <td>45</td>
      <td>5.3</td>
      <td>2.06</td>
      <td>8.42</td>
      <td>20</td>
      <td>20</td>
      <td>34</td>
      <td>Mid Atl</td>
      <td>NJ</td>
      <td>POLYGON ((-75.48964 39.71474, -75.47633 39.719...</td>
      <td>(-74.37764544111192, 40.16340637207031)</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Connecticut</td>
      <td>A-</td>
      <td>46</td>
      <td>5.1</td>
      <td>1.39</td>
      <td>5.72</td>
      <td>18</td>
      <td>18</td>
      <td>09</td>
      <td>N Eng</td>
      <td>CT</td>
      <td>POLYGON ((-73.53082 41.52265, -73.51758 41.665...</td>
      <td>(-72.66026049545243, 41.56192970275879)</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Maryland</td>
      <td>A-</td>
      <td>29</td>
      <td>12.3</td>
      <td>2.62</td>
      <td>21.88</td>
      <td>30</td>
      <td>30</td>
      <td>24</td>
      <td>S Atl</td>
      <td>MD</td>
      <td>MULTIPOLYGON (((-75.71106 38.64955, -75.70742 ...</td>
      <td>(-76.72408804171778, 38.85972785949707)</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>Massachusetts</td>
      <td>A-</td>
      <td>49</td>
      <td>3.7</td>
      <td>2.31</td>
      <td>13.11</td>
      <td>14</td>
      <td>14</td>
      <td>25</td>
      <td>N Eng</td>
      <td>MA</td>
      <td>MULTIPOLYGON (((-71.31983 41.77209, -71.34030 ...</td>
      <td>(-72.09162515290728, 42.19374084472656)</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>43</th>
      <td>46</td>
      <td>Arizona</td>
      <td>F</td>
      <td>18</td>
      <td>15.7</td>
      <td>28.86</td>
      <td>23.26</td>
      <td>36</td>
      <td>36</td>
      <td>04</td>
      <td>Mtn</td>
      <td>AZ</td>
      <td>POLYGON ((-114.51984 33.02767, -114.55830 33.0...</td>
      <td>(-111.67611563511193, 34.15624809265137)</td>
    </tr>
    <tr>
      <th>44</th>
      <td>47</td>
      <td>Missouri</td>
      <td>F</td>
      <td>6</td>
      <td>21.3</td>
      <td>18.65</td>
      <td>23.60</td>
      <td>35</td>
      <td>35</td>
      <td>29</td>
      <td>W N Cen</td>
      <td>MO</td>
      <td>POLYGON ((-89.10497 36.95387, -89.12959 36.866...</td>
      <td>(-92.49264906395838, 38.27892875671387)</td>
    </tr>
    <tr>
      <th>45</th>
      <td>48</td>
      <td>Idaho</td>
      <td>F</td>
      <td>15</td>
      <td>16.4</td>
      <td>24.39</td>
      <td>28.53</td>
      <td>8</td>
      <td>8</td>
      <td>16</td>
      <td>Mtn</td>
      <td>ID</td>
      <td>POLYGON ((-117.02531 43.67915, -117.02280 43.7...</td>
      <td>(-115.47965192564584, 45.49642753601074)</td>
    </tr>
    <tr>
      <th>46</th>
      <td>48</td>
      <td>Wyoming</td>
      <td>F</td>
      <td>8</td>
      <td>18.7</td>
      <td>27.97</td>
      <td>21.99</td>
      <td>6</td>
      <td>6</td>
      <td>56</td>
      <td>Mtn</td>
      <td>WY</td>
      <td>POLYGON ((-104.05311 41.69825, -104.05499 41.5...</td>
      <td>(-107.55158804185346, 42.80889892578125)</td>
    </tr>
    <tr>
      <th>47</th>
      <td>50</td>
      <td>Mississippi</td>
      <td>F</td>
      <td>5</td>
      <td>21.5</td>
      <td>11.87</td>
      <td>22.06</td>
      <td>43</td>
      <td>43</td>
      <td>28</td>
      <td>E S Cen</td>
      <td>MS</td>
      <td>POLYGON ((-88.45078 31.43545, -88.43455 31.120...</td>
      <td>(-89.70172485313775, 32.60195732116699)</td>
    </tr>
  </tbody>
</table>
<p>48 rows × 14 columns</p>
</div>




```python
fig, ax = plt.subplots(nrows=1, ncols=1,figsize = (25,12))
gpd_gunpolicy = gpd.GeoDataFrame(df_gunpolicy)
base = gpd_gunpolicy.plot(ax=ax, column= 'GUN DEATH RATE (PER 100K)', cmap='OrRd', legend=True, legend_kwds={'label': "Gun Death Rate (per 100k)"})
for idx, row in gpd_gunpolicy.iterrows():
    plt.annotate(s=row['2018 GRADE'],xy=row['coords'],
                 horizontalalignment='center')
# Optional: Scatter to show the mass shootings
# plt.scatter(y=temp["lat"], x = temp["lng"], alpha = 0.5, marker='o', color='red', s=10*np.sqrt(temp['city_count']))
plt.axis('off')
plt.title('2018 State Gun Law Score ')
plt.show()

```


![png](FinalProject_files/FinalProject_65_0.png)





## 2018 State Gun Law Score

### Interpretation

This geospatial plot shows a map of the US with each states' gun law score (from A to F with A being the most strict and F being more lenient. The shades of red show the amount of gun deaths in each state.

Note: Not uniformly distributed 

### Data Analysis

This plot allows us to compare the strictness of gun laws to the amount of gun deaths. From this graph, states with lenient rateings (D, F) tended to have more gun deaths that year. Additionally, states with strict gun control laws (A, B) had lower amounts of deaths from guns.

The plot above shows a strong correlation between gun control laws and gun deaths. This graph however does not show that mass shootings are related to gun control laws. This is due to the fact that 'gun deaths' includes other occurrences such as suicide, violent crime, self-defense, and accidental deaths.




## USA map for reference


```python
fig, ax = plt.subplots(nrows=1, ncols=1,figsize = (25,12))
gpd_gunpolicy = gpd.GeoDataFrame(df_gunpolicy)
base = gpd_gunpolicy.plot(ax=ax, column= 'GUN DEATH RATE (PER 100K)', cmap='rainbow')
for idx, row in gpd_gunpolicy.iterrows():
    plt.annotate(s=row['STATE_ABBR'],xy=row['coords'],
                 horizontalalignment='center')
plt.axis('off')
plt.title('USA MAP FOR REFERENCE')
plt.show()

```


![png](FinalProject_files/FinalProject_70_0.png)




### 3.3 Gun Law vs Mass Shootings



```python
#Merge mass shootings df and gun law df
df_scatter = count_df.merge(df_gunpolicy,on='STATE_NAME')
df_scatter
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>STATE_NAME</th>
      <th>Shootings</th>
      <th>AREA_x</th>
      <th>PERIMETER_x</th>
      <th>STATE__x</th>
      <th>STATE_ID_x</th>
      <th>STATE_FIPS_x</th>
      <th>SUB_REGION_x</th>
      <th>STATE_ABBR_x</th>
      <th>geometry_x</th>
      <th>...</th>
      <th>GUN DEATH RATE (PER 100K)</th>
      <th>AREA_y</th>
      <th>PERIMETER_y</th>
      <th>STATE__y</th>
      <th>STATE_ID_y</th>
      <th>STATE_FIPS_y</th>
      <th>SUB_REGION_y</th>
      <th>STATE_ABBR_y</th>
      <th>geometry_y</th>
      <th>coords</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Tennessee</td>
      <td>55</td>
      <td>10.88</td>
      <td>21.46</td>
      <td>39</td>
      <td>39</td>
      <td>47</td>
      <td>E S Cen</td>
      <td>TN</td>
      <td>POLYGON ((-83.95470 35.45546, -84.01265 35.407...</td>
      <td>...</td>
      <td>18.4</td>
      <td>10.88</td>
      <td>21.46</td>
      <td>39</td>
      <td>39</td>
      <td>47</td>
      <td>E S Cen</td>
      <td>TN</td>
      <td>POLYGON ((-83.95470 35.45546, -84.01265 35.407...</td>
      <td>(-86.31700629724438, 35.83477592468262)</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Georgia</td>
      <td>54</td>
      <td>14.60</td>
      <td>20.10</td>
      <td>44</td>
      <td>44</td>
      <td>13</td>
      <td>S Atl</td>
      <td>GA</td>
      <td>MULTIPOLYGON (((-85.13023 31.77869, -85.13163 ...</td>
      <td>...</td>
      <td>15.4</td>
      <td>14.60</td>
      <td>20.10</td>
      <td>44</td>
      <td>44</td>
      <td>13</td>
      <td>S Atl</td>
      <td>GA</td>
      <td>MULTIPOLYGON (((-85.13023 31.77869, -85.13163 ...</td>
      <td>(-83.25166803132484, 32.6812744140625)</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Texas</td>
      <td>88</td>
      <td>65.06</td>
      <td>64.81</td>
      <td>40</td>
      <td>40</td>
      <td>48</td>
      <td>W S Cen</td>
      <td>TX</td>
      <td>MULTIPOLYGON (((-105.99836 31.39382, -106.2127...</td>
      <td>...</td>
      <td>12.4</td>
      <td>65.06</td>
      <td>64.81</td>
      <td>40</td>
      <td>40</td>
      <td>48</td>
      <td>W S Cen</td>
      <td>TX</td>
      <td>MULTIPOLYGON (((-105.99836 31.39382, -106.2127...</td>
      <td>(-99.64643196200913, 31.166861534118652)</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Virginia</td>
      <td>32</td>
      <td>10.51</td>
      <td>31.20</td>
      <td>34</td>
      <td>34</td>
      <td>51</td>
      <td>S Atl</td>
      <td>VA</td>
      <td>MULTIPOLYGON (((-79.14433 36.54606, -79.21706 ...</td>
      <td>...</td>
      <td>11.9</td>
      <td>10.51</td>
      <td>31.20</td>
      <td>34</td>
      <td>34</td>
      <td>51</td>
      <td>S Atl</td>
      <td>VA</td>
      <td>MULTIPOLYGON (((-79.14433 36.54606, -79.21706 ...</td>
      <td>(-78.23740390508686, 37.99645805358887)</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Florida</td>
      <td>109</td>
      <td>13.35</td>
      <td>41.09</td>
      <td>48</td>
      <td>48</td>
      <td>12</td>
      <td>S Atl</td>
      <td>FL</td>
      <td>MULTIPOLYGON (((-80.78589 28.78493, -80.76264 ...</td>
      <td>...</td>
      <td>12.3</td>
      <td>13.35</td>
      <td>41.09</td>
      <td>48</td>
      <td>48</td>
      <td>12</td>
      <td>S Atl</td>
      <td>FL</td>
      <td>MULTIPOLYGON (((-80.78589 28.78493, -80.76264 ...</td>
      <td>(-81.70001563029163, 28.109305381774902)</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>39</th>
      <td>South Dakota</td>
      <td>1</td>
      <td>22.60</td>
      <td>22.75</td>
      <td>5</td>
      <td>5</td>
      <td>46</td>
      <td>W N Cen</td>
      <td>SD</td>
      <td>POLYGON ((-102.78793 42.99532, -103.00541 42.9...</td>
      <td>...</td>
      <td>11.8</td>
      <td>22.60</td>
      <td>22.75</td>
      <td>5</td>
      <td>5</td>
      <td>46</td>
      <td>W N Cen</td>
      <td>SD</td>
      <td>POLYGON ((-102.78793 42.99532, -103.00541 42.9...</td>
      <td>(-100.257863681294, 44.368736267089844)</td>
    </tr>
    <tr>
      <th>40</th>
      <td>Washington</td>
      <td>15</td>
      <td>20.75</td>
      <td>34.96</td>
      <td>1</td>
      <td>1</td>
      <td>53</td>
      <td>Pacific</td>
      <td>WA</td>
      <td>MULTIPOLYGON (((-122.40075 48.22540, -122.4615...</td>
      <td>...</td>
      <td>11.1</td>
      <td>20.75</td>
      <td>34.96</td>
      <td>1</td>
      <td>1</td>
      <td>53</td>
      <td>Pacific</td>
      <td>WA</td>
      <td>MULTIPOLYGON (((-122.40075 48.22540, -122.4615...</td>
      <td>(-119.72064210624406, 47.27300834655762)</td>
    </tr>
    <tr>
      <th>41</th>
      <td>West Virginia</td>
      <td>1</td>
      <td>6.49</td>
      <td>18.20</td>
      <td>29</td>
      <td>29</td>
      <td>54</td>
      <td>S Atl</td>
      <td>WV</td>
      <td>POLYGON ((-79.23190 38.48037, -79.27260 38.437...</td>
      <td>...</td>
      <td>18.6</td>
      <td>6.49</td>
      <td>18.20</td>
      <td>29</td>
      <td>29</td>
      <td>54</td>
      <td>S Atl</td>
      <td>WV</td>
      <td>POLYGON ((-79.23190 38.48037, -79.27260 38.437...</td>
      <td>(-80.29892549880226, 38.91647720336914)</td>
    </tr>
    <tr>
      <th>42</th>
      <td>Utah</td>
      <td>2</td>
      <td>22.97</td>
      <td>19.99</td>
      <td>23</td>
      <td>23</td>
      <td>49</td>
      <td>Mtn</td>
      <td>UT</td>
      <td>POLYGON ((-114.04646 38.13769, -114.04427 38.5...</td>
      <td>...</td>
      <td>14.0</td>
      <td>22.97</td>
      <td>19.99</td>
      <td>23</td>
      <td>23</td>
      <td>49</td>
      <td>Mtn</td>
      <td>UT</td>
      <td>POLYGON ((-114.04646 38.13769, -114.04427 38.5...</td>
      <td>(-111.54578241685914, 39.439592361450195)</td>
    </tr>
    <tr>
      <th>43</th>
      <td>Maine</td>
      <td>1</td>
      <td>9.57</td>
      <td>18.90</td>
      <td>3</td>
      <td>3</td>
      <td>23</td>
      <td>N Eng</td>
      <td>ME</td>
      <td>MULTIPOLYGON (((-69.77779 44.07407, -69.86044 ...</td>
      <td>...</td>
      <td>11.6</td>
      <td>9.57</td>
      <td>18.90</td>
      <td>3</td>
      <td>3</td>
      <td>23</td>
      <td>N Eng</td>
      <td>ME</td>
      <td>MULTIPOLYGON (((-69.77779 44.07407, -69.86044 ...</td>
      <td>(-69.16328277498042, 45.25174140930176)</td>
    </tr>
  </tbody>
</table>
<p>44 rows × 23 columns</p>
</div>




```python
# df_scatter.plot.scatter(x='GUN LAW STRENGTH (RANKED)', y='Shootings')
sns.set_style('ticks')
fig, ax = plt.subplots()
fig.set_size_inches(18.5, 10.5)
sns.regplot(x="GUN LAW STRENGTH (RANKED)", y="Shootings", data=df_scatter, line_kws={"color": "red"}, truncate=True)
plt.title('State Gun Law Strength vs Mass Shootings (2015-2018)')
# Set x-axis label
plt.xlabel('Restrictive Laws <――――――――――――――――――――――――――――――――――――――> Permissive Laws')
# Set y-axis label
plt.ylabel('Number of Mass Shootings from 2015-2018') # Change to just 2018??

# Function to label the points as states
def label_point(x, y, val, ax):
    a = pd.concat({'x': x, 'y': y, 'val': val}, axis=1)
    for i, point in a.iterrows():
        ax.text(point['x']+.02, point['y'], str(point['val']))

label_point(df_scatter['GUN LAW STRENGTH (RANKED)'], df_scatter['Shootings'], df_scatter['STATE_ABBR_x'], plt.gca())

plt.show()
```


![png](FinalProject_files/FinalProject_74_0.png)


## State Gun Law Strength vs Mass Shootings (2015-2018)

### Interpretation

This regression plot shows the strictness of state gun laws with respect to the number of mass shootings from 2015-2018. <br>

The x-axis represents the strictness of state gun laws, states with stricter gun laws will be on the left, and states with more lenient gun laws will be on the right of the plot. The y-axis represent the mass shootings per million from 2015-2018.

The dots are not uniformly distributed.

Outliers: California, Illinois, Florida.

### Data Analysis

There is a negative correlation between the permissiveness of the gun laws and the number of mass shootings in 2015-2018 period. States that have stricter gun laws have more gun shootings, which is contrary to our hypothesis. We realized that we forgot to take into account the population density of a state, so we decided to explore that variable next. 



```python
t_value_0, p_value_0 = stats.ttest_ind(df_scatter['Shootings'], df_scatter['GUN LAW STRENGTH (RANKED)'])
p_value_0
```




    0.17956714722184852






```python
df_scatter2 = count_df.merge(population,on='STATE_NAME')
df_scatter2 = df_scatter2[['STATE_NAME','Shootings', 'MEAN_POPULATION']]
df_scatter2['SHOOTINGS_PER_MILLION'] = df_scatter2['Shootings'].apply(float)/(df_scatter2['MEAN_POPULATION'] / 1000000)
df_scatter2
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>STATE_NAME</th>
      <th>Shootings</th>
      <th>MEAN_POPULATION</th>
      <th>SHOOTINGS_PER_MILLION</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Tennessee</td>
      <td>55</td>
      <td>6.68e+06</td>
      <td>8.24</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Georgia</td>
      <td>54</td>
      <td>1.04e+07</td>
      <td>5.22</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Texas</td>
      <td>88</td>
      <td>2.81e+07</td>
      <td>3.13</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Virginia</td>
      <td>32</td>
      <td>8.44e+06</td>
      <td>3.79</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Florida</td>
      <td>109</td>
      <td>2.08e+07</td>
      <td>5.24</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>39</th>
      <td>South Dakota</td>
      <td>1</td>
      <td>8.68e+05</td>
      <td>1.15</td>
    </tr>
    <tr>
      <th>40</th>
      <td>Washington</td>
      <td>15</td>
      <td>7.35e+06</td>
      <td>2.04</td>
    </tr>
    <tr>
      <th>41</th>
      <td>West Virginia</td>
      <td>1</td>
      <td>1.82e+06</td>
      <td>0.55</td>
    </tr>
    <tr>
      <th>42</th>
      <td>Utah</td>
      <td>2</td>
      <td>3.07e+06</td>
      <td>0.65</td>
    </tr>
    <tr>
      <th>43</th>
      <td>Maine</td>
      <td>1</td>
      <td>1.33e+06</td>
      <td>0.75</td>
    </tr>
  </tbody>
</table>
<p>44 rows × 4 columns</p>
</div>




```python
#Merge mass shootings df and gun law df
df_scatter2 = df_scatter2.merge(df_gunpolicy,on='STATE_NAME')
# df_scatter2
```


```python
sns.set_style('ticks')
fig, ax = plt.subplots()
fig.set_size_inches(18.5, 10.5)
sns.regplot(x="GUN LAW STRENGTH (RANKED)", y="SHOOTINGS_PER_MILLION", data=df_scatter2, line_kws={"color": "red"}, truncate=True)
plt.title('State Gun Law Strength vs Mass Shootings per million people (2015-2018)')
# Set x-axis label
plt.xlabel('Restrictive Laws <――――――――――――――――――――――――――――――――――――――> Permissive Laws')
# Set y-axis label
plt.ylabel('Mass Shootings per million people (2015-2018)') # Change to just 2018??

# Function to label the points as states
def label_point(x, y, val, ax):
    a = pd.concat({'x': x, 'y': y, 'val': val}, axis=1)
    for i, point in a.iterrows():
        ax.text(point['x']+.02, point['y'], str(point['val']))

label_point(df_scatter2['GUN LAW STRENGTH (RANKED)'], df_scatter2['SHOOTINGS_PER_MILLION'], df_scatter2['STATE_ABBR'], plt.gca())

plt.show()
```


![png](FinalProject_files/FinalProject_80_0.png)


# State Gun Law Strength vs Mass Shootings per million (2015-2018)

### Interpretation

This regression plot shows the strictness of state gun laws with respect to the number of mass shootings per million people from 2015-2018. <br>

The x-axis represents the strictness of state gun laws, states with stricter gun laws will be on the left, and states with more lenient gun laws will be on the right of the plot. The y-axis represent the mass shootings per million from 2015-2018

The dots are not uniformly distributed.

Outliers: Illinois, Louisiana

### Data Analysis

In the regression plot above we could see that mass shootings are strongly correlated by a state’s access to guns. It fits the narrative, as mass public shootings are rooted in the much too readily available weapons of mass killings, usually assault weapons. The states with the highest gun death rates are often the states with relatively loose gun restrictions. Terrorist acts like those committed in El Paso and Dayton are more likely to keep happening to people who live in places where it’s easy to buy, sell, and carry guns. When they compared those scores to mass shootings per million residents, they found that for every 10-point relaxation in a state’s gun laws, the rates of mass shootings in that state increased by 11.5 percent. This trend showed up even after the models were adjusted for population demographics like household income, unemployment, poverty, education, incarceration rates, and race. The eight most restrictive states include Hawaii, Massachusetts, New Jersey, Connecticut, Maryland, California, Illinois, and New York. Leading the pack in both permissive laws and mass shooting rate were Vermont, South Carolina, Louisiana, and Arizona.Both Texas and Ohio, where the latest terror attacks were carried out, also scored high on gun law permissibility. In both states it’s legal to carry concealed weapons in public, provided the gun owner has the proper permits to own it.


## T-test for significance 
Since we have the visualization, we would like to test it for significance. 

To start we set out hypothesis:

Ho: There is no association between law strictness and mass shootings per million people 

Ha: There is no association between law strictness and mass shootings per million people

Alpha: 0.05



```python
t_value, p_value = stats.ttest_ind(df_scatter2['SHOOTINGS_PER_MILLION'], df_scatter2['GUN LAW STRENGTH (RANKED)'])
t_value
```




    -9.324964090910854




```python
p_value
```




    1.0722786803118152e-14



# 4. Ethics and Privacy:
For this project, the data analyzed was gathered from online databases. The online data itself does not have any ethical concern- as most mass shooting cases are reported widely by the media and are highly publicized. This project does not violate an individual’s right to privacy, as victims of mass shooting and perpetrators are part of public records and thus the individual’s involved do not have the right to privacy (with the exception of minors). The only ethical concern about individual’s privacy may be relevant to the project the cases involving minors, where state and federal statutes protects the individual from being publicized. However, in the given context, this project does not use any individual name, location or personal information, which effectively protects the privacy of any minors who might be protected by federal and/or state laws. Specific addresses of shooting locations were removed from the datasets in used and only regional/state information was taken into account. 








# 5. Conclusions and Discussions:

In this project, we wanted to observe the relationship between  local gun policies and the number of mass shootings that occur within each state. We refined our scope by asking, "does a state with a strict gun policy typically have fewer mass shootings?". Our group hypothesized  that the number of mass shootings in a state **is** strongly correlated with how strict its gun policy is. 

The correlation between gun law strictness and mass shootings seemed at first like it would be an obvious strong correlation, however initial data seemed to go against this. Our initial plot showed the areas where mass shootings often occur but not its correlation. Then when we looked at the correlation between gun deaths and gun law strictness, we saw that there was a relatively strong correlation. This however was for gun deaths in general, not just mass shootings. When we looked at the relationship between mass shootings and state gun law strictness, we actually found a negative correlation. Initially, this made it seem as if the opposite of what we thought was true. We however then realized that the reason for this was population which led us to do a regression plot.

In the regression plot we showed that mass shootings are correlated, albeit weakly, by a state’s access to guns. We showed in the regression plot that per million residents, Mass shootings are more likely to happen to people who live in places where it’s easy to buy, sell, and carry guns in other words in states with weaker Gun Policies. For example, Texas and Ohio, where the latest terror attacks were carried out along with many others, scored high on gun law permissibility. In both states it’s legal to carry concealed weapons in public, provided the gun owner has the proper permits to own it. It is important to note that while there is a correlation to gun law strictness, population density likely plays an even bigger role in the amount of mass shootings. This however, would take further study beyond what our hypothesis was testing.


