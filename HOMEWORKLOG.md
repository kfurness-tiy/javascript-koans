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
