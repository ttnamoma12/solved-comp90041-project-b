Download Link: https://assignmentchef.com/product/solved-comp90041-project-b
<br>
This project (Project B), and the next one (Project C), will continue with the same theme introduced in Project A – namely, an implementation of the game of Nim. Please refer to the Project A specification for a description of the game and its rules.

In Project A, a simple Java program was created to handle Nim’s core game play mechanics. In the next two projects, the objective is to design and implement a more complete version of Nim, making full use of Java’s object-oriented paradigm.

<strong>Key Knowledge Points Covered in Project B:</strong>

<ol>

 <li>Design of the class structure for the project requires the knowledge of UML diagrams (taught inWeek 5).</li>

 <li>Implementation requires understanding of <em>Classes </em>(taught in Week 4 – 6) and <em>Arrays </em>(taught in Week 7).</li>

</ol>

You may start working on the project right away except the array part. If you would like to start to work on the array part before week 7, you may learn basics of arrays by yourself.

<h1>2      Requirements</h1>

In this project, we introduce a third class NimGame. The game playing process is delegated from Nimsys to NimGame. Since only one game will be active at any given time, only a single NimGame instance is required at any time by Nimsys. Nimsys should also maintain a collection of players. Initially, this collection will be empty – players will need to be added in order to play a game.

A NimGame instance needs to have the following information associated with it:

<ul>

 <li>The current stone count</li>

 <li>An upper bound on stone removal</li>

 <li>Two players</li>

</ul>

The system should allow for games of Nim to be played, with the rules of the game, and the players, specified by the user.

A player, as described by the NimPlayer class, needs to have the following information associated with it:

<ul>

 <li>A username</li>

 <li>A given name</li>

 <li>A family name</li>

 <li>Number of games played</li>

 <li>Number of games won</li>

</ul>

The system should allow players to be added. It should also allow for players to be deleted, or for their details to be edited. Players should not be able to directly edit their game statistics, although they should be able to reset them.

The system is a text based interactive program that reads and executes commands from standard input (the keyboard) until an ‘exit’ command is issued, which will terminate the program. If a command produces output, it should be printed to standard output (the terminal).

When Nimsys is first executed, it should display a welcome message, <strong>followed by a blank line</strong>. A command prompt (a ‘dollar’ sign, i.e., $) should then be displayed.

In following description, all command line displays are put in a box. This is only for easier understanding the format. <strong>The box should NOT be printed out by your program, only the contents in the box should be printed. </strong>The command prompt is illustrated below:

Welcome to Nim

$

At any given time, the system can be in one of two states – either a game is in progress, or no game is in progress. Hereafter, these will be referred to as the ‘game’ and ‘idle’ states, respectively. (Note: the states are just used to explain the mechanism of Nimsys. You don’t need to create a variable called ‘state’ in your code).

When in the idle state, the system should accept the following commands. These commands are entered at the Nimsys command prompt. If a command produces output, it should be printed immediately below the line where the command was issued. After the command has executed, a new command prompt should be displayed. This new command prompt should be separated from the previous command (and its output, if any) by a single blank line.

<strong>Note that in the syntax descriptions below, a term enclosed in square brackets indicates an optional parameter. The input is assumed to be always </strong><em>valid</em><strong>, but not always </strong><em>correct</em>. Valid input suggests that entered data have the same type of the corresponding variables, e.g., String data are entered for String variables, integer data are entered for int variables. Correct input suggests that the entered data can be correctly processed by the corresponding command, e.g., adding an existing user and removing a nonexistent user are incorrect input. <strong>Unless otherwise stated, you are NOT required to check validness, but you ARE required to check the correctness of the input, as shown in the below examples.</strong>

<ol>

 <li>addplayer – Allows new players to be added to the game. If a player with the given <strong>username </strong>already exists, the system should indicate this, as shown in the example execution.</li>

</ol>

Syntax: addplayer username,family_name,given_name Example Execution:

<ul>

 <li>add a new user:</li>

</ul>

$addplayer lskywalker,Skywalker,Luke

$

<ul>

 <li>add a user who already exists in the system</li>

</ul>

$addplayer lskywalker,Skywalker,Luke The player already exists.

$

<ol start="2">

 <li>removeplayer – Allows players to be removed from the game. The username of the player to beremoved is given as an argument to the command. If no username is given, the command should remove all players, but in this case, it should display a confirmation question first. If a username for a non-existent player is given, the system should indicate that the player does not exist. The format of these messages is illustrated in the example execution below.</li>

</ol>

Syntax: removeplayer [username] Example Execution:

<ul>

 <li>remove a nonexistent user</li>

</ul>

$removeplayer lskyrunner The player does not exist.

$

<ul>

 <li>remove a user</li>

</ul>

$removeplayer lskywalker

$

<ul>

 <li>remove all users</li>

</ul>

$removeplayer Are you sure you want to remove all players? (y/n) y $

<ol start="3">

 <li>editplayer – Allows player details to be edited. Note that the player’s username cannot be changedafter the player is created. If a username for a non-existent player is given, the system should indicate that the player does not exist, as illustrated in the example execution.</li>

