# Python-for-DS
# Data processing
First, we need to check the type:
```Python
import pandas as pd
music_pd = pd.read_csv("music.csv")
music_pd.isnull().sum()
music_pd_bkp = music_pd.copy(deep=True)
music_pd.head()
music_pd.info()
```
The output is:
```

Index	Highest Charting Position	Number of Times Charted	Week of Highest Charting	Song Name	Streams	Artist	Artist Followers	Song ID	Genre	...	Danceability	Energy	Loudness	Speechiness	Acousticness	Liveness	Tempo	Duration (ms)	Valence	Chord
0	1	1	8	2021-07-23--2021-07-30	Beggin'	48,633,449	Måneskin	3377762	3Wrjm47oTz2sjIgck11l5e	indie rock italiano, italian pop	...	0.714	0.8	-4.808	0.0504	0.127	0.359	134.002	211560	0.589	B
1	2	2	3	2021-07-23--2021-07-30	STAY (with Justin Bieber)	47,248,719	The Kid LAROI	2230022	5HCyWlXZPP0y6Gqq8TgA20	australian hip hop	...	0.591	0.764	-5.484	0.0483	0.0383	0.103	169.928	141806	0.478	C#/Db
2	3	1	11	2021-06-25--2021-07-02	good 4 u	40,162,559	Olivia Rodrigo	6266514	4ZtFanR9U6ndgddUvNcjcG	pop	...	0.563	0.664	-5.044	0.154	0.335	0.0849	166.928	178147	0.688	A
3	4	3	5	2021-07-02--2021-07-09	Bad Habits	37,799,456	Ed Sheeran	83293380	6PQ88X9TkUIAUIZJHW2upE	pop, uk pop	...	0.808	0.897	-3.712	0.0348	0.0469	0.364	126.026	231041	0.591	B
4	5	5	1	2021-07-23--2021-07-30	INDUSTRY BABY (feat. Jack Harlow)	33,948,454	Lil Nas X	5473565	27NovPIUIRrOZoCHxABJwK	lgbtq+ hip hop, pop rap	...	0.736	0.704	-7.409	0.0615	0.0203	0.0501	149.995	212000	0.894	D#/Eb
5 rows × 23 columns
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
```
Second, change the types according to our needs.
```Python
# To covert data in columns into a different type, we can use pandas' to_numeric function, in case that the data is unclear
# p = re.compile(r'\d+')
# music_df['Artist Followers'].apply(lambda x: int(x) if p.match(x) else None)
music_df['Artist Followers'] = pd.to_numeric(music_df['Artist Followers'],errors = 'coerce')# if there's " ", just return NA

```

For int64, we have "Artist Followers, Popularity"
