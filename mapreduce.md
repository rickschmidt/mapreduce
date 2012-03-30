#MapReduce

##Highlights
* MapReduce is an implementation for processing large data sets and was created at Google.
* MapReduce solves the problem engineers have of automatically parallelizing basic computations over large datasets. 
* It is made up of two basic concepts from the world of functional programming.

    1)Map: Where the same function is applied to ever piece of data in a set.
    2)Reduce: Intermediate values from the map operation are reduced into a smaller set.
    
        *These functions inherently make the solution easy to implement recursively.*

The implementation of the MapReduce algorithm has made cloud computing possible.  It often provides a straightforward solution to solving many computing problems that naturally arise when trying to implement features in a cloud based product.

As the web continues to change everyday the use cases for MapReduce are also changing.  The social web has presented its own set of problems where MapReduce is not optimal.  As the demand for implementing new user features slows the rise in demand for computational power to work with "Big Data" increases.



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

* Hadoop is largely supported by competing companies in order to replicate googles success in distributed cloud computing.


##Cloud Computing
The benefits of cloud computing are obvious to developers as are most of the drawbacks.  Skipping the benefits most developers can instantly point out that when all of your data is in the cloud you are opening yourself up to privacy violations and intellectual theft.  The host may not make there intentions of what they intend to do with your data.  If there is no intent in ever trying to profit off of an individuals data they may not take the steps necessary to secure their servers such as limiting access to employees and applying patches.  

###Real Time Web
Distributed cloud computing is not the holy grail of information science and architecture as it would appear.  As the web has recently become more social there is a need to process data in real time.  The "real time web" has it has been dubbed is one in which social interactions form networks around data.  If your google you want to present this data instantly to your users. Users benefit from having the freshest content available; Google benefits from being able to advertise to you precisely when you are most interested in making a purchase.  

###Reduction in utility of MapReduce from a consumers perspecitve
The distributed model of MapReduce is costly in terms of time.  Yes very interesting statistics can be interpolated from massaging a data set but in order to adapt a real time solution is needed.  Google has begun to steer away from MapReduce in several of its products including search. An [example](http://www.theregister.co.uk/2010/09/09/google_caffeine_explained/ )     

###Applications of MapReduce in light of the Real Time Web
The end is far from near for MapReduce implementations.  At the same time the "real time web" is growing so is "big data".  Projects qualify as "big data" when the collections become so enormous that they require specialists in data taxonomy, warehousing, and analysis.  Big data projects promise great utility.  

####Metagenomics
In bioinformatics there is a field called metagenomics.  Metagenomics is an area of study where the genomes of an entire community are studied at once.  The data to be analyzed is often from organisms that practically can not be studied individually. Imagine all of the microbes in a soil sample, oceanic water, or your digestive tract.  Modern sequencing has made it possible to gather all of this information cheaply and quickly. It is valuable except few people have developed few tools to devise any meaning.  

####How MapReduce can be used in Metagenomics
These are the kinds of problems that MapReduce are good for and will continue to work well with.  For example mapping similar DNA sequences in a metagenomic set  
by there taxonomy and then taking a count is an extremely straightforward, useful, and easy to code implementation of map reduce.  The number of these operations will overwhelm a desktop computer.  The taxonomical identification using a BLAST search is relatively time consuming when the the numbers of sequences that need to be identified is so large.  

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
lorem
Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.


Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.



