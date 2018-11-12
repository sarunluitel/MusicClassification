The music classification ipynb provides all the methods and implementation of the algorithm. 

The methods to specify the feature extraction are:

  --fourierfeatures -> extracts n number of features after fast furouir transform
  @params (data, n) where data is a [tuple ([song_samples], samping_rate)] -> list of outputs from librosa.load()
                    and n is the number of features to extract. default = 1000 
                    
  --mfccfeatures -> extracts mean of features after mfcc transform
  @params (data) where data is a [tuple ([song_samples], samping_rate)] -> list of outputs from librosa.load()
  
  --getBest_Features -> extracts mean, standard Deviation, skewness and kurtosis of features after mfcc transform
  @params (data) where data is a [tuple ([song_samples], samping_rate)] -> list of outputs from librosa.load()
  
The methods to specify the algorithm are:
   -- genericML1 -> This method encapsulates random forest
   @params (tdf,ldf) where tdf is training features dataframe and ldf is training labels dataframe
   
   -- genericML2 -> this method encapsulates k-nearest Neighbour
   @params (tdf,ldf) where tdf is training features dataframe and ldf is training labels dataframe
   
ExampleUsage:
Feature Extraction: training_features = getBest_Features(data = data)
Running the algorithm: myModel = genericML1(trainingData,trainingLabel) 
prediction: myModel.predict(testingData)
