# Shuffle

Randomly rearranges the contents of an array.

Kotlin playground [link](https://pl.kotl.in/aVq0IjksY)

## Code

Here is a implementation of Shuffle in kotlin:

```kotlin
import java.util.Random

fun <T : Comparable<T>> shuffle(items: MutableList<T>): List<T> {
    val rg = Random()
    for (i in 0..<items.size) {
        val randomPosition = rg.nextInt(items.size)
        val tmp: T = items[i]
        items[i] = items[randomPosition]
        items[randomPosition] = tmp
    }
    return items
}
```

Shuffle implementation provide by Markus Kramer. This implementation reuses existing code to do the shuffling and can be called like other kotlin collection functions.
 
```kotlin
import java.util.Collections
  /**
     * Returns a randomized list.
     */
fun <T> Iterable<T>.shuffle(): List<T> {
    val list = this.toMutableList().apply { }
    Collections.shuffle(list)
    return list
}
```
