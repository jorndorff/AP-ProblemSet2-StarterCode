# Overview

This project contains several classes used to practice writing object-oriented code and solve real-world problems. Filenames and descriptions are outlined below in the problems subsections. It also contains test cases in the Tests.java file that test all problem classes.

# Problems

## Complex Number

Design a `Complex` class that represents a complex number.

### Fields

* double real
* double imag

### Constructors

* default constructor sets the complex number to 1
* two argument constructor takes a real and imaginary part

### Methods

* accessors and modifiers
* modulus -- returns the "length" of the number in the complex plane
* angle -- returns the angle in radians between the number and the positive x axis
* toString -- returns the form "a + ib"

## Qubit

Design a class called `Qubit` to represent a quantum bit in a quantum computer.

### Fields

* Complex down
* Complex up

### Constructors

* default constructor sets down to 0 and up to 1
* two argument constructor takes two Complex numbers

### Methods

* accessors and modifiers
* measure -- returns either “up” or “down” probabilistically. The probability of measusring an "up" state is |up|^2 and likewise with down.
* validate -- returns whether the state is normalized. Normalized means that |up|^2 + |down|^2 = 1
* toString -- returns the form "(a + ib)|up> + (c + id)|down>:

## Humans

Design `Human`, `Woman`, and `Man` classes in such a way that the following code compiles and runs as expected. You  are not required to add other features to your classes. Consider whether the human class should be `abstract` here.

``` java
import java.util.ArrayList
  
  public class HumanRunner {
    ArrayList<Human> arr = new ArrayList<Human>();
    arr.add(new Man());
    arr.add(new Woman());
    arr.add(new Man());
    arr.get(0).eat("salad");
    arr.get(1).eat("steak");
    
    // The following line must generate a compiler error.
    // arr.add(new Human());
  }
```

## Songs

Design 2 classes, one called `Top10Songs` and one called `Song`. The Song class should have 2 private fields, artist and title, and accessors for each variable. It should also have a Constructor that takes in 2 Strings to initialize the class fields.  

Top10Songs will hold 10 Song objects in an array. It's only constructor should take no args and initialize the array (to all null)

### Top10Songs Methods

add method that takes in a Song and returns a boolean.  Places song in first available slot and returns true.  If all slots are taken, does not place Song and returns false.

add method that takes in a song and an index and returns a Song.  This method should place the parameter Song at the given index and then bump all other songs down accordingly. The last song, which gets “bumped” from the list, should be returned.

toString method that return a String representation of the list that is numbered with each Song on its own line.

## Poems

Define an abstract class Poem with no fields.

### Poem Methods

* public abstract int numLines() - returns the number of lines in the poem.
* public abstract int getSyllables(int k) - returns the number of syllables on the k-th line.
* public abstract void printRhythm() - shows the rhythm of the poem. For example, a haiku has 3 lines of 5, 7, and 5 syllables, so for a haiku the printRhythm method should print:

```
ta-ta-ta-ta-ta
ta-ta-ta-ta-ta-ta-ta
ta-ta-ta-ta-ta
```

### Concrete Classes

A limerick has 5 lines of 9, 9, 6, 6, and 9 syllables. Define Haiku and Limerick subclasses of Poem, and make the printRhythm method in each of them work without duplicating any code.

 

## Transportation Safety (Optional -- Not Graded)

