# Predict-trip-duration
## Goal: 
  Predict the trip duration time from origin to destination. 
## Overview of the Assignment:
    To complete this assignment, you'll need:
        • a computer running MacOS or Linux with about 1.6 GB of storage space for data
        • an Internet connection to download some data
        • machine learning software of your choice
    A. You will download a public data set of Yellow Cab Taxi rides in New York City, where each
    row of the CSV data file provides features of one trip.
    B. Once you have downloaded the data, you'll need to preprocess it and split the data into
    training, validation, and test sets.
    C. You should then develop a machine learning regression model that can predict the time
    duration of a taxi trip. This model should be trained on the training set, tuned with the validation
    set, and evaluated with the test set. Your goal is to minimize the RMSE between your predicted
    trip duration and the ground-truth trip durations in the test set.
## Get the data:
    A1. Create a subdirectory and place all data and your software/report here.
    
    A2. Use a web browser to visit the New York City Taxi and Limousine Commission webpage for
    information on the [data](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).
    
    A3. Download the January 2016 Yellow Cab data set (1.6 GBytes, 10 million rows, in CSV
    format) found at this [link]:
    (https://s3.amazonaws.com/nyc-tlc/trip+data/yellow_tripdata_2016-01.csv)
    
    A4. Download a PDF file describing the data set schema:
    http://www.nyc.gov/html/tlc/downloads/pdf/data_dictionary_trip_records_yellow.pdf

## Data preparation
    B1. Clean and preprocess the data using best practices. You may want to remove rows that
    have outlier values or impute any missing values. Additionally, if you find that training your
    machine learning model takes too long (during step C3 later), you may want to sample the
    original data file down so that you can iterate experiments faster; if you perform sampling for this
    purpose, you must still use the original data to report your results.
    B2. Compute the duration of each trip. Observe that the data set, as you saw in step A5
    above, has pickup and dropoff times, but it is missing the overall time duration. This ground-truth
    value is very important, as your goal is to predict the duration of each taxi trip. You will need to
    compute this time duration by subtracting dropoff_time - pickup_time for each row and
    then append it to the end of the row for use as the ground-truth in your machine learning
    algorithm.
    B3. Split your data randomly into three parts. Following best practices, split the original data set
    into training, validation, and test data sets using the proportions of 0.6, 0.2, and 0.2, respectively, 
    for each set. Each input row should have a random chance to being assigned to each of the sets following
    those proportions. Name your three resulting files as data-training.csv, data-validation.csv, and data-test.csv. 
## Build model and train
    (link to notebook: https://github.com/wybeyond-drame/Predict-trip-duration/blob/master/Predict%20trip%20duration.ipynb)
    C1. Select features by looking through the data and choosing the features that you think will be
    able to predict the time duration of each trip.
    NOTE: It is important that you use only those features that are available to your algorithm when
    the Maps app generates the ETA at the start of the taxi trip. Therefore, you cannot use any of
    the features related to to the final fare/pricing, because those are not known until after the trip
    has completed. Specifically, you cannot use these features: payment_type, fare_amount,
    extra, MTA_tax, improvement_surcharge, tip_amount, tolls_amount, and
    total_amount.
    C2. Consider computing new features that are derivable from the features in the data set. If you
    have time, try joining external data sources, or use a library to generate new features. One
    potentially useful function is a geohash algorithm.
    C3. Implement your machine learning solution using any well-known machine learning software
    package. As mentioned above, we would prefer a working solution with R, Python, or
    Tensorflow. Train your model on data-training.csv, tune the model with data-validation.csv, and
    report your final results with data-test.csv. Your goal should be to minimize the RMSE between
    the ground-truth time duration values in data-test.csv and the values that you predict for each
    test instance.
