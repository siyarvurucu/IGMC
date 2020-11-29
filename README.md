IGMC on Spotify Million Playlist Dataset

The task is to predict the remaining songs in playlists, given their current songs. More details can 
be found in the competition https://www.aicrowd.com/challenges/spotify-million-playlist-dataset-challenge
 
IGMC model learns from graph structures. Any additional features are optional (and beneficial) for the training. The model is inductive; it can be directly applied to previously unseen data points.
On the down side, preprocessing time of the dataset is too long. A new subgraph must be created with respect to each node pair, which takes much longer time than one forward-backward pass of a GNN.
Training of the models in the table below is quite limited due to this restriction - the dataset contains ~65M edges. The challenge dataset in the competition contains 10k playlists. Evaluation of each song with 10k playlists would take around 700 days in google colab.

Training sets are randomly selected for each training. Test set contains 111 playlist, their ground truth songs together with 15000 false songs. 
False songs are randomly selected from immediate neighbors (songs that are in other playlists together with some ground truth songs).

| Training Set Size (Edges) |  Epoch | R-Precision on Test Set (n=111) |
|-------------------|:------:|------------:|
| 8K                |     50 |        0.18 |
| 80K               |      3 |        0.34 |
| 80K Sparse        |     10 |        0.29 |
| 800K              |      3 |        0.26 |
| 800K Sparse       |      2 |        0.23 |

**R-Precision:** (averaged) Percentage of the correct songs in the top N recommendations for a playlist, where N is the number of songs in the playlist.  
Recommendations contain (15000+N) songs.

![song degree histogram](imgs/songhist.png)

![playlist degree histogram](imgs/plhist.png)

47 percent of the songs are in one playlist.  
84 percent of the songs are in less than 10 playlists.  


