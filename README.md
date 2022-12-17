# Ludo Board Game Status Tracker

## Description

- a short description of the game:

  - a board game for two to four players, in which the players race their four tokens from start to finish according to the rolls of a single die

- list of in-game items:

  - 16 tokens (4 tokens a player)
        
  - board
        
  - die

- description of 5 events occurring in the game:

  - enter play from the yard (roll a die of 6):
  
      - tracks players' yards => tracks amount of tokens in field

      - (yard bbox with bboxes of each token inside; tracks by coordinate similarity)

  - roll a die on the playing field:
    
    - tracks score on a die

  - make a token move according to the rolled die:
  
    - tracks token on the field

  - beat opponent (enter the same square as the opponent is in, so that it goes back to its yard):
    
    - tracks players' yards => tracks amount of tokens in field

  - enter the home (count score):
  
    - tracks players' homes => counts current score of a player

    - (tracks by token bbox' coordinate similarity with home bbox)
        
