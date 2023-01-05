# Please, go to another branch (difficult_update)

(We didn't want to merge it to save the initial commit dates)

# Ludo Board Game Status Tracker

Co-authored-by: [@giminosk](https://github.com/Giminosk)

![Report](https://github.com/allsuitablenamesarealreadytaken/ludo-tracker/blob/main/REPORT.md)

![Code](https://github.com/allsuitablenamesarealreadytaken/ludo-tracker/tree/main/code)

![Snippets](https://github.com/allsuitablenamesarealreadytaken/ludo-tracker/tree/main/snapshots)

![Results](https://github.com/allsuitablenamesarealreadytaken/ludo-tracker/tree/main/results)

## Description

- essence of the game:

  - a board game for two to four players, in which the players race their four tokens from start to finish according to the rolls of a single dice

- list of in-game items:

  - 16 tokens (4 tokens a player)
        
  - board
        
  - dice

- description of 5 events occurring in the game:

  - enter play from the yard (roll a dice of 6):
  
      - tracks players' yards => tracks amount of tokens in field

        **Implementation:** yard bbox with bboxes of each token inside; tracks by coordinate similarity

  - roll a dice on the playing field:
    
    - tracks score on a dice

  - make a token move according to the rolled dice:
  
    - tracks token in the field

  - beat opponent (enter the same square as the opponent is in, so that it goes back to its yard):
    
    - tracks players' yards => tracks amount of tokens in the field

  - enter the home (count score):
  
    - tracks players' homes => counts current score of a player

      **Implementation:** tracks by token bbox' coordinate similarity with home bbox)
        
