# Hex-Game-in-C-
The included file is the my third draft of the Hex game in C++. 
The program is playable against an AI that makes optimal moves. This program 
creates a Board class in which two players, AI/Human denoted as player Black 
and player White try to get a path made from one side of the board, based on
their player categorization, using nodes under their names. This is my third
attempt at the Hex game and the difference this time is the AI uses a
Monte Carlo simulation of determining the next optimal move. Basically, how 
it works is we get all the empty spots in the board and stores them into
a permutation which is then randomized. The AI takes a point and plays off 
the point to which a BFS checks the win condition. If the computer won then
we increment a win counter that is used when we /1000 as a value for optimal moves. 
This is reset and done 1000 times to pick a very optimal move. 
