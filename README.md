# player-comparator
Matplotlib dashboard to compare soccer players based on several shooting stats

## dashboard
![Dashboard Sample](https://github.com/4ndyparr/player-comparator/blob/master/dashboard_sample3.png)

## the data

The data was scraped from https://understat.com/ into two datasets:
      
* _**allshots.csv**_ contains the data of all shots from the big five european leagues for the seasons
from 2014-15 to 2017-18. The attributes recorded include the shot type, the situation or context
of the shot, the xG statistic for that shot, and the location of the shot among others. 
        
* _**allinfo.csv**_ contains data relative to each player such as their team/s each season and the
number of appearances.
        
## credits

This notebook tries to replicate and expand on the interesting analyses and data visualizations
ideas of __Benjamin Morris'__ articles.
        
## in retrospect

* The _for_ loops applied to the dataframes within list comprehensions i.e.
`[len(shots[shots.player_id==player]) for player in players]`,
although they make for easy readable code, they are very inefficient. Some of them take minutes!
They loop through the whole database one time per player. I would rewrite those parts using something
like `shots.groupby(['player_id'])` and applying transformations to these group dataframes,
which would be exponentially faster.
        
* It would have been interesting to have plotted other statistics such as:
  * xGs-per-shot vs shots (it would show the type of shots each player is taking, and combined with
      the number of shots it will show the relationship between volume and efficiency)
  * GAAs vs shots (it would show how the players perform in relation with the average player (xGs)).
    
* Finally, making the plots interactive so you can explore the different outliers and interesting
points of the scatterplots looks like the next logical step, but it is beyond the scope of this
project, which was to familiarize myself with Matplotlib.
