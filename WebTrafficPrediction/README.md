2n Prize solution for the Web Traffic Prediction competition on Kaggle.

Kaggle competition site: https://www.kaggle.com/c/web-traffic-time-series-forecasting

Process to reproduce the solution:

* Clone the Kaggle repository

* Download competition data into the Kaggle/input directory

* Go to the Kaggle/WebTrafficPrediction directory

* Run the keras-kf-12-stage2-sept-10.ipynb notebook.  This trains the base deep learning model and computes predictions from it. This should produce several files in the Kaggle/submissions directory, including:
     * keras_kf_12_stage2_sept_10_train.csv
     * keras_kf_12_stage2_sept_10_test.csv
      
* The file keras_kf_12_stage2_sept_10_test.csv is my first submission.  It scores 36.91121 and would have got the 4th rank overall.

* Run the Pred_11-stage2-sept-10.ipynb notebook.  This creates a median based model and computes predictions out of it.  It should produce files in the Kaggle/submissions directory, including:
    * pred_10_stage2_sept_10_train.csv
    * pred_10_stage2_sept_10_test.csv

* Run the first_stage2.ipynb notebook.  It computes the first date at which a page data is non zero. It should create a file in the Kaggle/data directory:
    * first.csv
    
* Run the xgb_23_keras_7_2_stage2-sept-10-2.ipynb notebook.  This creates the final model by running xgboost on the residuals for the neural network predictions. It uses the past visits plus the above two notebook outputs as features.  It should produce files in the Kaggle/submission directory, including:
    * xgb_1_2017-09-12-19-14-14_test.csv

* This file is my second submission. It scores 36.78499 and got me the second place.
    
Kaggle asks to provide a simpler model that provides 90% of the performance, if possible.  Such model is provided in file keras_simple.ipynb.  Its feature set is much simpler, basically the median of visits for each of the last 8 weeks of training data, plus the site (eg es.wikipedia.org), and the agent-access method.  Its output score 37.58692 and would have got the 9th rank.
