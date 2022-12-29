# Report-  Ludo Board Game Status Tracker

## Information from Milestone 1

- team members:

  - Sofya Aksenyuk, 150284

  - Uladzimir Ivashka, 150281

- selected board game:

  - “Ludo” (“Chińczyk” in polish)

- a short description of the game:

  - a board game for two to four players, in which the players race their four tokens from start to finish according to the rolls of a single dice

- list of in-game items:

  - 16 tokens (4 tokens a player)
        
  - board
        
  - dice

- description of 5 events occurring in the game:

  - enter play from the yard (roll a dice of 6)

  - roll a dice on the playing field

  - make a token move according to the rolled dice

  - beat opponent (enter the same square as the opponent is in, so that it goes back to its yard)

  - enter the home (count score)

## Description of dataset

Each video is around 30-35 seconds long

- Easy:

  - perfect upper view

  - game elements are not covered with anything

  - no shadows or light reflections

  - camera is stable

- Medium:

  - perfect upper view

  - game elements are not covered with anything

  - shadows

  - worse light

  - light reflections

  - camera is stable

- Difficult:

  - angled view

  - game elements are covered with hands from time to time

  - shadows

  - worse light

  - light reflections

  - shaking of camera

## Used techniques

- Common for all modes:

  - For tracking tokens and detection of other game elements:
 
    - template detection

    - KCF tracker for dice and CSRT multitrackers for tokens

  - For tracking game score and amount of tokens left in yard:

    - function that checks if token bbox is in home bbox

  - For tracking dice amount:

    - Gaussian Blur

    - thresholding

    - dilation

    - Hough Circles

  - For tracking distance between opponents:

    - Initial board is divided into 4 parts (left up, right up, left down, right down)

    - Intersection points between these 4 parts are detected

    - Manhattan distance is calculated, taking into account what board parts the opponents are in, e.g.:

      - if token A is in left up part and token B is in right down part: 

        distance = sum of:
          
          - manhattan distance of up intersection point to right one (or down - left) 

          - manhattan distance of token A to up intersection point

          - manhattan distance of token B to right intersection point

          - constant (manhattan distance of passing one of 4 board parts)

  - For tracking beat opponent:

    - threshold of distance described above

- Used just for difficult mode:

  - For better tracking:

  - video stabilization (due to camera shaking)

  - frame translation (due to angled view)
