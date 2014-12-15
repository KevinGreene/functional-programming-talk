## Why?


### Concurrency

Stateless functions are inherently parallelizable

Immutable objects are inherently threadsafe


### No Side-effect Bugs

Side effects clearly defined and clearly marked

No weird state issues


### Brevity

From Programming Clojure:

```java
// From Apache Commons Lang, http://commons.apache.org/lang/
public static int indexOfAny(String str, char[] searchChars) {
  if (isEmpty(str) || ArrayUtils.isEmpty(searchChars)) {
      return -1;
  }
  for (int i = 0; i < str.length(); i++) {
      char ch = str.charAt(i);
      for (int j = 0; j < searchChars.length; j++) {
        if (searchChars[j] == ch) {
            return i;
        } 
      }
  }
  return -1;
}
```

```clojure
(defn indexed [s] (map vector (iterate inc 0) s))

(defn index-filter [pred coll]
  (when pred
    (for [[idx elt] (indexed coll) :when (pred elt)] idx)))

(defn index-of-any [pred coll]
  (first (index-filter pred coll)))
```


### Holistic Reasons

Expanding paradigm knowledge increases programmer ability

Many programmers find functional programs simpler

Many programmers find functional programming more fun

Recruiting and retention