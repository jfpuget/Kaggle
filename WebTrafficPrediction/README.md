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

* Run the first_stage2.ipynb notebook.  It computes the first dat at which a page data is non zero. It should create a file in the Kaggle/data directory:
    * first.csv
    
