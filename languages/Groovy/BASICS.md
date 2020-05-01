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
