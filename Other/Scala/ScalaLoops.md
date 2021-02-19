## Loops


### for expression

> for (seq) yield expr

### Generators

> for (n <- Vector(1, 2, 3)) yield n + 1
> for (n <- Set(1, 2, 3)) yield "#" + n

the first generated element defines the result type

#### Multiple Generators

> for {  
>   n <- 1 to 3  
>   m <- 1 to n  
> } yield n * m  


### Filters

> for {  
>   n <- 1 to 3 if n % 2 == 1  
>   m <- 1 to n  
> } yield n * m  

### Definitions

> for {  
>    time <- times  
>    hours = time.hours if hours > 12  
> } yield (hours - 12) + "pm"  
> // Result: Vector[String] = Vector(1pm, 2pm)  

What's the type of times?
What's a possible value for times?
