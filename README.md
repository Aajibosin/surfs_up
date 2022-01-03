# Overview of the analysis
The purpose of this project is to have an insightful information on weather report of a particular area at given period of time.
By using Sqlite database information, we are able to retrieve information to know the temperature and precipitation of a regiion.
And also using the right tools from pandas we were able to generate the statistics of mean, standard deviation, minimum, maximum and count.



# Results
  We have different results from this project,
* The first result is query that filters the Measurement table to retrieve the temperatures for the month of June. 
  Measurement = Base.classes.measurement
  Station = Base.classes.station
  Session = Session(engine)
  prev_year = dt.date(2017, 8, 23)
  dt.timedelta()
  prev_year = dt.date(2017, 8, 23) - dt.timedelta(days=365)
  results =[]
  results = Session.query(Measurement.date, Measurement.prcp).filter(Measurement.date >= prev_year).all()
  print(results)
  
  <img width="869" alt="image" src="https://user-images.githubusercontent.com/93049677/147924469-872b46e7-6cd5-470e-b927-73d40fd615cf.png">

* The second result is converting the above result into dataframe 
   df = pd.DataFrame(results, columns=['date','precipitation'])
   df.set_index(df['date'], inplace=True)
   print(df.to_string(index=False))
   
   
   <img width="825" alt="image" src="https://user-images.githubusercontent.com/93049677/147924688-184de30e-3164-46ee-80cb-5235492db219.png">

* The third is, using the statistics to get the mean, std, count, minimum and maximum,
<img width="634" alt="image" src="https://user-images.githubusercontent.com/93049677/147924811-16162ee5-93bd-40ac-b1d3-e8b798532d3c.png">



# summary
Using SQLite, we were able to get temperature and precipitation of two different months June and December,
by using queries to create engine and also a session link from python to database. The first query was to retrieve temperature
for June and December, then we converted the results to dataframe to enable us to have a proper view of the data and finally 
we used statistical approaach to get the mean, std, minimum, maximum and count for both June and December.
Query 1, df.plot() this will be used to derive a graphical representation
Query 2, session.query(func.count(Station.station)).all() this will be used to get the number of stations.


