# Analyzing Key Features of Song Popularity on Spotify‬‬
*Members:‬‭ Trevor Cai, Samantha Chou, Samson Hyunh, Hannah Jin, Shreyas Kamath, Joshua Li‬*

This project uses the Spotify tracks dataset and utilizes supervised learning along with other data science techniques to determine the‬ best audio feature predictors for song popularity.

### i. DATA SET‬
This project uses the Spotify tracks dataset from Spotify Web’s API that includes audio‬
‭ features for a playlist of songs across over 125 genres. For each track, there is a corresponding‬
‭ track_id, artists, album, track name, and genre, among many other numerical features, including‬
‭ popularity from a scale of 0 to 100 (calculated from an algorithm based mostly on number of‬
‭ plays and recency of plays), danceability (0.0-1.0), duration in milliseconds, loudness in‬
‭ decibels, acousticness (0.0-1.0), etc.

### ii. OVERVIEW OF PROBLEM‬
This project uses supervised learning and other data science techniques to determine the‬
‭ best audio feature predictors for song popularity.‬

### iii. KEY METHODOLOGY‬
We began by cleaning the dataset and dropping non-numeric data to ensure a‬
‭ genre-agnostic, broad analysis of what drives song popularity. The data was binned into three‬
‭ categories—low, medium, and high popularity—to simplify the classification problem. A‬
‭ correlation analysis was performed to identify potential predictors of popularity, and we ensured‬
‭ that the models we employed were robust to multicollinearity among the features. For model‬
‭ optimization, we used GridSearchCV to tune hyperparameters such as the maximum depth for‬
‭ the decision tree and the number of estimators for the random forest. While further tuning of‬
‭ random forest hyperparameters was intended, time constraints limited this process. The‬
‭ maximum depth validated for the decision tree was also applied to the random forest for‬
‭ consistency. Finally, we visualized feature importance and evaluated model performance using‬
‭ confusion matrices, with decision trees and random forests emerging as the most effective‬
‭ methodologies for analyzing the most insightful feature importances.‬
‭ 
### iv. RESULTS‬
The results of the analysis revealed that audio features such as `‬‭acousticness‬‭`,‬ 
`speechiness‬‭ `, and `‬‭ energy‬‭ `, along with track duration (`‬‭duration_ms‬‭`), were the most‬
‭ significant predictors of song popularity, as identified by both the decision tree and random‬
‭ forest models. In contrast, attributes like `‬‭key‬‭`, `‬‭mode‬‭`, and `‬‭explicit‬‭` were found to have‬
‭ minimal influence on popularity.‬

The decision tree model achieved an optimal depth of 20 and produced an overall‬
‭ accuracy of 64% on the validation set. Its performance varied across classes, with class `1`‬
‭ (medium popularity) showing the highest recall (76%), while class `2` (high popularity) had a‬
‭ significantly lower recall of 30%, indicating difficulty in correctly predicting less frequent‬
‭ categories. The weighted average F1-score for the decision tree was 0.64, reflecting moderate‬
‭ effectiveness but notable struggles with class imbalance.‬

The random forest, with 200 estimators as its best hyperparameter, outperformed the‬
‭ decision tree with an overall accuracy of 70%. It achieved a strong recall of 87% for class `1`,‬
‭ demonstrating its robustness in identifying medium popularity tracks, but struggled with class‬
‭ `2`, which had a low recall of 25%. The macro average F1-score of 0.60 for the random forest‬
‭ indicates slightly better performance than the decision tree, particularly in balancing precision‬
‭ and recall across all classes. Overall, the random forest proved to be a more effective model for‬
‭ predicting song popularity, though both models struggled with minority class predictions.‬

One of the most interesting features to us was the duration of the song. There has been a‬
‭ general notion of popular songs getting shorter in length and the data shows a clear "sweet spot"‬
‭ for song length, where tracks under roughly 1 million milliseconds (about 16-17 minutes) tend to‬
‭ achieve higher popularity scores, with the most popular songs (scoring 80-100) typically being‬
‭ even shorter. After we determined that the duration of a song has high feature importance, we‬
‭ further inspected the duration data. We observed a gradual decline in maximum potential‬
‭ popularity as songs get longer. However, the wide vertical spread of points across most durations‬
‭ indicates that while length may influence popularity, it's not the sole determining factor – songs‬
‭ of similar lengths can have vastly different popularity scores.‬

## v. HOW TO USE THE CODE‬
1. Upload or View The Notebook (Set up the environment)‬
  a.‬‭ Open Google Colab.‬
  b.‬‭ Click on File → Upload Notebook.‬
  c.‬‭ Select the file CS_M148_Final_Project_Code.ipynb from your computer and upload it.‬
    i.‬‭ Look through the code to become familiarized with what it does‬
    ii.‬‭ Prepare the dataset and file formats‬.
   
If using the appendix code, just click the link(s) below.‬

3. Run All Cells‬
  a.‬‭ Click Runtime → Run All to execute all cells in the notebook sequentially.‬
  b.‬‭ If you prefer to run individual cells, click on the play button beside each cell‬
  c.‬‭ After executing the code, analyze how it works with your goals‬
