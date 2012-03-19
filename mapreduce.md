#MapReduce

##Highlights
* MapReduce is an implementation for processing large data sets and was created at Google.
* MapReduce solves the problem engineers have of automatically parallelizing basic computations over large datasets. 
* It is made up of two basic concepts from the world of functional programming.

    1)Map: Where the same function is applied to ever piece of data in a set.
    2)Reduce: Intermediate values from the map operation are reduced into a smaller set.
    
        *These functions inherently make the solution easy to implement recursively.*

##Necessity
* The need for MapReduce software stems from the fact that google runs on cheap commodity hardware housed in large data centers all of the world running Linux.
* Google had already solved the problem of how to access data spanning many disks over many continents with the google file system (GFS).
* In order to make sure every engineer can be productive with a large data set there needs to be away to massively parallelize computations.


##Implementation
* MapReduce is implemented in C++


##Example of Mapping and Reducing
* The map function takes a data set and applies the same function to every item in the data set returning a new data set of the same length.
* If functional programming sounds strange it shouldn't. You have been doing it since your basic math courses.
    * Take the mathematical function f(x)=x^2 for example.  It is a function that takes every element passed into it and applies the same operation resulting in a new data set of the same length.
* Reducing is when the result of a map function is reduced in to a smaller data set.
    * If our goal was to find the sum of the squares of our dataset {1..10} using the previous function we would simply take the result of the map and add every value.  
    * A common implementation of this in functional programming would be to apply a fold() operation across a dataset.  A fold operation is a handy way of combining both the map and reduction in one step. 
    
##Folding
* A map and reduce function used together is generally called a fold. Functional programming languages generally feature both a left and right fold operation.  The fold operation works by taking all of the values in a set and applying the same function to each.  For each point the fold operation builds from the intermediate values. 

    Consider the fold operation in scala:
    
    `A list with the intergers is 1,2,3 is created and the foldLeft operation is applied to it.  FoldLeft has an initial value of 0 and the loop contains the local variables named              accumulator and current.`
    
    `scala> List(1,2,3).foldLeft(0){(accumulator,current)=>current+accumulator}
     res0: Int = 6`
    
## Example of use at google
* In the paper that google describes MapReduce they state that one use would be to calculate word occurrences over large data sets.  The map function builds up key value pairs matching the word with a document number that the word appeared on.  The result is a large hash map.  The reduction happens when the values of each pair are counted to determine the total number of occurrences. This basic problem has a wide number of uses such as determining breaking news items, determining trends, and spam keyword detection.


## Why is MapReduce a good idea for large datasets?
* Working with extremely large datasets requires massively parallel computation.  The data itself is largely independent or can at least be divided as such.   
## Implementations of the MapReduce Pattern
###Hadoop
* Hadoop is a project from the Apache foundation
* Hadoop allows the user to write map and reduce functions that can distribute the workload computing large datasets over thousands of nodes built from commodity hardware.  

* Hadoop is 


