# README
To build use:
`mvn package`

To run use:
`./run`

This will give you a barebones REPL, where you can enter text and you will be output at most 5 suggestions sorted alphabetically.

To start the server use:
`./run --gui [--port=<port>]`

## Project Details
* REPL Loop with 4 commands: 
    * add: adds two numbers
    * subtract: subtracts two numbers
    * stars: loads in the specified star CSV data sheet
    * naive_neighbors: returns the closest k neighbors to either given coordinates
or a specific star name
## Design Choices
* Different REPL commands are checked with if/if else/else statements to identify
and execute the correct command
* If any error arises, or if any invalid inputs are entered, an error is 
printed to the REPL console
* When loading CSV data from the "stars" command, it is stored in a 2D array
to represent the rows of star data and the columns of their attributes
  * Within this array, is a sixth column, which is used to store the distance
    from the given location the corresponding star is
  * This column is populated when "naive_neighbors" command is called
* There are four unique helper methods for this REPL loop:
    * distanceFormula
      * calculates distance between two 3D points; called in fillDistances
    * fillDistances
      * fill the distance column in the CSV data 2D array by calculating the distance from each star to the
      given point
    * sortCSVData
      * sorts 2D CSV array by the distance column, with the nearest stars at the top
    * printKNearest
        * prints the first k entires in the sorted CSV data array 
## Errors / Bugs
* There are no known errors/bugs in this project