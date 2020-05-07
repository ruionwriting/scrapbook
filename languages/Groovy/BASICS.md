> Don't get to excited to expect amazing Grooby code here. These are learning notes/cheatcheat. Grooby is not my thing, just something I need to use.

# Groovy Basics

## String interpolation and a bit more

### Basic

```groovy
def completedActivities = 0
completedActivities = completedActivities + 5
println 'You have completed ' + completedActivities + ' activities today.'

def totalActivities = 10
totalActivities = totalActivities - completedActivities
println 'You now have ' + totalActivities +' activities remaining.'
```

Output:

```shell
You have completed 5 activities today.
you now have 5 activities remaining.
```

### Improve things and explore the options we have

```groovy
def completedActivities = 0
completedActivities = completedActivities + 5
println "You have completed $completedActivities activities today."

def totalActivities = 10
totalActivities = totalActivities - completedActivities
println "you now have $totalActivities activities remaining."

```

Output:

```shell
You have completed 5 activities today.
you now have 5 activities remaining.
```

### Even better

```groovy
def completedActivities = 0
completedActivities = completedActivities + 5
println "You have completed ${completedActivities + 1} activities today."

def totalActivities = 10
totalActivities -= completedActivities
println "You now have $totalActivities activities remaining."

```

Note calculating a value while interpolating and using a simpler form of calculating `totalActivities`.

Output:

```shell
You have completed 6 activities today.
you now have 5 activities remaining.
```

## Working with objects

### Types

Example on how to [determine type of an object](https://code-maven.com/groovy-determine-type-of-object):

```groovy
def obj = ["question", 42, 'answer']
 
println obj.getClass()   // class java.util.ArrayList
 
println (obj instanceof List)                   // true
println (obj instanceof java.util.ArrayList)    // true
 
println (obj.getClass() == List)                // false
println (obj.getClass() == java.util.ArrayList) // true
```
