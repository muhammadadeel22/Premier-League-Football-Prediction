# Premier-League-Football-Prediction
MSc Project

This Jupyter Notebook demonstrates the use of a Long Short-Term Memory (LSTM) recurrent neural network and a Random Forest Classifier to predict the outcome (win, lose, or draw) of English Premier League (EPL) football matches.  The model leverages historical match data and engineered features to make predictions, specifically focusing on capturing temporal dependencies in team performance.
Data and Preprocessing

The notebook begins by loading a dataset containing EPL match results.  The dataset includes features such as:

    Team: The name of the home team.
    Opponent: The name of the away team.
    Venue: Home or Away
    Date: The date of the match.
    Time: Match Time
    Result: Win, Lose or Draw for the home team.
    Goals Scored (gf): Number of goals scored by home team
    Goals Conceded (ga): Number of goals conceded by home team
    Shots (sh): Total number of shots taken by home team
    Shots on Target (sot): Number of shots on target by home team
    Distance Covered (dist): Total distance covered by home team (in km)
    Free Kicks (fk): Number of free kicks awarded to home team

Data preprocessing steps include:

    Data Cleaning: Removing unnecessary columns and handling missing values.
    Feature Engineering: Creating new features such as rolling averages of goals, shots, and other key performance metrics over the previous three matches. This incorporates temporal dynamics into the model.
    Feature Encoding: Converting categorical features (team names, venue) into numerical representations.

Model Training and Evaluation

A Random Forest Classifier is trained using the preprocessed data. The dataset is split into training and testing sets (matches before and after January 1st, 2024, respectively).  The model's performance is evaluated using several metrics:

    Accuracy: The overall correctness of predictions.
    Precision: The proportion of correctly predicted wins out of all predicted wins.
    Precision-Recall Curve: A visualization of the trade-off between precision and recall at various thresholds.
    Confusion Matrix: A table showing the counts of true positives, true negatives, false positives, and false negatives.
    Feature Importance: A measure of how much each feature contributes to the model's predictions.

A sequential LSTM model is built using Keras. The model architecture consists of:

    Two LSTM layers with dropout for regularization.
    A dense output layer with a sigmoid activation function for binary classification (win/loss/draw simplified to win/not win).

The model is trained using the training data sequences and evaluated on the test data sequences.  Performance is evaluated using:

    Accuracy: The overall correctness of predictions.
    Precision: The proportion of correctly predicted wins out of all predicted wins.
    Classification Report: Provides precision, recall, F1-score, and support for each class (win and loss/draw).
    Confusion Matrix: A table showing the counts of true positives, true negatives, false positives, and false negatives.

Results and Visualization

The notebook includes visualizations of the model's performance:

    Confusion Matrix Heatmap: A visual representation of the model's predictions compared to actual results.
    Precision-Recall Curve: Shows the relationship between precision and recall as the classification threshold varies.
    Feature Importance Bar Plot: Displays the relative importance of each feature in the model.

Requirements

To run this notebook, you will need:

    Python 3.x
    pandas
    scikit-learn
    seaborn
    matplotlib

Make sure you install these libraries using pip: pip install pandas scikit-learn seaborn matplotlib
Usage

    Mount Google Drive: The code assumes the data is stored in your Google Drive. You'll need to run the initial cell to mount your drive.
    Update File Path: Adjust the file path in pd.read_csv() to point to your matches.csv file.
    Run the Notebook: Execute all cells in the notebook sequentially.