Please create the classes according to this UML and use the Runner class using the specifications below: (Note: not all has-a relationships are shown in this UML) 

 ![Screen Shot 2017-02-28 at 11.16.36 AM.png](https://lh4.googleusercontent.com/8u5TcCdIeAHmKBRX_u_7z_yE0CT7wytjZxAHdVM7t3ZpEhuVUnVa1jGL46Pg8D1p6cnjG61YXGJTvMIGzuMwjRT-oq2ze88VpgG7g7kM6Vtdcx2eZgQJ_xwEMdcjFGK8T0e-9xg)

Safety interface MUST have the following:

```java
public interface Safety
{
    public static final int BUSCAPACITY = 30;
    public static final int TRAINCAPACITY = 300;
    public static final int PLANECAPACITY = 150;
    public static final int HELICOPTERCAPACITY = 5;
    public static final int SHIPCAPACITY = 100;
    public static final int BOATCAPACITY = 20;
    
    boolean checkSafety();
}



```

Transport abstract class must have the following fields:

```java
private int numOfTicketsSold; 
private double farePerPerson;
private boolean fireExtinguisher;
```

And a method name `revenue()` that returns the double type. Note: Revenue is calculated by how many tickets has been sold times the price per ticket.

WaterSafety abstract class must have the following fields:

```java
private int numberOfLifeJacket;
private int numberOfLifeBoat;
private int capacityOfLifeBoat;
```

To pass safety check for the following transportation methods, meaning checkSafety() method should return true only if:

**Bus:** has a fire extinguisher and the bus is filled within its capacity, meaning the number of tickets sold must not exceed its capacity.

**Train:** has a fire extinguisher and the train is filled within its capacity, meaning the number of tickets sold must not exceed its capacity.

**Plane:** has a fire extinguisher, has enough life jackets and lifeboats and the plane is filled within its capacity, meaning the number of tickets sold must not exceed its capacity.

**Helicopter:** has a fire extinguisher, has enough life jackets and lifeboats and the plane is filled within its capacity, meaning the number of tickets sold must not exceed its capacity.

**Ship:** has a fire extinguisher, has enough life jackets and lifeboats and the plane is filled within its capacity, meaning the number of tickets sold must not exceed its capacity.

**Boat:** has a fire extinguisher, has enough life jackets and lifeboats and the plane is filled within its capacity, meaning the number of tickets sold must not exceed its capacity.

**Runner class:**

![Screen Shot 2017-02-28 at 11.18.41 AM.png](https://lh3.googleusercontent.com/wWOKlf5N_SoXMDjkymJ6amVJP26HcadyClL6o4TTlkhRE3f7LYZZQ-G4FeQS2-YlJHZ3WRqAugt5XPnKtbkmLsW8RoFKi9QNtmn4g2lE-HECyL4lIB6hXaN2qGpODgRPWPhNDe4)

## Team

Complete the `Team`, `Game`, and `League` classes that are sketched out in the Team directory.

## Purchasable

Write the `Purchasable` interface which contains 2 methods: cost, which returns an int representing the cost, in cents; and it should contain itemName, which returns the name of the item as a String.

Then write the concrete class `Book` which implements Purchasable. You may implement the two inherited abstract methods any way you want.

## Coin (immutable class)

### Fields    

- int value

### Constructors

- Coin(int v)

### Methods

Because this class is immutable, it does not have any modifiers or methods with side effects.

- int getValue()
- String getName()

## Shopper

### Shopper Fields

* String name
* List<Coin> coins
* List<Purchasable> purchases

### Shopper Constructors

* Shopper(String n)

### Shopper Methods

* int getTotalValue() //Returns the total value (in cents) of all coins that the shopper has
* boolean buy (Purchasable p) //Attempts to add p to list of purchases, assuming that Shopper has enough funds. If they do, also subtract appropriate coins, replace with any necessary change, and return true. For example, if you purchase something for 8 cents and have only a quarter, you should remove the quarter and replace it with a dime, a nickel, and 2 pennies. If the shopper does not have enough money, the method should return false.
* String toString() //Returns string representation of this shopper.
* You may also want an addCoin(Money m) method that will allow you to give money to the shopper for testing purposes.

## Game Board

Create concrete class `Grid`, abstract class`GridItem` which implements Comparable, and concrete class `GamePiece`which extends GridItem. Together they will define a board for a game like checkers or chess.

### Grid Fields

An array of arrays of type GridItem

### Grid Constructors

Grid(int rows, int cols)

Grid(Grid other) //New grid that is a copy of other

### Grid Methods

GridItem place(GridItem item, int row, int col) //Place item at row and col within grid. Return what was there.

GridItem get(int row, int col) //Return item at row and col within grid.

String toString() //Return string representation of grid.

### GridItem Fields

String value

### GridItem Constructors

GridItem(String initVal)

### GridItem Methods

//Accessor for value

String getValue()

class GamePiece extends GridItem


# Grading
| Category      | Points |
| ------------- | ------ |
| Documentation | 2      |
| Functionality | 15     |
| Test Coverage | 3      |

| Deduction | Points |
| --------- | ------ |
|           |        |

Classes, methods, and any other parts of the public interface do not match the required names, they will be graded as if they were not written at all.
