# Final Project

### In one sentence, describe your project.

We are going to build a shared network snake game for synchronizing network data / messages to have smooth gameplay performance.

### What is the minimum deliverable for this project?

We will build a snake game in python using pygame library. 

This python binary will be controlled by an external C++ backend, which will need to handle decisions about movements of the players on the screen of the multiplayer python snake game.
The C++ backend is in charge of determining who will be the server, and who will be the clients. Only one player can be the server. When the server received all client's messages a 
message handler will distribute global coordinates / collision logic to each player's snake python game.

### What is the maximum deliverable for this project?

In addition to the features above, we will build a functional snake game, where users fight to eat an "apple" to expand their snake. If there is any collision, the designated snake who collided into the body of another snake will be destroyed. If there is further time, we can introduce some AI snakes to account for missing players.

### What tools or environment will you be using?

We will be using C++ to control shared network message handler threads and named pipe threads for the communication from backend to frontend python application, Python for the GUI and snake game animations, and running our tests on Ubuntu Linux 16.04.

### What are your first step(s)?

1. Create a local multiplayer snake game in python with max players of 3-4. (This will include collision game physics logic, and "apples", which expand the snake's body)
2. Create a named pipe handler in C++ which can control movements of our snakes.
3. Create a server/client relationship in C++ which will dictate, whoever is first to initialize the game will be the server, others are the client.
4. Create backend logic , when the server has received all clients data and its own (data being the snake's position in the next frame), then it will send a message to all other clients, to allow update of game's graphics (network data synchronization via "snapshots" of local snake data). 

### Find at least one related publication or tool and reference it here.

(Explanation of network sync)
https://www.dreamincode.net/forums/topic/402599-computer-networking-two-player-interactive-game/

### What is the biggest problem you foresee or question you need to answer to get started?

I do not know anything about how timing delays on a network may impact game performance. Reading through the documentation of shared network games, a main issue constantly feared in the gaming world, is when one player/client sees an image of another player/character, how there is a "lag time disposition". We may have apply techniques inside and outside of class to deal with things like thread synchronization between the network data and local game data to improve lossy fps.
