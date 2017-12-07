# Native Array Methods: Map, Filter, Reduce

## Objectives

* Explain the use case for native array methods
  - map
  - filter
  - reduce
* Write map, filter, and reduce functions
* Identify the parts of a native array method
* Chaining methods together

## Notes

* Explain the use case for native array methods
  - map:
    * returns a new array of the same length as input array
    * apply our code to every item in the input array
    * often some kind of data transformation or manipulation
  - filter:
    * looks for a specific thing in array and keeps it or not
    * involves a test
    * returns a new array of equal or LESSER length than the input array
    * filter out items from the original array based on our test/condition
    * generally want to remove things from the array
  - reduce:
    * doesn't automatically return a new array
    * returns a new value (string, number, object, array)
    * often reducing into a single value

* Patterns in structure
  - All these methods take a callback function as a parameter
  - Set up an action for each element in the array
  - MAP, REDUCE, FILTER:
    * Need to return something for each iteration!!!
    * Outside of the callback function, usually want to return result of the function running

* Identifying parts of native array methods
  - MAP, FILTER, FOREACH - 3 Potential Parameters:
    1. Current Value/Item in the loop
    2. Current index value in the loop
    3. Array that the method was called on
  - REDUCE - 4 potential parameters
    1. We have an accumulator as the first parameter
    2. Current Value/Item in the loop
    3. Current index value in the loop
    4. Array that the method was called on

```js

// REDUCE PARAMETERS / STRUCTURE

spells.reduce(function(accumulator, currentValue, index, array) {
  // Business logic

}, '')

// CHAINING METHODS

function getTotalItemSales(sales, id){
    var filteredArray = sales.filter(sale => sale.itemId == id)
    var reducedArray = filteredArray.reduce((totalSales, sale) => {
        return totalSales += sale.quantity;
    }, 0);

    return sales.filter(sale => sale.itemId == id).reduce((totalSales, sale) => {
        return totalSales += sale.quantity;
    }, 0);
}

```
