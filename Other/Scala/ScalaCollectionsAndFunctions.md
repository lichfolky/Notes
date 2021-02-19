## Collections

+ calling ` Vector(..., ..., ...)` it's like calling `Vector.apply(1, 2, 3)`
+ no raw type, but type parameters `Vector[Int](1, 2, 3)` can be inferred

+ **++** → Concatenates two collections  
+ **toSeq, toSet, etc.** → Convert between collection types  
+ **isEmpty** and **size** → Provide size information  
+ **contains** → Tests whether a collection contains an element  
+ **head** → Returns the first element, last the last  
+ **tail** → Returns all elements except for the first, init vice versa  
+ **take n** → Returns the first n elements, drop n vice versa  
+ **zip** → Combines corresponding elements in pairs
+ **groupBy** → Partitions a collection into a map of collections

+ ` Set(..., ..., ...)`
no duplicates
> numbers + 4  

+ ` Seq(..., ..., ...)`

> val numbers = Seq(1, 2, 3)  
> numbers(0)  
> numbers :+ 4  
> 0 +: numbers  
> Seq(1, 2, 1, 3).distinct  

+ Tuple1, Tuple2, Tuple3... Tuple33
finite heterogeneous containers,  
Tuple fields are named `_1`, `_2`  
Tuple2s (Pairs) can be created with the -> operator  
`1 -> "a"`

#### Maps
unique keys!

> val map = Map(1 -`> "a", 2 -`> "b")  
> map(1) #returns 'a'
> map.getOrElse(9, "z") #returns 'z'  

by default collections are immutable

higher order
map takes a function which takes an element of the collection and returns some value
> numbers.map(number => number + 1)

function literals and `_`

Function values are objects



#### Functions

addOne = (n: Int) => n + 1

scala has Function0 to Function22
All function types define an apply method


##### method to function

`val addOneFun: Int => Int = addOne`  
the method gets lifted into a function

##### Higher order functions
##### Map


> val languages = Vector("Scala", "Java", "JavaScript")
> languages.map(language => language.toLowerCase)


##### flatmap
> Seq("Now is", "the time").map(s => s.split(" "))  
> Seq("Now is", "the time").flatMap(s => s.split(" "))

in the first collection of tuples in the second each element is expanded into the result

##### filter and filterNot
unary function parameter that returns a boolean


#### Unclear
function literals and `_`
Scala has first-class functions
Function values are objects
trait
