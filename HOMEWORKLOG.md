Please note that the functions or methods that I write about are ones that I had to research because I have not encountered before or forgot what they did. I have also included my current questions and understandings (or misunderstandings) about them.

## About Expects ##
Did okay on "about arrays" section. I won't lie, it is weird to only be looking at tests, but I'm getting used to it.
* Do not understand when it says "expected false to be truthy" and we replace false with truth. Why are we not replacing it with "truthy?"

## About Arrays ##
* It should create arrays: Expected 4 to be "Fill this value in"
  * Took me a while to figure out that this was part of an object, so that is why we needed to put the key (value1)

* It should understand length.
  * Expected 10 to be 'Fill this value in'.
    * Did not realize that if you give a variable a name and then add new Array(#), you will create an array with that amount of empty slots. So cool.
  * Expected [ 'peanut' ] to equal 'Fill this value in'.
    * What happens if you have items in an array, but then you change its length with .length = #, and you put less or more numbers than in the array....?
      * Figured this out. If you give a number bigger than the length, it does not do anything. If you give it a number shorter than the actual length, it cuts off the last array items.

* It should slice arrays.
  * Expected [  ] to equal 'Fill this value in'.
    * Do not understand what 'backwards' splicing does (with the higher number listed first and a lower number listed next)

* It should know about shifting arrays.
  * Learned about arr.unshift. It add elements to the beginning of an array.
  * Learned about arr.shift. It removes the first element and returns that element. This is helping me understand what some methods return, as long as you assign them to a variable or "return" them.

## About Functions ##
* It should allow extra function arguments.
  * Expected 'first' to be 'Fill this value in'.
    * I can see how the answer was determined, but this is one that would probably trip me up. I think this would be difficult to write on my own or understand without prompts.

* It should allow extra function arguments.
  * Expected 'first,second,third' to be 'Fill this value in'.
    * I did not realize that "arguments" was a key word, and I can use that as a parameter for when I call the function. It took me a little while to understand how the function new what "arguments" length was if it was not declared. It's because it's a reserved word and is talking about the arguments when called.
    * Reminder! Don't forget about spaces (or lack of) when you join or split something.

  * It should pass functions as values.
    * Expected 'John rules!' to be 'Fill this value in'.
      * I understand that var praiseSinger is creating an object with the key of 'give praise' and the value of 'append rules', but I don't know how you could tell that it is a function. My first instinct is to say that since it is not in quotation marks, it is something that is already defined, so it would have to be an object, array, function, etc., so you would just have to find which one it was.
      * I have trouble following how to call for items in objects and the different notations.

## About Mutability ##
* I am seeing a similarity between creating objects and constructors. When we create a constructor function and use this.text = text, it looks like we are creating key/value pairs.

* It should expect prototype properties to be public and mutable.
  * I am getting confused following this process. On line 58, I do not understand why we have to use the method "getFullName," if we are not going to use it. Are we even using that method?
    ``` js
    it("should expect prototype properties to be public and mutable", function () {
    function Person(firstname, lastname)
    {
      this.firstname = firstname;
      this.lastname = lastname;
    }
    Person.prototype.getFullName = function () {
      return this.firstname + " " + this.lastname;
    };

    var aPerson = new Person ("John", "Smith");
    expect(aPerson.getFullName()).toBe('John Smith');

    aPerson.getFullName = function () {
      return this.lastname + ", " + this.firstname;
    };

    expect(aPerson.getFullName()).toBe('Smith, John');
  });
  ```

* It should know that variables inside a constructor and constructor args are private.
  * I do not quite understand what is going on here, but here are my assumptions. Since the constructor created a function within itself, if we want to change a variable, we have to call the method in the constructor. For example, if we wanted to change the first name to Penny, we would have to:
  ``` js
    var aPerson = new Person ("John", "Smith");
    aPerson.getFirstName.firstname = "Penny";
  ```
  But I am not sure if that is correct. The last exercise calls for the constructor (because aPerson was = to new Person), and then get full name was called. Since aPerson.first/lastname were declared about as Penny and called for in the function, that is what will be returned.

  * This article is helping me out a lot.
    * [CSS Ticks: Understanding Constructors](https://css-tricks.com/understanding-javascript-constructors/)

## About Higher Order Functions ##
* It should use filter to return array items that meet a criteria.
  * .filter is used to make a new array. The items it is filled with are based on the callback function. If an item is returned as true in the callback function, it joins the array. If not, it is ignored.
  * I don't know what the underscore(variable) means, but I am assuming that it is saying "the following anonymous function will use these parameters...?"

* It should use 'map' to transform each element.
  * .map is a function that takes every element of an array and calls a function for each element. .map returns a new array with the results of each function call(result) in it.

* It should use 'reduce' to update the same result on each iteration.
  * .reduce tries to turn an array with different numbers into an array with a single number. To do this is names the array, calls for reduce, and then calls for the function that we want to run each element on.
    arr.reduce(callback function, first function parameter(optional))
  * I do not know what memo is, even with the included comments. I understand that it is in the function we will be "calling back", or in this case using, and we will start using this function on the element in position 0 in our array. But the function is hard to understand. I am thinking that memo is like total. If we don't have a total, we assume it is 0. So then we add 0 plus the current array number, which would be 1 since we are on position 0.
  * Still confused about the difference between toBe and toEqual.

* It should use 'forEach' for simple iteration.
  * I don't quite understand '.forEach.' This is what I think I know about it. 'forEach' takes an array and, just like map, calls a function for each element in order. The difference is that '.map' actually returns an array with the values it produces. '.forEach' does not return anything unless you specifically make it; therefore, you have more control of what you want to return as a result of going through each element in the array. I think...
  * This article helped me understand the differences between forEach and map. [Article](https://medium.com/@prufrock123/foreach-map-in-javascript-3381017a6155#.2ewsjprhg)
  * I still don't understand why it is using "underscore(numbers)" instead of just stating the array (aka numbers)

* It should use 'all' to test whether all items pass condition.
  * I am only seeing information on ".all" in relation to Promises. I don't know if a promise specifically has to say promise to be one? From the tests, I am assuming that .all means that the return will be true or false based on whether all the items in an array pass the test in a function.
    array.all(function to be passed)
    return true if all items passed OR false if all items did not pass

* It should use 'any' to test if any items passes condition.
  * I am having difficulty on finding information on .any, but it seems to check and see if any of the items in an array pass a "test" (the given function with a boolean value return), and if any item does, the return is true.

* It should use range to generate an array.
  * ."range" makes an array filled with numbers in ascending order based on how many items were specified to be in that array.
  * When I tried to play with range in the console, I only got back errors that .range is not a function. In the example we used an 'underscore' as the array (or object before the method was called). What can usually be used with the .range method? The test makes since with this, but I don't actually understand how to utilize it outside of this test.
  * I do not understand what the -1 at the end of the third test does. I get that we start from 0 and count down until right before we hit -4, but that negative one does not seem to be doing much...?

* It should use flatten to make nested arrays easy to work with.
  * I cannot find much documentation on '.flatten,' but it seems to concat two arrays together into one array.

* It should use chain() ... .value() to use multiple higher order functions.
  * I definitely did not follow this test. I can see how using  .flatten().map(function(x) { return x+1 } ) would return 6, but I do not understand how the other methods (or higher order functions?) are utilized to return 6.

* What are higher order functions? I started reading about them but quickly got confused.

## About Objects ##
* It should confirm that properties are case sensitive.
  * DON'T FORGET that capitalization is critical!

* It should confirm that when a function is attached to an object, 'this' refers to the object.
  * Whoa! Date.getFullYear() returns the year (local time). So cool.

* Considering 'in' keyword + should have the bomb.
  * 'in': State a property you want to find in an object. If the named property is there, it will return true, if not, it will return false. For example: var example = 'cats' (property) in 'animals'(object);  return = true

* It should know that properties can be added and deleted.
  * delete: Can delete a property(key), just by putting delete [objectName.propertyName]

## About Inheritance ##
#### Thinking About Inheritance ####
* It should be able to call a method on the derived object.
  * '.call': I do not quite fully understand this method. I know that it calls for a constructor and then in the parameter uses this. I do not understand why it uses this in the parameters. Maybe it is because the new parameter being created should be included alongside the other parameters...? I also do not understand the ordering related to the expect.

* It should be able to call a method on the base object.
  * It is hard to follow these functions. What does:
  ``` js
    Muppet.call(this, age, hobby);
    ```
    do in the SwedishChef function? Does it replicate the parameters of Muppet?

* It should set constructor parameters on the base object.
  * This part makes me realize that '.call' plus the parameters of the original constructor (and this to add new parameters), will add the parameters of the constructor to the new function.

#### About Crockford's Inheritance Improvement ####
* It should be able to call a method on the derived object.
  * ".beget" is not documented. Although the comment says, "no longer need to call the Muppet (base type) constructor", I still do not understand what is going on. I am assuming that beget means that Gonzo no longer has to reference Muppet, including functions.

#### About Applying What We Have Learnt ####
* var i,j,hasMushrooms, productsICanEat = [];
  * Are you able to assign more than one variable at a time? What is going on in this line of code?
  * I am going to do my best to explain how to follow this function to get the correct length of "productsICanEat"
    1. You have an array of objects called products. We will look at items in this array in our for loops.
    2. Our for loop starts out with looking at the property containsNuts. If the object does not contain nuts (the value of the property 'contains nuts' is false), then we will assign our variable 'hasMushrooms' to false, but we will double check that in a bit. If the product does not pass the first if statement, then it will not have a chance of being pushed into "productsICanEat"
    3. If the product does not contain nuts, we will move to the next for loop. This for loop looks at each value in the property 'ingredients.' There is more than one value because ingredients is an array. If mushrooms is listed on the ingredients than the array "has mushrooms" is changed to true.
    4. In this if statement on line 31, we are looking for 'hasMushrooms' to NOT be true. If has mushrooms is false, after both for loops, that products object will be pushed into the "productsICanEat" array. If it does have mushrooms, it will not be pushed into the array.  
    5. The only object to pass all the tests is products[1] (the Pizza Primavera1)

* It given I'm allergic to nuts and hate mushrooms, it should find a pizza I can eat (functional).
  * I just want to clarify my thinking. Since products I can eat was "reassigned" as a new variable and is an empty array, the length will be 0.
  * I don't know if the comment on line 42 needs to be regarded as important. I thought my logic of renaming the variable helped me understand why the test passed, but maybe there is something else that I am missing?

* It should count the ingredient occurrence (imperative).
  * I am a little lost on the naming of the var ingredianCount. Why is "ingredient name" being put in curly brackets and quotes? I don't quite understand what the purpose of that is. Are the curly braces indicating that this string will be replaced with something else?
  ``` js
    var ingredientCount = { "{ingredient name}": 0 };
  ```
  * This is the part that is confusing me the most. I cannot decipher figure out why parenthesis are in certain places and why there is an || (or) sign.
    ``` js
          ingredientCount[products[i].ingredients[j]] = (ingredientCount[products[i].ingredients[j]] || 0) + 1
    ```

  * This is what I understand:
    * We are trying to look through the array products to search for how many times a certain ingredient was listed.
    * We use the for loop to cycle through each item in the array. Since each item in the array happens to be an object, we have to have another for loop to look at the values in the ingredient property in the objects.
    * I know that we are trying to add 1 for every instance of the ingredient that was found.

* It should count the ingredient occurrence (functional).
  * Once again, I am assuming that since 'ingredientCount' was renamed as a variable AFTER the for loop functions, it will come up as undefined because it will not be passed through the for loops. But there is yet another mysterious comment on line 84 that seems like it is asking me to apply some methods to this variable. I am not sure what I am supposed to do with this, but I feel like my original logic explains how it is passing the test as undefined. What am I missing?
  * I also still don't understand how I have written ingredient 17 times, but am still spelling it as ingrediant every single time I type it in. Oh boy.


#### Learned ####
* One thing I really want to note that I learned was about underscore javascript. It is a library that has a lot of helpful functions. I would not say that I know how to effectively use it, but I am glad that I am now familiar with some useful functions it provides, such as:
  * .filter: Looks through each item in an array, puts it through a boolean test, and the items that are returned as true are put in a new array.

  * .reduce with memo: reduce turns a list of value into a single value (must be values/numbers). Memo is the "initial state of the reduction." Whatever function is applied with reduce will determine how we create one value from all of the values.

  * .forEach is now referred to as .each: each will go through each item in an array (or object) and apply it to a function (which I think is called the iteratee, yay for new vocabulary). If it passes, you specifically have to give a return since it's default return is undefined.

  * .all is now referred to as .every: .every goes through an array and determines if each element passes a predicate (new vocab again! predicate is a function returning a boolean). If every item in the array is returned as true, then .every returns true.

  * .any is now referred to as .some: .some also sees if items in an array pass a predicate. If ANY of them do, .some returns true.

  * .range: .range will create an array with numbers.
    * underscore.range(5) => [0, 1, 2, 3, 4]
      * It makes an array with the length of 5, starting at 0.
    * underscore.range(2,10) => [2, 3, 4, 5, 6, 7, 8, 9]
      * It makes an array starting at 2 and stopping before 10.
    * underscore.range(0, 10, 2) => [0, 2, 4, 6, 8]
      * It will make an array starting at 0 counting up by twos and stopping before the value 10 is reached.
    * I think I understand range now quite a bit more than when I was working through the koans. Hooray!

  * .flatten: .flatten will take an array and "flatten it to a single level" which means, instead of having arrays withing arrays, it will create one array. It is kind of like concat for strings. If you only want to go down a single level of depth, you then can use flatten(array, true). The true is speaking to "shallow", so it means that you want your .flatten to be shallow and only go down one depth.

#### Vocab ####
* Predicate: 'A predicate is a function that takes one item as input and returns either true or false based on whether the item satisfies some condition.'
  * [Link to where definition was taken](http://codepen.io/Universalist/post/predicates-in-javascript)

#### ES6 updates similart to underscore.js ####
* underscore = each    ES6 = forEach
* underscore = all    ES6 = every
* underscore = any    ES6 = some 
