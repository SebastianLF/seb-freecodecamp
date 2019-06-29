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
## challenge #2:
##### Functional Programming: Understand Functional Programming Terminology

```
/**
 * A long process to prepare green tea.
 * @return {string} A cup of green tea.
 **/
const prepareGreenTea = () => 'greenTea';

/**
 * A long process to prepare black tea.
 * @return {string} A cup of black tea.
 **/
const prepareBlackTea = () => 'blackTea';

/**
 * Get given number of cups of tea.
 * @param {function():string} prepareTea The type of tea preparing function.
 * @param {number} numOfCups Number of required cups of tea.
 * @return {Array<string>} Given amount of tea cups.
 **/
const getTea = (prepareTea, numOfCups) => {
  const teaCups = [];

  for(let cups = 1; cups <= numOfCups; cups += 1) {
    const teaCup = prepareTea();
    teaCups.push(teaCup);
  }

  return teaCups;
};

// Add your code below this line

const tea4GreenTeamFCC = getTea(prepareGreenTea, 27); // :(
const tea4BlackTeamFCC = getTea(prepareBlackTea, 13); // :(

// Add your code above this line

console.log(
  tea4GreenTeamFCC,
  tea4BlackTeamFCC
);
```

:heavy_check_mark: The tea4GreenTeamFCC variable should hold 27 cups of green tea for the team.<br/>
:heavy_check_mark: The tea4GreenTeamFCC variable should hold cups of green tea.<br/>
:heavy_check_mark: The tea4BlackTeamFCC variable should hold 13 cups of black tea.<br/>
:heavy_check_mark: The tea4BlackTeamFCC variable should hold cups of black tea.<br/>
<br/><br/>
## challenge #3:
##### Functional Programming: Understand the Hazards of Using Imperative Code

```
// tabs is an array of titles of each site open within the window
var Window = function(tabs) {
  this.tabs = tabs; // we keep a record of the array inside the object
};

// When you join two windows into one window
Window.prototype.join = function (otherWindow) {
  this.tabs = this.tabs.concat(otherWindow.tabs);
  return this;
};

// When you open a new tab at the end
Window.prototype.tabOpen = function (tab) {
  this.tabs.push('new tab'); // let's open a new tab for now
  return this;
};

// When you close a tab
Window.prototype.tabClose = function (index) {
  var tabsBeforeIndex = this.tabs.splice(0, index); // get the tabs before the tab
  var tabsAfterIndex = this.tabs.splice(index); // get the tabs after the tab

  this.tabs = tabsBeforeIndex.concat(tabsAfterIndex); // join them together 
  return this;
 };

// Let's create three browser windows
var workWindow = new Window(['GMail', 'Inbox', 'Work mail', 'Docs', 'freeCodeCamp']); // Your mailbox, drive, and other work sites
var socialWindow = new Window(['FB', 'Gitter', 'Reddit', 'Twitter', 'Medium']); // Social sites
var videoWindow = new Window(['Netflix', 'YouTube', 'Vimeo', 'Vine']); //  Entertainment sites

// Now perform the tab opening, closing, and other operations
var finalTabs = socialWindow
                    .tabOpen() // Open a new tab for cat memes
                    .join(videoWindow.tabClose(2)) // Close third tab in video window, and join
                    .join(workWindow.tabClose(1).tabOpen());

alert(finalTabs.tabs);
```

:heavy_check_mark: Work through the code and see if you can figure out the problem, then advance to the next challenge to learn more.
<br/><br/>
## challenge #4:
##### Functional Programming: Avoid Mutations and Side Effects Using Functional Programming

```
// the global variable
var fixedValue = 4;

function incrementer (value) {
  // Add your code below this line
  
  return fixedValue + 1;
  // Add your code above this line
}

var newValue = incrementer(); // Should equal 5
console.log(fixedValue); // Should print 4
```

:heavy_check_mark: Your function incrementer should not change the value of fixedValue.<br/>
:heavy_check_mark: Your incrementer function should return a value that is one larger than the fixedValue value.
<br/><br/>
## challenge #5:
##### Functional Programming: Pass Arguments to Avoid External Dependence in a Function

```
// the global variable
var fixedValue = 4;

// Add your code below this line
function incrementer (value) {
  
  return value + 1;
  // Add your code above this line
}

var newValue = incrementer(fixedValue); // Should equal 5
console.log(fixedValue); // Should print 4
```

:heavy_check_mark: Your function incrementer should not change the value of fixedValue.<br/>
:heavy_check_mark: Your incrementer function should take a parameter.<br/>
:heavy_check_mark: Your incrementer function should return a value that is one larger than the fixedValue value.<br/>
<br/><br/>
## challenge #6:
##### Functional Programming: Refactor Global Variables Out of Functions

