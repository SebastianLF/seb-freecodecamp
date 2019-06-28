FP section: https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/functional-programming

## challenge #11:
##### Return Part of an Array Using the slice Method

```
function sliceArray(anim, beginSlice, endSlice) {
  // Add your code below this line
  
  return anim.slice(beginSlice, endSlice);
  
  // Add your code above this line
}
var inputAnim = ["Cat", "Dog", "Tiger", "Zebra", "Ant"];
sliceArray(inputAnim, 1, 3);
```

:heavy_check_mark: Your code should use the slice method.<br/>
:heavy_check_mark: The inputAnim variable should not change.<br/>
:heavy_check_mark: sliceArray(["Cat", "Dog", "Tiger", "Zebra", "Ant"], 1, 3) should return ["Dog", "Tiger"].<br/>
:heavy_check_mark: sliceArray(["Cat", "Dog", "Tiger", "Zebra", "Ant"], 0, 1) should return ["Cat"].<br/>
:heavy_check_mark: sliceArray(["Cat", "Dog", "Tiger", "Zebra", "Ant"], 1, 4) should return ["Dog", "Tiger", "Zebra"].
<br/><br/>
## challenge #12: 
##### Functional Programming: Remove Elements from an Array Using slice Instead of splice

```
function nonMutatingSplice(cities) {
  // Add your code below this line
  return cities.slice(0, 3);
  
  // Add your code above this line
}
var inputCities = ["Chicago", "Delhi", "Islamabad", "London", "Berlin"];
nonMutatingSplice(inputCities);
```

:heavy_check_mark: Your code should use the slice method.<br/>
:heavy_check_mark: Your code should not use the splice method.<br/>
:heavy_check_mark: The inputCities array should not change.<br/>
:heavy_check_mark: nonMutatingSplice(["Chicago", "Delhi", "Islamabad", "London", "Berlin"]) should return ["Chicago", "Delhi", "Islamabad"].
<br/><br/>
## challenge #13: 
##### Functional Programming: Combine Two Arrays Using the concat Method

```
function nonMutatingConcat(original, attach) {
  // Add your code below this line
  
  return [].concat(original).concat(attach);
  
  // Add your code above this line
}
var first = [1, 2, 3];
var second = [4, 5];
nonMutatingConcat(first, second);
```

:heavy_check_mark: Your code should use the concat method.<br/>
:heavy_check_mark: The first array should not change.<br/>
:heavy_check_mark: The second array should not change.<br/>
:heavy_check_mark: nonMutatingConcat([1, 2, 3], [4, 5]) should return [1, 2, 3, 4, 5].
<br/><br/>
## challenge #14: 
##### Functional Programming: Add Elements to the End of an Array Using concat Instead of push

```
function nonMutatingPush(original, newItem) {
  // Add your code below this line
  return [].concat(original).concat(newItem);
  
  // Add your code above this line
}
var first = [1, 2, 3];
var second = [4, 5];
nonMutatingPush(first, second);
```

:heavy_check_mark: Your code should use the concat method.<br/>
:heavy_check_mark:Your code should not use the push method.<br/>
:heavy_check_mark:The first array should not change.<br/>
:heavy_check_mark:The second array should not change.<br/>
:heavy_check_mark:nonMutatingPush([1, 2, 3], [4, 5]) should return [1, 2, 3, 4, 5].
<br/><br/>
## challenge #15: 
##### Functional Programming: Use the reduce Method to Analyze Data

:heavy_exclamation_mark: The global variable "watchList" is [here](https://github.com/zelol/seb-freecodecamp/blob/master/functional-programming/watchList.md).

```
// Add your code below this line

var averageRating;

function filterByDirector(list, director){
  return list.filter(function(value, index, arr) {
    return value.Director === director;
  })
}

function sumRating(list, key) {
  return list.reduce(function(acc, value, index, arr){
    length = index + 1;
    return acc + Number(value[key]);
  }, 0)
}

function avgRatingCompute(sum, length) {
  return sum /= length;
}

averageRating = avgRatingCompute(sumRating(filterByDirector(watchList, "Christopher Nolan"), 'imdbRating'), filterByDirector(watchList, "Christopher Nolan").length);

// Add your code above this line

console.log(averageRating); 
```

:heavy_check_mark: The watchList variable should not change.<br/>
:heavy_check_mark: Your code should use the reduce method.<br/>
:heavy_check_mark: The averageRating should equal 8.675.<br/>
:heavy_check_mark: Your code should not use a for loop.
