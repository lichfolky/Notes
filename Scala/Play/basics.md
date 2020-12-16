### Play framework
Java 1.8 for Scala
Build tools: sbt or Gradle

**MVC pattern:**  
`app/controllers`  
`app/models`  
`app/views`  

`public/` static assets 4 web server  
`conf/`  
+ application.conf
+ routes  

`target/` builds  

### Play console
>~ ALT + 5

you run it with `sbt ` in the top level of the project  
`~ run` or `sbt run`  
+ `sbt 'run 8080'`  

`~ test` or `sbt test`  
`~ testOnly class` or `sbt class`  
es: `~ testOnly com.acme.SomeClassTest`  

Will trigger the execution of com.acme.SomeClassTest test every time you modify a source file.


`help run` for help

Play uses akka 
