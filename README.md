# SimpleStream
SimpleStream makes it easier to use Java 8 Streams by reducing the amount of boilerplate code required to perform common tasks.

````java
import static simplestream.SimpleStream.stream;

Collection<Integer> values = Arrays.asList(1, 5, 2, 4, 3);

/* Simpler collector methods */
stream(values).map(x -> x + 1).toList(); // [2, 6, 3, 5, 4]

/* Less confusing filtering */
stream(values).select(x -> x % 2 == 0).toList(); // [2, 4]
stream(values).remove(x -> x % 2 == 0).toList(); // [1, 5, 3]

/* Comparison operations (for streams of Comparable elements) */
stream(values).min(); // 1
stream(values).max(); // 5
stream(values).sort().toList(); // [1, 2, 3, 4, 5]

/* Numeric operations (for streams of numbers) */
stream(values).sumAsInt(); // 15
stream(values).average(); // 3.0

/* Miscellaneous operations */
stream(values).groupBy(x -> x % 2 == 0 ? "even" : "odd"); // {even=[2, 4], odd=[1, 5, 3]}
stream(values).contains(4); // true
stream(values).join("+"); // "1+5+2+4+3"
````

SimpleStream is distributed in source form and contains a single source file (<code>SimpleStream.java</code>) that can be directly included in your project. You can download the latest release [here](https://github.com/lmadhavan/simplestream/releases).
