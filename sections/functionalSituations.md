## When?


### ALL THE PROBLEMS!!!

![FP All The Things!](images/x-all-the-things-template.png)


### Expression Problem

![Expression Problem](images/expression_problem.png)


### Parallelizable Computation

Single Core

```clojure
(map + (iterate inc 0) (iterate inc 1))
```

Multiple Cores
```clojure
(pmap + (iterate inc 0)(iterate inc 1))
```


### DSLs

Midje

```clojure
(facts "about `first-element`"
  (fact "it normally returns the first element"
    (first-element [1 2 3] :default) => 1
    (first-element '(1 2 3) :default) => 1)
```


### Data Manipulation

Functional programming is already built on data transforms

Easily parallelizability makes data import faster


### Web Development

HTTP is stateless and full of verbs


### UI Development

React, RxJava, ReactiveCocoa focus on functional concepts

ClojureScript + React is delightful