FP section: https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/functional-programming
## challenge #1:
##### Functional Programming: Learn About Functional Programming

```
/**
 * A long process to prepare tea.
 * @return {string} A cup of tea.
 **/
const prepareTea = () => 'greenTea';

/**
 * Get given number of cups of tea.
 * @param {number} numOfCups Number of required cups of tea.
 * @return {Array<string>} Given amount of tea cups.
 **/
const getTea = (numOfCups) => {
  const teaCups = [];
  
  for(let cups = 1; cups <= numOfCups; cups += 1) {
    const teaCup = prepareTea();
    teaCups.push(teaCup);
  }

  return teaCups;
};

// Add your code below this line

const tea4TeamFCC = getTea(40); // :(

// Add your code above this line

console.log(tea4TeamFCC);
```

:heavy_check_mark: The tea4TeamFCC variable should hold 40 cups of tea for the team.<br/>
:heavy_check_mark: The tea4TeamFCC variable should hold cups of green tea.<br/>
<br/><br/>
## challenge #11:
##### Functional Programming: Return Part of an Array Using the slice Method

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
<br/><br/>
## challenge #16: 
##### Functional Programming: Sort an Array Alphabetically using the sort Method

```
function alphabeticalOrder(arr) {
  // Add your code below this line
  
  return arr.sort(function(a, b){
    if(a < b){ return -1; }
    if(a > b){ return 1; }
    return 0;
  });
  
  // Add your code above this line
}
alphabeticalOrder(["a", "d", "c", "a", "z", "g"]);
```

:heavy_check_mark: Your code should use the sort method.<br/>
:heavy_check_mark: alphabeticalOrder(["a", "d", "c", "a", "z", "g"]) should return ["a", "a", "c", "d", "g", "z"].<br/>
:heavy_check_mark: alphabeticalOrder(["x", "h", "a", "m", "n", "m"]) should return ["a", "h", "m", "m", "n", "x"].<br/>
:heavy_check_mark: alphabeticalOrder(["a", "a", "a", "a", "x", "t"]) should return ["a", "a", "a", "a", "t", "x"].<br/>
<br/><br/>
## challenge #17: 
##### Functional Programming: Return a Sorted Array Without Changing the Original Array

```
var globalArray = [5, 6, 3, 2, 9];
function nonMutatingSort(arr) {
  // Add your code below this line
  
  return [].concat(arr).sort();

  // Add your code above this line
}
nonMutatingSort(globalArray);
```

:heavy_check_mark: Your code should use the sort method.<br/>
:heavy_check_mark: Your code should use the concat method.<br/>
:heavy_check_mark: The globalArray variable should not change.<br/>
:heavy_check_mark: nonMutatingSort(globalArray) should return [2, 3, 5, 6, 9].<br/>
<br/><br/>
## challenge #18: 
##### Functional Programming: Split a String into an Array Using the split Method

```
function splitify(str) {
  // Add your code below this line
  
  return str.split(/[^a-z]/i);
  
  // Add your code above this line
}
splitify("Hello World,I-am code");
```

:heavy_check_mark: Your code should use the split method.<br/>
:heavy_check_mark: splitify("Hello World,I-am code") should return ["Hello", "World", "I", "am", "code"].<br/>
:heavy_check_mark: splitify("Earth-is-our home") should return ["Earth", "is", "our", "home"].<br/>
:heavy_check_mark: splitify("This.is.a-sentence") should return ["This", "is", "a", "sentence"].<br/>
<br/><br/>
## challenge #19: 
##### Functional Programming: Combine an Array into a String Using the join Method

```
function sentensify(str) {
  // Add your code below this line
  
  return str.split(/[-,.]/).join(" ");

  // Add your code above this line
}
sentensify("May-the-force-be-with-you");
```

:heavy_check_mark: Your code should use the join method.<br/>
:heavy_check_mark: Your code should not use the replace method.<br/>
:heavy_check_mark: sentensify("May-the-force-be-with-you") should return a string.<br/>
:heavy_check_mark: sentensify("May-the-force-be-with-you") should return "May the force be with you".<br/>
:heavy_check_mark: sentensify("The.force.is.strong.with.this.one") should return "The force is strong with this one".<br/>
:heavy_check_mark: sentensify("There,has,been,an,awakening") should return "There has been an awakening".<br/>
<br/><br/>
## challenge #20: 
##### Functional Programming: Apply Functional Programming to Convert Strings to URL Slugs

```
// the global variable
var globalTitle = "Winter Is Coming";

// Add your code below this line
function urlSlug(title) {
  
  return title.trim().split(/ +/g).join("-").toLowerCase();
  
}
// Add your code above this line

var winterComing = urlSlug(globalTitle); // Should be "winter-is-coming"
```

:heavy_check_mark: The globalTitle variable should not change.<br/>
:heavy_check_mark: Your code should not use the replace method for this challenge.<br/>
:heavy_check_mark: urlSlug("Winter Is Coming") should return "winter-is-coming".<br/>
:heavy_check_mark: urlSlug(" Winter Is  Coming") should return "winter-is-coming".<br/>
:heavy_check_mark: urlSlug("A Mind Needs Books Like A Sword Needs A Whetstone") should return "a-mind-needs-books-like-a-sword-needs-a-whetstone".<br/>
:heavy_check_mark: urlSlug("Hold The Door") should return "hold-the-door".<br/>
<br/><br/>
## challenge #21: 
##### Functional Programming: Use the every Method to Check that Every Element in an Array Meets a Criteria

```
function checkPositive(arr) {
  // Add your code below this line
  
    return arr.every(function(elem){
        return elem > 0
    });
  
  // Add your code above this line
}
checkPositive([1, 2, 3, -4, 5]);
```

:heavy_check_mark: Your code should use the every method.<br/>
:heavy_check_mark: checkPositive([1, 2, 3, -4, 5]) should return false.<br/>
:heavy_check_mark: checkPositive([1, 2, 3, 4, 5]) should return true.<br/>
:heavy_check_mark: checkPositive([1, -2, 3, -4, 5]) should return false.<br/>
<br/><br/>
## challenge #22: 
##### Functional Programming: Use the some Method to Check that Any Elements in an Array Meet a Criteria

```
function checkPositive(arr) {
  // Add your code below this line
  
  return arr.some(function(elem){
    return elem > 0;
  });
  
  // Add your code above this line
}
checkPositive([1, 2, 3, -4, 5]);
```

:heavy_check_mark: Your code should use the some method.<br/>
:heavy_check_mark: checkPositive([1, 2, 3, -4, 5]) should return true.<br/>
:heavy_check_mark: checkPositive([1, 2, 3, 4, 5]) should return true.<br/>
:heavy_check_mark: checkPositive([-1, -2, 3, -4, -5]) should return false.<br/>
<br/><br/>
## challenge #23: 
##### Functional Programming: Introduction to Currying and Partial Application

```
function add(x) {
  // Add your code below this line
  
  return function(y){
    return function(z) {
      return x + y + z;
    } 
  }
  
  // Add your code above this line
}
add(10)(20)(30);
```

:heavy_check_mark: add(10)(20)(30) should return 60.<br/>
:heavy_check_mark: add(1)(2)(3) should return 6.<br/>
:heavy_check_mark: add(11)(22)(33) should return 66.<br/>
:heavy_check_mark: Your code should include a final statement that returns x + y + z.<br/>
