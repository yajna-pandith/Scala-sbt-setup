# Scala-sbt-setup
## Setting up JAVA_HOME
```
brew tap AdoptOpenJDK/openjdk
brew install --cask adoptopenjdk8
```

## Setting up SCALA_HOME
### Download scala
```
wget https://downloads.lightbend.com/scala/2.12.10/scala-2.12.10.tgz  /tmp 
cd /tmp
tar -zxvf scala-2.12.10.tgz 
mv scala-2.12.10 /usr/local/opt
```
### In .zshrc 
```
export JAVA_HOME=$(/usr/libexec/java_home -v1.8)
export PATH="$JAVA_HOME/bin:$PATH"
SCALA_HOME=/us/local/opt/scala-2.12.10
export PATH="$JAVA_HOME/bin:$SCALA_HOME/bin:$PATH"
```


## Install sbt 

```
brew install sbt
```

## In the IntelliJ
From IntelliJ marketplace install Scala plugin and SBT Executor plugin

Create a new sbt project 

## In the build.sbt

```
name := "awsS3utils"

scalaVersion := "2.12.10"

version := "0.1"

organization := "com.bsq.fintrans"

libraryDependencies ++= Seq("com.amazonaws" % "aws-java-sdk" % "1.12.37" )

libraryDependencies ++= Seq("org.apache.hadoop" % "hadoop-hdfs" % "3.2.0")

libraryDependencies ++= Seq("org.apache.spark" %% "spark-sql" % "3.1.2")
```





