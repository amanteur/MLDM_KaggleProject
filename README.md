# MLDM group project for Kaggle's KKBox's Music Recommendation Challenge
Here you can find the description of the project.
- [Link](https://www.kaggle.com/c/kkbox-music-recommendation-challenge) to the challenge.
- **Challenge's main point**:  
  Predict given members information, song information and in which part of UI the member listened this song, whether the member of the service will listen the particular song again in one month.
- Group's participants: 
  - [Amantur Amatov](https://github.com/amanteur)
  - [Irina Yuryeva](https://github.com/upayuryeva) 
  - [Edgar Zakharyan](https://github.com/edgar2597)
- **Disclaimer:** All code is presented in Jupyter Notebooks. Each member did his/her own work, which **may** intersects with other works of group's members.

--------
This project can be divided in two parts:
1) Explanatory data analysis and feature extraction
2) Model selection, training and evaluation

### First part of the project
[Link](https://github.com/amanteur/MLDM_KaggleProject/tree/main/Part1) to the folder of .ipynb files.  
Here each member describes what they've done during first half of the project:
- Amantur:
  - made a full explanatory data analysis on every given dataset;
  - made a feature extraction and preparation on 'members' and 'train/test' datasets. All transformations are presented in table.  
  
  | Was         | What were done       |Now         |  
  | ----------- | ----------- | ----------- |  
  | gender column had string type with values 'female' and 'male' with NaNs | Transformed gender column to bool and treated the NaNs in this column in two different ways (putting random values or putting 3rd 'unknown' value) | gender column without NaNs and has two modes (random and unknown), that will be tested in the next phase |  
  | birthday column with age of member | Replaced birthdays (ages), which are greater than 90 and smaller then 0 with 0 (which is 'unspecified'). Added a binary feature, whether the user specified the age or not | Two features - filtered age and has age or not |  
  | dates when the membership started and when it ends |  Added new feature 'membership days', which means, how long this user is a member of the service | membership days |
  | in which part of UI member listened the song features: source_type, source_system_tab, source_screen_name| Replaced NaNs with 'Unknown' rows in source_type, source_system_tab, source_screen_name. In test there was source screen names, which were absent in train dataset, so I replaced them with 'Unknown' too. | filtered features source_type, source_system_tab, source_screen_name |
  | Nothing | In train and test added a feature, which tells how many songs the user listened, and a feature, which tells how many plays a particular song had (so to say a song popularity) | Two features: user_plays and song_plays | 
  | Nothing | In train added features based on target feature - how many times a member replayed any song and what is the ratio to the all songs, and how many replays a song had and its ratio to all plays. Then these features were transfered to test (cause it has no target data). There were users and songs, which didn't appear in train, so I leave them as NaN in these target-based features | two features: user_replays_ratio and song_replays_ratio |
- Irina: <br>
  Was working on feature extraction of songs and song_extra (some additional songs information) datasets. 
  In song_extra dataset was song name and isrc code, where I found information about country and release year. I join song and song_extra datasets and make transformations presented in table. 
  | Was         | What were done       |Now         |
  | ----------- | ----------- | ----------- |
  | Song length in ms      |Songs and train dataset were join and plot of songs length dictribution in train dataset was made. Based on the plot songs lengths were difided on intervals to make categorical features based on song lenght | Categorical feature based on intervals of song length.|
  | Genre category  | A lot of songs have several genres. And my idea was instead of making dummy features on genres like "12/13" and "12", derive genre "12/13" on "12" and "13" and make dummy faetures on 2 genres. Then, after join songs data and train data, dummy features were groubed by member and summarize, then, normalized by member, to get representation on what genres they prefer. Also I count genres for every song, maybe this feature will show us if member likes multigenre songs.| 1. Nubmer of genres of the song. <br>2. Songs from format "12/13/14" to [12, 13, 14] to make in easier to get dummy features from several categories|
  |Artist name, Composer, Lyricist |Count the number of *feature name* of the song.|Nubmer of *feature name* of the song|
  |Year|To derive years on categories, i derive them on decades|Decades|
  |Language, country|Nothing|Language, country|
  - Getting rid of NAN values <br>
    There was some nan values for year, language, country, genres features. To get rid of them but not lose some important information by just making them "UNKNOWN" I found the most popular values of those features for every artist and fill nans for every artists with them. Other features in all data I just make "UNKNOWN".
- Edgar:

  I did the EDA of given datasets. Visualized distributions of some core user features, like gender, age and registrations time. Merged and splited all datasets into training, validation and testing ones.
  Also did some feature engineering and transformed them to make them more valuable for fiting. I did a transformation of date varibles (expiration date, registration_init_time, membership_days), since they were presented not in date formats. I changed there formats into datetime %Y%m%d. And then 
  I extracted year, month and day data as a separate columns from both registration_init_time and expiration_date.

-------
Here will be written the vision of the project's next phase:
- Create one structured notebook where all of the best parts of expanatory analysis of group members' notebooks will be written.
- Create one structured notebook where all of the best parts of feature extraction of group members' notebooks will be written.
- Create a notebook for model selection and evaluation.
- Create a presentation based on our work.

### Second part of the project
Here each member describes what they've done during second half of the project:
TBA.