```
// the global variable
var bookList = ["The Hound of the Baskervilles", "On The Electrodynamics of Moving Bodies", "Philosophiæ Naturalis Principia Mathematica", "Disquisitiones Arithmeticae"];

/* This function should add a book to the list and return the list */
// New parameters should come before the bookName one

// Add your code below this line
function add (list, bookName) {
  
  return list.concat(bookName)
  
  // Add your code above this line
}

/* This function should remove a book from the list and return the list */
// New parameters should come before the bookName one

// Add your code below this line
function remove (list, bookName) {
    return list.filter(function(elem){ return elem !== bookName })
}

var newBookList = add(bookList, 'A Brief History of Time');
var newerBookList = remove(bookList, 'On The Electrodynamics of Moving Bodies');
var newestBookList = remove(add(bookList, 'A Brief History of Time'), 'On The Electrodynamics of Moving Bodies');

console.log(bookList);
```

:heavy_check_mark: bookList should not change and still equal ["The Hound of the Baskervilles", "On The Electrodynamics of Moving Bodies", "Philosophiæ Naturalis Principia Mathematica", "Disquisitiones Arithmeticae"].<br/>
:heavy_check_mark: newBookList should equal ["The Hound of the Baskervilles", "On The Electrodynamics of Moving Bodies", "Philosophiæ Naturalis Principia Mathematica", "Disquisitiones Arithmeticae", "A Brief History of Time"].<br/>
:heavy_check_mark: newerBookList should equal ["The Hound of the Baskervilles", "Philosophiæ Naturalis Principia Mathematica", "Disquisitiones Arithmeticae"].<br/>
:heavy_check_mark: newestBookList should equal ["The Hound of the Baskervilles", "Philosophiæ Naturalis Principia Mathematica", "Disquisitiones Arithmeticae", "A Brief History of Time"].
<br/><br/>
## challenge #7:
##### Functional Programming: Use the map Method to Extract Data from an Array

:heavy_exclamation_mark: The global variable "watchList" is [here](https://github.com/zelol/seb-freecodecamp/blob/master/functional-programming/watchList.md).

```
// Add your code below this line

var rating = [];

rating = watchList.map(function(elem){
  return { title: elem.Title, rating: elem.imdbRating }
});

// Add your code above this line

console.log(rating); 
```

:heavy_check_mark: The watchList variable should not change.<br/>
:heavy_check_mark: Your code should not use a for loop.<br/>
:heavy_check_mark: Your code should use the map method.<br/>
:heavy_check_mark: rating should equal [{"title":"Inception","rating":"8.8"},{"title":"Interstellar","rating":"8.6"},{"title":"The Dark Knight","rating":"9.0"},{"title":"Batman Begins","rating":"8.3"},{"title":"Avatar","rating":"7.9"}].
<br/><br/>
## challenge #8:
##### Functional Programming: Implement map on a Prototype

```
// the global Array
var s = [23, 65, 98, 5];

Array.prototype.myMap = function(callback){
  var newArray = [];
  // Add your code below this line

  this.forEach(function(elem, index, arr){
    newArray.push(callback(elem));
  });
  
  // Add your code above this line
  return newArray;

};

var new_s = s.myMap(function(item){
  return item * 2;
});
```

:heavy_check_mark: new_s should equal [46, 130, 196, 10].<br/>
:heavy_check_mark: Your code should not use the map method.
<br/><br/>
## challenge #9:
##### Functional Programming: Use the filter Method to Extract Data from an Array

:heavy_exclamation_mark: The global variable "watchList" is [here](https://github.com/zelol/seb-freecodecamp/blob/master/functional-programming/watchList.md).

```
// Add your code below this line

var filteredList;

filteredList = watchList
.filter(function(elem){ return Number(elem.imdbRating) >= 8 })
.map(function(elem){ return { "title": elem.Title, "rating": elem.imdbRating } });

// Add your code above this line

console.log(filteredList); 
```

:heavy_check_mark: The watchList variable should not change.<br/>
:heavy_check_mark: Your code should use the filter method.<br/>
:heavy_check_mark: Your code should not use a for loop.<br/>
:heavy_check_mark: filteredList should equal [{"title": "Inception","rating": "8.8"},{"title": "Interstellar","rating": "8.6"},{"title": "The Dark Knight","rating": "9.0"},{"title": "Batman Begins","rating": "8.3"}]
<br/><br/>
## challenge #10:
##### Functional Programming: Implement the filter Method on a Prototype

```
// the global Array
var s = [23, 65, 98, 5];

Array.prototype.myFilter = function(callback){
  var newArray = [];
  // Add your code below this line
  
  this.forEach(function(elem){
    if(callback( elem )) { newArray.push(elem); }
  });

  // Add your code above this line
  return newArray;

};

var new_s = s.myFilter(function(item){
  return item % 2 === 1;
});
```

:heavy_check_mark: new_s should equal [23, 65, 5].<br/>
:heavy_check_mark: Your code should not use the filter method.
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
