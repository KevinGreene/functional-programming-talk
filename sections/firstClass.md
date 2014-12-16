## First Class Functions are...


### Arguments

Functions can be passed as arguments

Functions can be returned by functions


### Arguments Compared

Imperative
```
applySpecificFunction(Collection c){
  def newCollection = new Collection
  for x in c {
    newCollection.add(specificFunction(x))
  }
  return newCollection
}
```

Functional
```
applySpecificFunction(Collection c){
  return map(specificFunction, c)
}
```


### Return Values

Functions can return other functions


### Return Value Example

```
def applyTwice(f) {
  return f(f)
}

def addThree(x) {
  return x + 3
}

def addSix = applyTwice(addThree)
addSix(2) // 8
```


### Anonymous

Functions can be defined without a name


### Anonymous Compared

Imperative
```
  processDatum(datum) {
    return datum * 3
  }
  processData(data){
    map(processDatum, data) // Map imported from FP lib
  }
```

Functional
```
  processData(data){
    map((x) -> x*3 , data) // Map imported from FP lib
  }
```


### Currying / Partial Application

Functions called without all arguments return partial functions.

```
def f(a,b) // equivalent to f(a)(b)
def partial = f(a) // returns a function that takes single argument
```


### Currying / Partial Application Compared

Imperative
```
 def modN(n, x) = (x % n) == 0

 def n = 3
 for(x in list){
   modN(n, x)
 }
 ```

Functional

```
 def modN(n, x) = (x % n) == 0
 def mod3 = modN(3)
 for(x in list){
   mod3(x)
 }
```