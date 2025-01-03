# Project Title

AI Solution to Mancala 

## Description

This program is a mancala game that was generated by AI.

## AI Prompts

* Prompt for Board.java
~~~
Create this, ignore all "Link icon"

Constructor Details Link icon
Board Link icon
public Board()
Initializes a new Mancala board with pits and stores.
Method Details Link icon
setUpPits Link icon
public void setUpPits()
Establishes 12 empty Pits in the board
getPits Link icon
public ArrayList<Pit> getPits()
Returns the list of pits in the board, not including the stores
Returns:
ArrayList of pits
getStores Link icon
public ArrayList<Store> getStores()
Returns the list of stores in the board, not including the stores
Returns:
ArrayList of Stores
setUpStores Link icon
public void setUpStores()
Establishes 2 empty Stores in the board
initializeBoard Link icon
public void initializeBoard()
Initializes the board by distributing stones.
resetBoard Link icon
public void resetBoard()
Resets the board by redistributing stones but retains the players.
registerPlayers Link icon
public void registerPlayers(Player one,
 Player two)
Connects Players to their Stores. Will need to call methods in store and in player to ensure a two-way connection
Parameters:
one - Player one
two - Player two
moveStones Link icon
public int moveStones(int startPit,
 Player player)
               throws InvalidMoveException
Moves stones for the player starting from a specific pit.
Parameters:
startPit - The starting pit
player - The player making the move
Returns:
The total number of stones added to the corresponding store
Throws:
InvalidMoveException - If the move is invalid
distributeStones Link icon
public int distributeStones(int startingPoint)
                     throws PitNotFoundException
Helper method that distributes stones into pits and stores, skipping the opponent's store.
Parameters:
startingPoint - The starting pit
Returns:
The total number of stones added to pits and stores
Throws:
PitNotFoundException - If the pit number is invalid
captureStones Link icon
public int captureStones(int stoppingPoint)
                  throws PitNotFoundException
Captures stones from the opponent's pits.
Parameters:
stoppingPoint - The stopping pit
Returns:
The number of stones captured, if any
Throws:
PitNotFoundException - If the pit number is invalid
getNumStones Link icon
public int getNumStones(int pitNum)
                 throws PitNotFoundException
Gets the number of stones in a specific pit.
Parameters:
pitNum - The pit number
Returns:
The number of stones in the pit
Throws:
PitNotFoundException - If the pit number is invalid
isSideEmpty Link icon
public boolean isSideEmpty(int pitNum)
                    throws PitNotFoundException
Indicates whether one side of the board is empty. An empty side indicates the end of the game. more context: pits 1-6 are on one side of the board while pits 7-12 are on the other side of the board. if this method were called with a 3 as a parameter, it would return true if pits 1-6 were empty, false otherwise.
Parameters:
pitNum - The pit number
Returns:
true if the side of the board that includes the parameter pit number is empty
Throws:
PitNotFoundException
toString Link icon
public String toString()
Overrides:
toString in class Object
~~~

* Prompt for Store.java
~~~
Create this, ignore all "Link icon"

Constructor Details Link icon
Store Link icon
public Store()
Initializes a new store.
Method Details Link icon
setOwner Link icon
public void setOwner(Player player)
Sets the owner of the store.
Parameters:
player - The owner of the store
getOwner Link icon
public Player getOwner()
Gets the owner of the store.
Returns:
The owner of the store
addStones Link icon
public void addStones(int amount)
Adds stones to the store.
Parameters:
amount - The number of stones to add
getTotalStones Link icon
public int getTotalStones()
Gets the total number of stones in the store.
Returns:
The total number of stones in the store
emptyStore Link icon
public int emptyStore()
Empties the store and returns the number of stones that were in it.
Returns:
The number of stones in the store
toString Link icon
public String toString()
Overrides:
toString in class Object
~~~

* Prompt for Player.java
~~~
Create this, ignore all "Link icon"

Constructor Details Link icon
Player Link icon
public Player()
Initializes a new player.
Player Link icon
public Player(String name)
Initializes a new player with a name.
Parameters:
name - The player's name
Method Details Link icon
getName Link icon
public String getName()
Gets the name of the player.
Returns:
The player's name
setName Link icon
public void setName(String name)
Sets the player's name.
Parameters:
name - The player's name
getStore Link icon
public Store getStore()
Gets the player's store where they collect stones.
Returns:
The player's store
getStoreCount Link icon
public int getStoreCount()
Gets the cound of the number of stones in the player's store where they collect stones.
Returns:
The count of stones in the player's store
setStore Link icon
public void setStore(Store store)
Sets the player's store.
Parameters:
store - The player's store
toString Link icon
public String toString()
Overrides:
toString in class Object
~~~

* Prompt for Pit.java
~~~
Create this, ignore all "Link icon"

Constructor Details Link icon
Pit Link icon
public Pit()
Initializes a new pit.
Method Details Link icon
getStoneCount Link icon
public int getStoneCount()
Gets the number of stones in the pit.
Returns:
The number of stones in the pit
addStone Link icon
public void addStone()
Adds a stone to the pit.
removeStones Link icon
public int removeStones()
Removes and returns the stones from the pit.
Returns:
The number of stones removed from the pit
toString Link icon
public String toString()
Overrides:
toString in class Object
~~~

* Prompt for MancalaGame.java
~~~
Create this, ignore all "Link icon"

