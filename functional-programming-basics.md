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


