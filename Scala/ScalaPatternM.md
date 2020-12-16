### Match Expressions

>expr match {  
>  case pattern1 => result1  
>  case pattern2 => result2  
>}


No fall through to the next alternative  
Match expressions return a value  
MatchError is thrown if no pattern matches  

patterns:
+ _ wildcard capture all
+ Variable pattern (es 'x') capture all and capture the value
+ Use a type annotation to match only certain types val:Int (they need variable or wildcard case also)
+ Costant .... Stable Identifiers
  > val highNoon = "12:00"
  > def whatTimeIsIt(any: Any): String = any match {
>  case `highNoon`=> "ciao"  

+ tuple
+ constructor pattern

>def matchSeq[A](seq: Seq[A]): String = seq match {  
>  case Seq(1, 2, 3) => "1 to 3"  
>  case x +: Nil => s"Only element is $x"  
>  case _ :+ x => s"Last element is $x"  
>  case Nil => "Empty sequence"  
>}

+ sequence pattern
+ | multiple patterns combine
+ Use @ to bind a variable to a pattern

use the if keyword to define a pattern guard
> case Time(h, m) if h >=12 => s"Yes, it is ${h-12}:$m pm"  

#### Exceptions

Use try-catch-expression to catch an exception
In the catch-clause define one or more match alternatives
finally-clause is optional

> def toInt(s: String): Int =  
>  try {  
>    s.toInt  
>  } catch {  
>    case \_: NumberFormatException => 0  
>  }

you can use patterns in loop Expressions

#### Optional values

Option is an ADT ab da ty with 2 values: some and None

Option() (Some and None...)
foreach()
getOrElse()
