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
