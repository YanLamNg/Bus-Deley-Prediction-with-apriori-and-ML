
# Bus Deley Prediction with apriori and ML

Abstract:

Public transportation is essential for the public’s daily life. For passengers, an
accurate transportation prediction, which means less bus waiting, and transit time. This
leads to maximize their time utilization. Also, it is critical for bus companies, and accuracy
prediction will help all them quick aware of the current states of the bus running. By devoting
more bus, or short the bus departure gap, the delay of the bus could be minimized, which
allows them provided more quality servers to the public. There are lots of researches that
digs into this area, which focuses on the relationship between the delay time and time
sections of a day (e.g., morning, afternoon, night), route and stations. However, in order to
reach predict an accurate bus delay, this is not enough. In this paper, we would go beyond
the conditions discussed above. and exam another important factor that causes delays - the
weather condition. specifically, This approach uses open data from government open portal
such as the historical bus delay datasheets, and historical weather datasheets. as the
source. then generate a large datasheet by joining that two datasheets. then apply different
data mining techniques on these data sheets to discover the relationships and frequent
patterns. to achieve this, we used a Apriority algorithm as well as deep learning algorithm is
designed to evaluate those frequent patterns and examine the relationship. base this.
conclude the reason that lead to delay, also the data unbalancing issues that cause hard in
form a correct module for prediction . The result is compared to the government open portal
provided delay data as well as weather conditions and shows the effectiveness and
correctness of our approach.



Author:
    Li Borui
    Li Qingyuan
    Hu Future
    Xie Xiaojian
    
    
    
    
    
## weather data:
    https://climate.weather.gc.ca/
    
    https://climate.weather.gc.ca/historical_data/search_historic_data_stations_e.html?searchType=stnName&timeframe=1&txtStationName=toronto&searchMethod=contains&optLimit=yearRange&StartYear=1840&EndYear=2019&Year=2019&Month=10&Day=19&selRowPerPage=25&txtCentralLatMin=0&txtCentralLatSec=0&txtCentralLongMin=0&txtCentralLongSec=0&startRow=51

    https://climate.weather.gc.ca/climate_data/hourly_data_e.html?hlyRange=2013-06-11%7C2019-10-19&dlyRange=2013-06-13%7C2019-10-19&mlyRange=%7C&StationID=51459&Prov=ON&urlExtension=_e.html&searchType=stnName&optLimit=yearRange&StartYear=1840&EndYear=2019&selRowPerPage=25&Line=51&searchMethod=contains&Month=10&Day=19&txtStationName=toronto&timeframe=1&Year=2019

## transport data:
    https://open.toronto.ca/catalogue/?vocab_topics=Transportation&n=5&sort=last_refreshed%20desc
    
## compile and run

### package used:
 pandas
 
 numpy
 
 tensorflow
 
 keras
 
 imbalanced-learn 
 
 multiprocessing

please make sure you have those package before running 

### program structure
the project root is comp-4710-project please launch code here to avoid error

the dataMining package contains all the code related to data mining

the Machine learning package contains all the code related to deep learning 


### first run:
    python dataMining/pre_procssing_bus.py
you may change the parameter in main called start and end to set the start and end year, but be sure, the range is between 2014 and 2019
### second run:
    python dataMining/aprioriDataMining.py
you may change the parameter called min_support of function generate_L() in main. but besure the value is under a reasonable range for Apriori 
### third run:
you may test different approach in deep learning:

approach 1 (Cluster Centroid undersampling):

     python 'Machine learning/classification_model_CC_undersampling.py'
    
approach 2 (modify class weight):
    
     python 'Machine learning/classification_model_class_weight.py'
    
approach 3 (the original one without improvement):
    
    python 'Machine learning/classification_model_original.py'   
     
approach 4 (random undersampling):
    
     python 'Machine learning/classification_model_random_undersampling.py'
    
### Bonus:
to test the performance between parallel and sequencial apriori, please run pre_processing_bus.py first as shown above,
then run:

    python dataMining/performance.py
    

## REMARK
the program must have the same structure as it shows. 

For the deep learning part, each python file corresponds to different implementation details
    

***important：the project may crash due to different version of anaconda, please use the newest one.***

***anaconda version: Python 3.7.4  [MSC v.1915 64 bit (AMD64)] :: Anaconda, Inc. on win32***

***pandas version: 0.25.1***


if you see the error message related something related to the panda package like "merge" then it is the panda and anaconda version issue

we test the program on general of WINDOWS machine, as well as the MACBook Pro, however, the program does not run MACBook Air due to some reason.



we use pycharm 2019.3 as IDE, the root path is the project root path. please insure that or the program won't run

please run under the project root folder, in that case you could set the the path in the code: add "../" before the path file, should fix it 

i.e. python dataMining/pre_processing.py
  
       
