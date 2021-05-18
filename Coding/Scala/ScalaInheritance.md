## inheritance
Each class, except for Any, has exactly one superclass

Non private members are inherited (also methods)
Non final members can be overridden

Use final to prevent a class from being extended

Sealed classes can only be extended within the same source file
Use it to create an algebraic data type (ADT) called tagged union
Example: Option with Some and None

### Subtype polymorphism

The subclass type conforms to the superclass type (subclass type is a superclass type)

> class Animal  
> class Bird extends Animal

extends defined a subclass  
AnyRef is used as superclass if you omit the extends part  
You can only extend exactly one class  

### The Superclass Constructor
>class Animal(val name: String)
> class Bird(name: String) extends Animal(name)

Attention: Superclasses are initialised first
Use final to prevent a class from being extended

### Overriding
>class Animal {
>  def eat(): Unit = println("Yum yum!")
>}
>
>class Bird extends Animal {
>  override def eat(): Unit = println("Beep!")
>}

Use override keyword to override a member
It redefines an existing member
All non final inherited members can be overridden
Use final to prevent a member from being overridden


super.eat()
Use super to access the superclass members


#### Uniform Access Principle

def name: String = "Arnold"
is the same
val name: String = "Arnold"

#### Lazy vals

All vals are initialized during object construction
Use lazy keyword to defer initialization until first usage
Attention: Lazy vals are not final and therefore might show performance drawbacks

> lazy val lazySeven = {
>        println("I am very lazy ;-)")
>        7
>     }


#### Abstract Classes
> abstract class Animal {
>  def name: String
>  def eat(): Unit
> }

Abstract classes cannot be instantiated
Abstract members define only the signature

>class Bird extends Animal {
>  def name: String = "Bill"
>  override def eat(): Unit = println("Beep!")
>}


**ADT** abstract data type

#### Traits

To overcome exactly one superclass limitation, Mix-in multiple traits

> trait Swimmer {
>  def swim: String = "I am swimming!"
> }

> class Foo
> trait Bar extends Foo

Traits may contain concrete and abstract members
Traits are abstract and can not have parameters
Like classes, traits extend exactly one superclass

Rule of thumb: First keyword has to be extends, regardless whether a class or trait,
 then use with for further mix-ins. Remember that mixing-in a trait means
 extending the superclass of the trait

Traits must respect the inheritance hierarchy, i.e. a class must not extend two incompatible superclasses
