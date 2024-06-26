# Insertion sort

<p align="center">
  <img width="400" src="https://github.com/MedellinAndroid/Kotlin-Algorithm/blob/master/InsertionSort/InsertionSort_anim.gif">
</p>

Insertion sort is a simple sorting algorithm that builds the final sorted array (or list) one item at a time. It is much less efficient on large lists than more advanced algorithms such as quicksort, heapsort, or merge sort.

Source: [Wikipedia page for Insertion sort](https://en.wikipedia.org/wiki/Insertion_sort)

Kotlin playground [link](https://pl.kotl.in/CxN8B7rlg)

## Code

```kotlin
fun <T : Comparable<T>> insertionSort(items: MutableList<T>): List<T> {
    if (items.isEmpty()) {
        return items
    }

    for (count in 1..<items.count()) {
        val item = items[count]
        var i = count
        while (i > 0 && item < items[i - 1]) {
            items[i] = items[i - 1]
            i -= 1
        }
        items[i] = item
    }
    return items
}
```