</ol>

Syntax: editplayer username,new_family_name,new_given_name Example Execution:

<ul>

 <li>edit a nonexistent user</li>

</ul>

$editplayer lskyrunner,Skywalker,Laurence The player does not exist.

$

<ul>

 <li>edit a user</li>

</ul>

$editplayer lskywalker,Skywalker,Laurence

$

<ol start="4">

 <li>resetstats – Allows player statistics to be reset. The username of the player whose statistics are tobe reset is given as an argument to the command. If no username is given, the command should reset all player statistics, but as with the ‘removeplayer’ command, a confirmation question should be displayed in this case. If a username for a non-existent player is given, the system should indicate that the player does not exist, as illustrated in the example execution.</li>

</ol>

Syntax: resetstats [username] Example Execution:

<ul>

 <li>reset a nonexistent user</li>

</ul>

$resetstats lskyrunner The player does not exist.

$

<ul>

 <li>reset a user</li>

</ul>

$resetstats lskywalker

$

<ul>

 <li>reset all users</li>

</ul>

$resetstats Are you sure you want to reset all player statistics? (y/n) y $

<ol start="5">

 <li>displayplayer – Displays player information. The username of the player whose information is tobe displayed is given as an argument to the command. If no username is given, the command should display information for all players, ordered by username alphabetically. If a username for a non-existent player is given, the system should indicate that the player does not exist, as illustrated in the example execution. <strong>Please note when displaying player, the sequence of syntax is </strong>username,givenname,familyname,number of games played,number of games won.</li>

</ol>

Syntax: displayplayer [username] Example Execution:

<ul>

 <li>display a nonexistent user</li>

</ul>

$displayplayer lskyrunner The player does not exist.

$

<ul>

 <li>display a user</li>

</ul>

$displayplayer lskywalker lskywalker,Luke,Skywalker,3 games,3 wins

$

<ul>

 <li>display all users</li>

</ul>

$displayplayer dvader,Darth,Vader,7 games,1 wins hsolo,Han,Solo,4 games,3 wins lskywalker,Luke,Skywalker,3 games,3 wins $

<ol start="6">

 <li>rankings – Outputs a list of player rankings. There are three columns displayed. The first columndisplays percentage wins or winning ratio, the second column displays the number of games played, and the final column shows the player’s full name, that is, first name followed by last name. This command takes the sort order as an argument. The sort order is desc or descending by default. That is, if no argument or desc is provided, the program should rank the players by the percentage of games they have won in descending order, i.e., players with highest percentage wins should be displayed first. If the user provides asc as an argument, the players should be ranked by the percentage of games they have won in ascending order. Round the percentages to the nearest integer value. However, you should use the exact values of winning ratios when comparing and sorting two users’ winning ratios. Ties should be resolved by sorting on usernames alphabetically. Only the first 10 players should be displayed, if there are more than 10. The output should be formatted according to the example below. For the purposes of formatting the output, you may assume that no player has played more than 99 games. Note that the vertical lines need to be aligned, with a single space appearing on either side. This means that in the first column you <strong>must </strong>have 5 characters consisting of a number, ’%’, and spaces. The first column must be left-justified.</li>

</ol>

Syntax: rankings [asc|desc] Example Execution:

<ul>

 <li>rank all users in descending order</li>

</ul>

$rankings

100% | 03 games | Luke Skywalker

75% | 04 games | Han Solo

14% | 07 games | Darth Vader

$

<ul>

 <li>rank all users in descending order</li>

</ul>

$rankings desc

100% | 03 games | Luke Skywalker

75% | 04 games | Han Solo

14% | 07 games | Darth Vader

$

<ul>

 <li>rank all users in ascending order</li>

</ul>

$rankings asc

14% | 07 games | Darth Vader

75% | 04 games | Han Solo

100% | 03 games | Luke Skywalker

$

<ol start="7">

 <li>startgame – Creates and commences a game of Nim. The game’s rules, and the usernames ofthe two players, are provided as arguments. You may assume that the initial stones and upperbound arguments are valid <strong>and correct</strong>. However, if at least one (i.e. one or two) of the usernames doesn’t correspond to an actual player, the system should indicate this by the output “One of the players does not exist.”, and the game should not commence.</li>

</ol>

Otherwise, the ‘startgame’ command will commence a game, i.e., after executing it, the system is in the game state. When a game is in progress, the system should proceed according to the game play mechanics discussed in Project A, i.e., players should, in an alternating fashion, be asked to enter the number of stones they would like to remove, with the game state being updated accordingly. In this project, bounds on stone removal should be enforced. That is, players should only be allowed to remove between 1 and N stones inclusive, where N is the upper bound or the number of stones remaining, whichever is smaller. Once all the stones are gone, a winner should be announced, and the statistics for the two players should be updated accordingly. The system should then return to the idle state, and a command prompt should be displayed again.

Syntax: startgame initialstones,upperbound,username1,username2 Example Execution:

<ul>

 <li>start game with a non-existent user</li>

</ul>

$startgame 10,3,lskyrunner,hsolo One of the players does not exist.

