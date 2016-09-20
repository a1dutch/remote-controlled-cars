# Remote Controlled Cars

The purpose of this exercise is to demonstrate TDD and come up with a solution to the problem given below. Working unit tests will be sufficient as a solution, but you may provide a simple user interface to demonstrate your codes capability if you desire.
Cars are placed on a 15 by 15 grid at particular co-ordinates heading north, and the simple commands Left, right and forward are transmitted to them. The commands must be executed and the final position calculated.
The following examples should be used to demonstrate your code:

For the input "5,5:RFLFRFLF"
We should get the position "7,7"

For the input "6,6:FFLFFLFFLFF"
We should get the position "6,6"

For the input "5,5:FLFLFFRFFF"
We should get the position "4,1"

## Design 

The design is kept pretty simple and uses regex to validate the input, it then parses the valid input string into a list of positions.

A position is either a direction change or move forward in the current direction.

This design takes into account invalid input formats and inputs that would put a car outside the grid, e.g. and input of '15,15:FRF' which would end up at 16,16

## Potential Changes

* Moving the parsing logic from the constructor into a parser class, and injecting the parser into the constructor.

* Using a language parser (ANTLR, Grappa, Parboiled, etc...) to parse the input, these generally involve specifying grammar and then parse the input into a model, maybe a bit to heavy weight for the simple format above.

* The grid is currently a fixed size, and has a hard coded regex, if different size grids were required then the regex could be changed to validate decimals and a further check made against the required grid size.   

## Build & Test And Package

```bash
mvnw clean package
```

## Run the example against the built jar

```bash
cd target
java -jar remote-controlled-cars-0.0.1-SNAPSHOT.jar <input>
```
