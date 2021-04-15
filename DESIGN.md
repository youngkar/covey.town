## Overview
To add TicTacToe to Covey.Town, we continued to utilize REST APIs for frontend-backend communication of both the game and the leaderboard. We also used
socket communication for keeping a player's board updated when the other player makes a move (i.e. the player doesn't send a request, but still receives an
update from the server). Since we utilized these existing methods of communication, the overarching architecture is largely unchanged. 



In the backend, we created new object representations for the game board and leaderboard and added them into each town. We also added to the REST API and WebSocket.

On the frontend, we have added new objects to the map as well as new components to interact with for the game board and leaderboard. 

## Backend updates 
#### Leaderboard.ts (all new)
| Class | Leaderboard |
|-|-|
| State            | allScores [an array of userIDs (string), userNames (string) and scores (number)] |
| Responsibilities | Tracks the running scores for players inside each room                           |
| Collaborators    | Player                                                                           |
#### TicTacToe.ts (all new)
| Class | TicTacToe |
|-|-|
| State            | player1 (String), player2 (String), gameBoard (2D array of numbers), current player (number), winningPlayer (String) |
| Responsibilities | Manages and tracks the events of a TicTacToe game                           |
| Collaborators    |                                                                            |
#### CoveyTownController.ts
| Class | CoveyTownController |
|-|-|
| State            | players in the room (Player[]), valid sessions (PlayerSession[]), videoClient (IVideoClient), listeners (CoveyRoomListener[]) |
| Responsibilities | Manages the events that occur in or involving players in the room, including adding, removing or relocating a player in a room.  |
| Collaborators    | PlayerSession, IVideoClient, TwilioVideo, CoveyRoomListener          |
#### CoveyTownStore.ts
| Class | CoveyTownsStore |
|-|-|
| State            |  |
| Responsibilities |  |
| Collaborators    |  |
#### CoveyTownRequestHandlers.ts
#### towns.ts

<br><br>
## Frontend updates 
#### Board.tsx
#### GameModal.tsx
#### LeaderboardModal.tsx
#### WorldMap.tsx
#### App.tsx