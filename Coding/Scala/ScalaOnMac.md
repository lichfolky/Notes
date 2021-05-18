install xcode

(xcode-select --install ??)

## install brew
**copy the script from https://brew.sh/index_it**

## install jenv
```brew install jenv```
** and follow instructions on https://www.jenv.be/ to add variables to ~/.zshrc or ~/.bash_profile **

install the supported jdk
brew cask install <thejavaversion>
jenv add $(PATH_TO_JVM_HOME)

load a version
```jenv local openjdk64-1.8.0.222```

install java 1.8

```brew install scala```
To use with IntelliJ, set the Scala home to:
/usr/local/opt/scala/idea

docs:
https://www.scala-lang.org/download/

## spark
check supported versions:
https://spark.apache.org/docs/latest/
