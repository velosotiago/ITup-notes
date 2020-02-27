Sorting Algorithms

# Sorting Algorithms


## Insertion Sort
```js
function InsertionSort(array) {
    for (i = 1; i < array.length; i++) {
        var notSorted = array[i];
        var j = i - 1;
        
        while (j >= 0 && array[j] > notSorted) {
            array[j+1] = array[j];
            j--;
        }
        array[j+1] = notSorted;
    }
    return array;
}
```

## Bubble Sort
Iterates through the array, always comparing array[i] and array[i+1] and switching them if needed.
```js
function BubbleSort(array) {
    var sorted = false;
    while (!sorted){
        sorted = true;
        for (var i = 0; i < array.length - 1; i++) {
            if (array[i] > array[i+1]) {
                sorted = false;
                var aux = array[i+1];
                array[i+1] = array[i];
                array[i] = aux;
            }
        }
    }
    return array;
}
```