# Python-for-DS
# Data processing
First, we need to check the type:
```Python
import pandas as pd
music_pd = pd.read_csv("music.csv")
music_pd.isnull().sum()
music_pd_bkp = music_pd.copy(deep=True)
# music_pd.head()
music_pd.info()
```
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 1556 entries, 0 to 1555
Data columns (total 23 columns):
 #   Column                     Non-Null Count  Dtype 
---  ------                     --------------  ----- 
 0   Index                      1556 non-null   int64 
 1   Highest Charting Position  1556 non-null   int64 
 2   Number of Times Charted    1556 non-null   int64 
 3   Week of Highest Charting   1556 non-null   object
 4   Song Name                  1556 non-null   object
 5   Streams                    1556 non-null   object
 6   Artist                     1556 non-null   object
 7   Artist Followers           1556 non-null   object
 8   Song ID                    1556 non-null   object
 9   Genre                      1481 non-null   object
 10  Release Date               1556 non-null   object
 11  Weeks Charted              1556 non-null   object
 12  Popularity                 1556 non-null   object
 13  Danceability               1556 non-null   object
 14  Energy                     1556 non-null   object
 15  Loudness                   1556 non-null   object
 16  Speechiness                1556 non-null   object
 17  Acousticness               1556 non-null   object
 18  Liveness                   1556 non-null   object
 19  Tempo                      1556 non-null   object
 20  Duration (ms)              1556 non-null   object
 21  Valence                    1556 non-null   object
 22  Chord                      1556 non-null   object
dtypes: int64(3), object(20)
memory usage: 279.7+ KB
Second, change the types according to our needs.

For int64, we have ""
