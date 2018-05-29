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

Below I have included a sample run that demonstrates the code correctly 
generating a desired sized table, addressing duplicate moves, 
correct win conditions (black has to go left/right), and  optimal AI movesets.
This was tested on an external compiler as well as the campus unix system, 
using the provided Makefile. Please note that for some compilers 
(like Microsoft Visual C++ 2012), seems to take a couple seconds for the AI 
to make a move. On UNIX and cpp.sh the timing is much faster. 

***************Sample Run************************************************
You wish to challenge a computer in Hex? Very well, Let's play!

How big of a board do you want to play on? (5 - 11 recommended): 5
Good! The board is set!
  0 w 1 w 2 w 3 w 4
0 +---+---+---+---+
 b \ / \ / \ / \ / \
  1 +---+---+---+---+
   b \ / \ / \ / \ / \
    2 +---+---+---+---+
     b \ / \ / \ / \ / \
      3 +---+---+---+---+
       b \ / \ / \ / \ / \
        4 +---+---+---+---+
_________________________________________________________
Now we need to pick sides. I'll let you pick. (b/w): w
My turn! I move: 1 3
  0 w 1 w 2 w 3 w 4
0 +---+---+---+---+
 b \ / \ / \ / \ / \
  1 +---+---+---B---+
   b \ / \ / \ / \ / \
    2 +---+---+---+---+
     b \ / \ / \ / \ / \
      3 +---+---+---+---+
       b \ / \ / \ / \ / \
        4 +---+---+---+---+
_________________________________________________________
Your turn!
Where are you putting your piece? (x y = ) 4 0
  0 w 1 w 2 w 3 w 4
0 +---+---+---+---+
 b \ / \ / \ / \ / \
  1 +---+---+---B---+
   b \ / \ / \ / \ / \
    2 +---+---+---+---+
     b \ / \ / \ / \ / \
      3 +---+---+---+---+
       b \ / \ / \ / \ / \
        4 W---+---+---+---+
_________________________________________________________
My turn! I move: 1 2
  0 w 1 w 2 w 3 w 4
0 +---+---+---+---+
 b \ / \ / \ / \ / \
  1 +---+---B---B---+
   b \ / \ / \ / \ / \
    2 +---+---+---+---+
     b \ / \ / \ / \ / \
      3 +---+---+---+---+
       b \ / \ / \ / \ / \
        4 W---+---+---+---+
_________________________________________________________
Your turn!
Where are you putting your piece? (x y = ) 1 1
  0 w 1 w 2 w 3 w 4
0 +---+---+---+---+
 b \ / \ / \ / \ / \
  1 +---W---B---B---+
   b \ / \ / \ / \ / \
    2 +---+---+---+---+
     b \ / \ / \ / \ / \
      3 +---+---+---+---+
       b \ / \ / \ / \ / \
        4 W---+---+---+---+
_________________________________________________________
My turn! I move: 2 1
  0 w 1 w 2 w 3 w 4
0 +---+---+---+---+
 b \ / \ / \ / \ / \
  1 +---W---B---B---+
   b \ / \ / \ / \ / \
    2 +---B---+---+---+
     b \ / \ / \ / \ / \
      3 +---+---+---+---+
       b \ / \ / \ / \ / \
        4 W---+---+---+---+
_________________________________________________________
Your turn!
Where are you putting your piece? (x y = ) 3 1
  0 w 1 w 2 w 3 w 4
0 +---+---+---+---+
 b \ / \ / \ / \ / \
  1 +---W---B---B---+
   b \ / \ / \ / \ / \
    2 +---B---+---+---+
     b \ / \ / \ / \ / \
      3 +---W---+---+---+
       b \ / \ / \ / \ / \
        4 W---+---+---+---+
_________________________________________________________
My turn! I move: 2 0
  0 w 1 w 2 w 3 w 4
0 +---+---+---+---+
 b \ / \ / \ / \ / \
  1 +---W---B---B---+
   b \ / \ / \ / \ / \
    2 B---B---+---+---+
     b \ / \ / \ / \ / \
      3 +---W---+---+---+
       b \ / \ / \ / \ / \
        4 W---+---+---+---+
_________________________________________________________
Your turn!
Where are you putting your piece? (x y = ) 1 1
You can't do that!
Where are you putting your piece? (x y = ) 0 4
  0 w 1 w 2 w 3 w 4
0 +---+---+---+---W
 b \ / \ / \ / \ / \
  1 +---W---B---B---+
   b \ / \ / \ / \ / \
    2 B---B---+---+---+
     b \ / \ / \ / \ / \
      3 +---W---+---+---+
       b \ / \ / \ / \ / \
        4 W---+---+---+---+
_________________________________________________________
My turn! I move: 1 4
  0 w 1 w 2 w 3 w 4
0 +---+---+---+---W
 b \ / \ / \ / \ / \
  1 +---W---B---B---B
   b \ / \ / \ / \ / \
    2 B---B---+---+---+
     b \ / \ / \ / \ / \
      3 +---W---+---+---+
       b \ / \ / \ / \ / \
        4 W---+---+---+---+
_________________________________________________________
I win! Robots > Mankind!!
Want to redeem yourself? (y/n) n
Shutting down now, come challenge me again!