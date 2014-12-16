## What?


### Pure Functions

Functions have no side effects

Same input -> Same output


### Pure Functions Compared

Object-Oriented
```
processSomeObject(Object o) {
  this.state = "changed"
  o.property = "new"
  return o
}
```

Functional
```
processSomeObject(Object o){
  return new Object(o, "new")
}
```


### Recursion

Present in most imperative languages

Prioritized in functional languages


### Recursion Compared

Imperative
```
def sum(list){
  def intSum = 0
  for (x in list) {
    intSum = intSum + x
  }
}

```

Functional
```
def sum(ints: List[Int]): Int = ints match { 
  case Nil => 0
  case x :: tail => x + sum(tail)
}
```


### Pattern Matching

```
  def matchTest(x: Any): Any = x match {
    case 1 => "one"
    case "two" => 2
    case y: Int => y + 10
    case _ => "many"
  }
```


### Lazy

Functions are only executed when their value is needed

Allows theoretical constructs like infinite lists

Never spend cycles on unused values


### Lazy Compared

Imperative
```
def l = [1, 2, 3]
def newL = []
for(i = 0; i < l.length; i++){
  newL.push(l[i] + i)
}
// All computation done at execution
```

Functional

```
(map + [1 2 3] (iterate inc 1))
;; Returns immediately
```


### First Class Functions