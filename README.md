# MLDM group project for Kaggle's KKBox's Music Recommendation Challenge
Here you can find the description of the project.
- [Link](https://www.kaggle.com/c/kkbox-music-recommendation-challenge) to the challenge.
- **Challenge's main point**:  
  Predict whether the member of the service will listen the particular song again in one month given members information, song information and in which part of UI the member listened this song.
- Group's participants: 
  - [Amantur Amatov](https://github.com/amanteur)
  - [Irina Yuryeva](https://github.com/upayuryeva) 
  - [Edgar Zakharyan]()
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
  - made a feature extraction and preparation on 'members' and 'train/test' datasets:
    - members:  
      Transformed gender column to bool and treated the NaNs in this column two different ways (putting random values or putting 3rd 'unknown' value. Replaced birthdays (ages), which are greater than 90 and smaller then 0, with 0 (which is 'unspecified').Added a binary feature, whether the user specified the age or not. Added new feature 'membership days', which means, how long this user is a member of the service.
    - train/test:  
      Replaced NaNs with 'Unknown' rows in source_type, source_system_tab, source_screen_name. In test there was source screen names, which were absent in train dataset, so I replaced them with 'Unknown' too. In train and test added a feature, which tells how many songs the user listened, and a feature, which tells how many plays a particular song had (so to say a song popularity). In train added features based on target feature - how many times a member replayed any song and what is the ratio to the all songs, and how many replays a song had and its ratio to all plays. Then these features were transfered to test (cause it has no target data). There were users and songs, which didn't appear in train, so I leave them as NaN in these target-based features.
- Irina:
  - Something1
  - Something2
  - etc
- Edgar:
  - Something1
  - Something2
  - etc

-------
Here will be written the vision of the project's next phase:
- Something1
- Something2
- etc

### Second part of the project
Here each member describes what they've done during second half of the project:
TBA.
