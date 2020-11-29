IGMC on Spotify Million Playlist Dataset

The task is to predict the remaining songs in playlists, given their current songs. More details can 
be found in https://www.aicrowd.com/challenges/spotify-million-playlist-dataset-challenge
 
IGMC model learns from graph structures. Any additional features are optional (and beneficial) for the training.

| Training Set Size (Edges) |  Epoch | R-Precision on Test Set |
|-------------------|:------:|------------:|
| 8K                |     50 |        0.18 |
| 80K               |      3 |        0.34 |
| 80K Sparse        |     10 |        0.29 |
| 800K              |      3 |        0.26 |
| 800K Sparse       |      2 |        0.23 |

Training sets are randomly selected for each training. Test set contains 111 playlist, their ground truth songs together with 15000 false songs. 
False songs are randomly selected from immediate neighbors (songs that are in other playlists together with some ground truth songs).

![song degree histogram](imgs/songhist.png)

![playlist degree histogram](imgs/plhist.png)

47 percent of the songs are in one playlist.  
84 percent of the songs are in less than 10 playlists.  

Average size of a subgraph: 527kB (n=4000)
Average number of neighbor songs: 200.000 (n=?)
1054TB is required.