$

<ul>

 <li>start a game</li>

</ul>

$startgame 10,3,lskywalker,hsolo

Initial stone count: 10

Maximum stone removal: 3

Player 1: Luke Skywalker

Player 2: Han Solo

10 stones left: * * * * * * * * * * Luke’s turn – remove how many?

3

7 stones left: * * * * * * * Han’s turn – remove how many?

4 Invalid move. You must remove between 1 and 3 stones.

7 stones left: * * * * * * * Han’s turn – remove how many?

3

4 stones left: * * * * Luke’s turn – remove how many?

3

1 stones left: * Han’s turn – remove how many?

<ul>

 <li>Invalid move. You must remove between 1 and 1 stones.</li>

 <li>stones left: * Han’s turn – remove how many?</li>

</ul>

1

Game Over Luke Skywalker wins!

$

<ol start="8">

 <li>exit – Exits the Nimsys program.</li>

</ol>

Syntax: exit

<strong>Note that before you call the exit method in Java using </strong>System.exit(0); <strong>, you must print a blank line first.</strong>

(a) exit the system

$exit

As was described earlier, it is important that your design makes good use of object-oriented design principles. This is particularly relevant when it comes to implementing the actual gameplay. <strong>In a real game, game proceeds with each player performing the action of removing some number of stones from the game. Your design should reflect this structure.</strong>

Don’t worry about changing your output for singular/plural entities. Simply always use plural entities, i.e., you should output ‘1 games’, ‘1 wins’, ‘1 stones’, etc.

<h1>Checklist For Solution</h1>

<ul>

 <li><strong>Error handling issues</strong></li>

</ul>

Only the following errors need to be handled (you may choose to handle more if you wish):  Adding a new player with an existing username.

Error message: The player already exists.

Follow-up operation: Print ‘$’ and prompt for user input again.  Removing a player with a non-existing username.

Error message: The player does not exist.

Follow-up operation: Print ‘$’ and prompt for user input again.  Resetting the statistics of a player with a non-existing username.

Error message: The player does not exist.

Follow-up operation: Print ‘$’ and prompt for user input again.  Displaying a player with a non-existing username.

Error message: The player does not exist.

Follow-up operation: Print ‘$’ and prompt for user input again.  Starting a game where at least one of the player’s username does not exist.

Error message: One of the players does not exist.

Follow-up operation: Print ‘$’ and prompt for user input again.

Removing stone outside of the range [1, stoneRemovalUpperBound], where stoneRemovalUpperBound is the maximum number of stones allowed to be removed in one turn.

Error message: Invalid move. You must remove between 1 and stoneRemovalUpperBound stones (do not need to consider the singular or plural form of “stone”).

Follow-up operation: Prompt for the same player to remove stone again.

<ul>

 <li><strong>Blank line and whitespace related issues. </strong>Make sure that between the output of last command (including indication for nonexistent users, confirmation for all-user operations, display results, and game results) and the next command prompt, there is one blank line.</li>

</ul>

Make sure that there is a whitespace between (y/n) and Are you sure… sentence.  Make sure that there is NO whitespace after each comma, e.g., when displaying users, it should be davader,Darth instead of davader, Darth.

Make sure that in game state, there is one blank line before the Initial stone count… and one blank line after the Player 2:….

Make sure that in game state, if a user input an invalid move, there is one blank line between the user-input move and the indication sentence Invalid move….

Make sure that an extra blank line is printed out before calling System.exit(0); when command exit is entered.

<ul>

 <li><strong>Ranking display related issues. </strong>Make sure that the ranking is in a descending order of winning ratio by default or when “desc” is provided as an argument.</li>

</ul>

Make sure that the ranking is in a ascending order of winning ratio when “asc” is provided as an argument.

Make sure that winning ratio is rounded to the nearest integer value when displaying the winning ratio. However, please note that exact values are still used when comparing and sorting two users winning ratios.

Make sure that users with the same winning ratio are sorted according to the alphabetical order of the user name irrespective of the argument supplied to the rankings command, e.g., if username ethan and username tom have the same winning ratio, you should rank ethan the higher place.

Make sure that the first and the second column strictly have 5 and 10 characters, respectively.

<ul>

 <li><strong>Display player related issues.</strong></li>

</ul>

Make sure that the displayed list is sorted in an alphabetical order of the username.

<ul>

 <li><strong>Game related issues.</strong></li>

</ul>

Make sure to correctly update the statistics for players when a game ends.

Make sure to check valid move by comparing the move to the smaller one between the current number of stones and the upper bound for one move.

Make sure that after an invalid move, it is still the turn of the player who made the invalid move.

<ul>

 <li><strong>Command line prompt related issues. </strong>Make sure that the command prompt appears again after each command is issued (except the exit command).</li>

</ul>

Make sure that only one command prompt is displayed after a game is over and the system returns to the idle state.

<ul>

 <li><strong>Other issues. </strong>The maximum number of players can be set as 100.</li>

</ul>

The branching statement switch may not support Strings on the submission server.  The boxes enclosing the above example executions are NOT to be printed out, they are just for better illustration.