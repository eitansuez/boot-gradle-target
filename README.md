# Example boot project illustrating use of sourceCompatibility.

## Assumptions

* You have openjdk-11 installed on your machine and `$JAVA_HOME/bin` is in your `$PATH`

## java 8 compatibility

#### Given
 
Note in `build.gradle` the following line:

```
sourceCompatibility = 1.8
```

### When

Build the project:

```
$ gradle clean build
```

### Then

Test the java version of a generated class file:

```
javap -v ./build/classes/java/main/com/eitan/bootgradletarget/HelloController.class | grep major
```

The output should be:

```
major version: 52
``` 

## java 11 compatibility

Edit `build.gradle` and set `sourceCompatibility` to `1.11`, and repeat the above steps:

1. do a clean build
2. re-run javap
3. the output should now state `major version: 55`


