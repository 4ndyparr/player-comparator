# player-comparator
Jupyter notebook matplotlib dashboard to compare soccer players based on several statistics

Plots included:
      - goals plus assists VS games
      - goals plus assists per game VS season
      - assists per game VS goals per game
      - in-play goal percentage VS shots per game
      - in-play goal percentage unassisted VS in-play goal percentage assisted
      - in-play long-range shots: goals VS attempts
      - free kicks: goals VS attempts
      - set-piece headers: goals VS attempts
      - penalty kicks: goals VS attempts
      
Statistics included:
      - goals
      - shots
      - assists
      - xGs (expected Goals per shot)
      - GAA (Goals Above Average)
      

## about the data:
      the data was scraped from https://understat.com/ into two datasets:
      
        'allshots.csv' contains the data of all shots from the big five european leagues for the seasons
        from 2014-15 to 2017-18. The attributes recorded include the shot type, the situation or context
        of the shot, the xG statistic for that shot, and the location of the shot among others. 
        
        'allinfo.csv' contains data relative to each player such as their team/s each season and the
        number of appearances.
        
## credits:
      this notebook tries to replicate and expand on the interesting analysis and data visualizations
    ideas of Benjamin Morris' articles.
        
## in retrospect:
      the for loops ('...for player in players') applied to the pandas dataframes, although they make
    the code more readable, are very inefficient! Some of them take minutes!
    I would rewrite those parts using groupby(['player_id']), and applying transformations to these
    group dataframes, which would be exponentially faster.
        
        it would have been interesting to have plotted other statistics such as:
    # xGs-per-shot vs shots (it would show the type of shots each player is taking, and combined with
    the number of shots it will show the relationship bw volume and efficiency)
    # GAAs vs shots (it would show how the players perform in relation with the average player (xGs)).
    
        finally interactive plots you can hover onto and explore the different outliers and interesting
    points of the scatterplots would have been a great addition, but this was hard to do with
    matplotlib.    