Constructor Details Link icon
MancalaGame Link icon
public MancalaGame()
Initializes a new Mancala game.
Method Details Link icon
setPlayers Link icon
public void setPlayers(Player onePlayer,
 Player twoPlayer)
Sets the players for the game.
Parameters:
onePlayer - Player one
twoPlayer - Player two
getPlayers Link icon
public ArrayList<Player> getPlayers()
Gets the players for the game.
Returns:
An ArrayList of the players in the game
getCurrentPlayer Link icon
public Player getCurrentPlayer()
Gets the current player.
Returns:
The current player
setCurrentPlayer Link icon
public void setCurrentPlayer(Player player)
sets the current player
setBoard Link icon
public void setBoard(Board theBoard)
Sets the board for the game.
Parameters:
theBoard - Board
getBoard Link icon
public Board getBoard()
Gets the board for the game.
Returns:
the Board for the game
getNumStones Link icon
public int getNumStones(int pitNum)
                 throws PitNotFoundException
Gets the number of stones in a specific pit.
Parameters:
pitNum - The pit number
Returns:
The number of stones in the pit
Throws:
PitNotFoundException - If the pit number is invalid
move Link icon
public int move(int startPit)
         throws InvalidMoveException
Makes a move for the current player.
Parameters:
startPit - The pit from which to start the move
Returns:
the total number of stones remaining in the players side pits
Throws:
InvalidMoveException - If the move is invalid
IllegalStateException - If the player is not valid
getStoreCount Link icon
public int getStoreCount(Player player)
                  throws NoSuchPlayerException
Gets the total number of stones in a player's store.
Parameters:
player - The player
Returns:
The total number of stones in the player's store
Throws:
NoSuchPlayerException - If the player is not found
getWinner Link icon
public Player getWinner()
                 throws GameNotOverException
Gets the winner of the game.
Returns:
The winning player or null for a tie
Throws:
GameNotOverException - If the game is not over yet
isGameOver Link icon
public boolean isGameOver()
Checks if the game is over.
Returns:
True if the game is over, false otherwise
startNewGame Link icon
public void startNewGame()
Starts a new game by resetting the board.
toString Link icon
public String toString()
Generates a string representation of the game.
Overrides:
toString in class Object
Returns:
The string representation of the game and board
~~~

* Prompt for Exceptions
~~~
I will list a bunch of exception classes that need to be created. Create them for me.

Exception1:
java.lang.Object
java.lang.Throwable
java.lang.Exception
mancala.GameNotOverException
All Implemented Interfaces:
Serializable
public class GameNotOverException
extends Exception
See Also:
Serialized Form
Constructor Summary Link icon
Constructors
Constructor
Description
GameNotOverException()
 
Method Summary Link icon
Methods inherited from class java.lang.Throwable Link icon
addSuppressed, fillInStackTrace, getCause, getLocalizedMessage, getMessage, getStackTrace, getSuppressed, initCause, printStackTrace, printStackTrace, printStackTrace, setStackTrace, toString
Methods inherited from class java.lang.Object Link icon
clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait
Constructor Details Link icon
GameNotOverException Link icon
public GameNotOverException()

Exception2:
Package mancala
Class InvalidMoveException
java.lang.Object
java.lang.Throwable
java.lang.Exception
mancala.InvalidMoveException
All Implemented Interfaces:
Serializable
public class InvalidMoveException
extends Exception
See Also:
Serialized Form
Constructor Summary Link icon
Constructors
Constructor
Description
InvalidMoveException()
 
Method Summary Link icon
Methods inherited from class java.lang.Throwable Link icon
addSuppressed, fillInStackTrace, getCause, getLocalizedMessage, getMessage, getStackTrace, getSuppressed, initCause, printStackTrace, printStackTrace, printStackTrace, setStackTrace, toString
Methods inherited from class java.lang.Object Link icon
clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait
Constructor Details Link icon
InvalidMoveException Link icon
public InvalidMoveException()

Exception3:
Package mancala
Class NoSuchPlayerException
java.lang.Object
java.lang.Throwable
java.lang.Exception
mancala.NoSuchPlayerException
All Implemented Interfaces:
Serializable
public class NoSuchPlayerException
extends Exception
See Also:
Serialized Form
Constructor Summary Link icon
Constructors
Constructor
Description
NoSuchPlayerException()
 
Method Summary Link icon
Methods inherited from class java.lang.Throwable Link icon
addSuppressed, fillInStackTrace, getCause, getLocalizedMessage, getMessage, getStackTrace, getSuppressed, initCause, printStackTrace, printStackTrace, printStackTrace, setStackTrace, toString
Methods inherited from class java.lang.Object Link icon
clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait
Constructor Details Link icon
NoSuchPlayerException Link icon
public NoSuchPlayerException()

Exception4:
Package mancala
Class PitNotFoundException
java.lang.Object
java.lang.Throwable
java.lang.Exception
mancala.PitNotFoundException
All Implemented Interfaces:
Serializable
public class PitNotFoundException
extends Exception
See Also:
Serialized Form
Constructor Summary Link icon
Constructors
Constructor
Description
PitNotFoundException()
 
Method Summary Link icon
Methods inherited from class java.lang.Throwable Link icon
addSuppressed, fillInStackTrace, getCause, getLocalizedMessage, getMessage, getStackTrace, getSuppressed, initCause, printStackTrace, printStackTrace, printStackTrace, setStackTrace, toString
Methods inherited from class java.lang.Object Link icon
clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait
Constructor Details Link icon
PitNotFoundException Link icon
public PitNotFoundException()
~~~



