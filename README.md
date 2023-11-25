# Monopoly
Name: Darshan AbhayKumar
ID: 2020A7PS1214P
Project - Monopoly

Drive Link: https://drive.google.com/drive/folders/1Vl7-5x0zdCA-dvDQqpViOwuZuSEnfL4h?usp=sharing

1> Favour composition over inheritance
In the class Square, we should've used composition over inheritance to define the several ticket squares because when inheritance is used , encapsulation becomes less effective as the subclass needs to access the variables of the superclass and thus encapsulation needs to be broken. Ex: The private variables, in our case int cost, int rent and String name, had to be declared protected instead of private making it it more volatile.

Additionally, since java doesn't support multiple inheritance and if we had to define a new kind of ticket which has properties of both ticketsquare and specialsquare, we wouldn't be able to do so.

2> Encapsulate what varies
In each of the cases when the Player does not have enough money and the game ends, there are several lines of code for the threads to stop functioning and to display the errors. Since I had to make several changes to make sure the game stops running. I copy pasted my code a many times to achieve the same. But instead if I had encapsulated the code inside a method and called the method everytime the player does not have enough money, I could've achieved the same but in much lesser time and cleaner looking code by just making changes inside the method.

3> Classes should be open for extention and closed for modification
If we wanted to add an additional double rent attribute to the game then we have to change the inheritance in the TicketSqaure class as only CityTickets can have double rent when all the cards of the same color are collected. This will make Utility and Station tickets also have this double rent attribute as they are inheriting the TicketSquare class. Solution to this would be to use interfaces to keep only the attributes which we need to be common making the classes more loosely coupled as well.

4> Depend on abstraction, do not depend on concrete classes
In the stack class, both the community chest and chance squares have the same cards but if we wanted to them to have a stack of cards each then declaring Stack class as an abstract class would've enabled us to code it much easily because we could've declared the Stacks class as abstract(interface) and have had Community chest and Chance as seperate classes which implement the Stacks class. But since we have Stacks set as a concrete class we are unable to do so.


Design Pattern:

When we are updating the money of the players we are calling each player's object every turn to update its money. Each player object has more information than it requires as all it needs is the current money of the player and add the rent collected in that turn. Additionally, it violated the OOP principle of coding to an interface not implementation as we are using concrete classes instead of interfaces to share data. 
To solve this, we can use Observer pattern:

	a> By using observer pattern we can have an Observer interface with a abstract notify method which is implemented by each player object (This also lets us use the Runnable interface as we can implement multiple interfaces). 

	b> There is a Subject interface which will receive any payment made by a player.

	c> The Subject interface will notify all the players of the change and the corresponding player will update their money






Additional Software used - Swing, WindowBuilder
Test cases run: Input can be 2, 3, 4 players

How to use code:
1> Run the program

2> In the menu you can choose either Help or Play. To play the game click on Play.

3> A new popup with the board and a start button will be displayed. 

4> Click on start. It will ask for input in console. Input any number from 2 to 4

5> Code will run until you exit the program or if a Player runs out of money.
