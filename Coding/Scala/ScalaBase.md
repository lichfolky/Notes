##Scala

REPL = read eval print loop
compiles and eval

REPL commands
> :javap <path|class>  disassemble to java  
> :load <path>   load scala functionalities  
> :quit exit the interpreter

for repl multiline expressions use | as multiline

BP: use dangling operators  
` val pippo = 5 `  
`+ 4 `

+ no curly brakets for single line
+ no need of return
+ Type annotations can be omitted

methods with one parameter can be used in fix notation (use it if the name it's symbolic)

`Martin Odersky".split(" ")`  
equals to  
`Martin Odersky" split " "`

postfix for no parameter methods

 `"Martin Odersky" split " " size`

 Methods starting with unary_ followed by +, -, ! or ~ can and should be used in prefix notation


#### Variables
var mutable
val immutable

protected visible within the enclosing entity of subclasses

#### Pakages and imports

` pakage com.typesafe.training.scalatrain ` for all members  

` import com.typesafe.training.scalatrain._ ` for all members  
> .{a, b} for multiple members  
> .{Date=>salDate} renaming

you can scope for method, import inside a method declaration.

#### Classes

**singleton objects**, defined by the use the keyword "object" instead of class,

single inheritance, extend exactly one superclass

AnyRef if no superclass is extended explicitly

> class Hello(msg: String)

**Signature** name and parameters (class definition)

> class Hello(val msg: String)

use **val/var** in the class parameters promote them, it creates a field and inits it to the passed value

` def name(first: String =  "") `
to define Default arguments

#### Methods and operators
method:
> def call

you can assign args by name

>  call(name="Pippo")

**equality**
no difference between primitive and reference  

null safe

for checking identity

> eq  
> ne

val/var class fields can be accessed with dot

An immutable field **(val)** gets compiled into
+ private final field
+ public getter method

An mutable field **(var)** gets compiled into
+ private field
+ public getter method
+ public setter method

#### Constructors
a **primary constructor** it's automatically defined by the Class parameters

in the defiinition of alternative constructors use
> def this() = ...

remember to init all the parameters

#### Companions

if the class has same pkg, name and file of another it's a companion

#### predef singleton object


#### Case classes
+ no need to use "new" in new instances
+ has apply method
+ has copy methods

used in values objects

#### Qualified Access Modifiers
use [] for relaxing and access the entity?
this for accessing the instance


#### Strings

s"Value = $n" with parameters $id
f fror expression ${expr}



##### Questions
+ what's an activator http://lightbend.com/activator
+ immutable objects?
+ pakage and import: full qualified name? difference btw ._ and pakage of the parent
+ prepend?

##### Unclear
+ Case keyword
+ relaxed Access []



Fold
accuulatore
funz che contiene qualcosa

contesto f che contiene delle a
