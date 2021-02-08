# Objects

* Contain key-value pairs; each key maps to a value
* Contain keys which are always strings (or symbols, but it's less common and not important right now)
* Have unique keys; the same key cannot appear twice in an object
* Have their keys point to values which can be of any type

## Object Literals
Some values can be represented by literals: 
* we have string literals like "lighthouse", 
* number literals like 5 and 7.5, etc. 
* Arrays also have a literal syntax using square brackets:
  * [1, 2, 3] is a 3-element array.

**Objects have a literal syntax using braces {}.**
Here is an empty object literal assigned to a variable:
```javascript
const emptyObject = {};
```
And an object literal with a single key-value pair:
```javascript
const tinyObject = { "size": "Tiny" };
```
This object has a single key (the string "size") associated with a value (the string "Tiny").

**Note that while our key size is enclosed in double quotes like a string, it can still be considered a string without the qoutes around it.** So we can save a few characters and make it read nicer by writing this instead:
```javascript
const tinyObject = { size: "Tiny" };
```
## Objects Are Like 2-Column Tables
We can think of an object as a table with two columns.

Objects allow us to easily access the values (in the second column) via a quick reference to their respective keys (in first column).

## Object Values
An object's values can be of any type. The following example shows an object with primitive values:

const myObject = {
  a: 6,     // Number
  b: "abc", // String
  c: true,  // Boolean
  d: null,  // Null
};
## Accessing Object Values
To retrieve a value within an object, use square-bracket notation.
```javascript
const person = { firstName: "Khurram" };
const firstName = person["firstName"]; // get the value associated with the key "firstName"
```
An alternative way to access the same value would be person.firstName.

* Undefined: *Don't use undefined as an object value manually.*

## Assigning a New Value to a Key
Square-bracket notation can also be used to assign new values to new or existing keys.

```javascript
const mary = { name: "Mary Sue" };
mary["name"] = "Mary Jane";
mary["age"]  = 22;
mary // shows the resulting object with both properties
```

## Objects as Values
In addition to primitives (like in the above example), we can nest objects within objects. The key-value pair in an object can have a value that is another object.

```javascript
const person = {
  name: "Paul",
  address: {
    street: "310 W 95th",
    city: "New York",
    zipCode: 10027
  }
};
```
* *Note that square bracket notation can be used to access nested values:*

```javascript
**person["address"]["city"]; // => "New York"**
```

# Object Keys
* How object keys work in Javascript:
  * Keys are always strings
  * Each key is unique (can only occur once in the object)
  * Each key is associated with exactly one value. (Note that technically, an array or another object would count as "one value" here, even though they contain other values.)
  * When writing out object literals, like { myKey: "some value" }, the key is always interpreted as a literal string, even if it's unquoted. It's only necessary to use quotes around the key if the key contains spaces, hyphens or periods. For instance: { "my-hyphenated-key": "some value" }.
    * By convention, we omit the quotes around keys in string literals whenever we can. If the key is a valid variable name, then we don't have to include quotes

The following example shows two ways of specifying the same value in an object literal: using a literal string for the value, or using a variable.
```javascript
const spam = "spam";
person["dislikes"] = { food: spam, "e-mail": "spam" };
```

## Object.keys
To inspect an object's keys, there is a method Object.keys(...) that returns an **array of keys**.


## Summary
We explored the essentials of how to define, access, and manipulate objects in JavaScript. We reviewed the most common way to create objects (const o = {}), accessing and setting properties on objects using string keys (o["key"]) as well as how to get a list of all the keys in an object (Object.keys(o)).

Objects are highly flexible data structures and the foundation of almost everything in JavaScript.

# Objects - Iteration
We have an object, and we want to iterate over each key-value pair.

When iterating over the elements of an array, we can use a loop such as:
```javascript
for (var i = 0; i < 10; i++) {
  // iterating over an array
  console.log(someArray[i]);
}
```
JavaScript objects, {key: value}, themselves are **not** iterable in the way that arrays are. Instead a **for...in** statement is needed.
```javascript
var planetMoons = {
  mercury: 0,
  venus: 0,
  earth: 1,
  mars: 2,
  jupiter: 67,
  saturn: 62,
  uranus: 27,
  neptune: 14
};
```
In the above example, our planetMoons object has 8 keys - one for each planet in our solar system.

* We can traverse all the properties of this object using a for-loop, like so:
```javascript
for (var planet in planetMoons) {
  var numberOfMoons = planetMoons[planet];
  console.log("Planet: " + planet + ", # of Moons: "+ numberOfMoons);
}
```
We have the key available to us within the scope of the loop; in the above example it is the planet variable. 
* Notice how we access the object using a variable, planetMoons[planet]. 
  * The variable planet iterates over each key ("mercury", "venus", ...) using the for-loop.

# Limitations of for ... in
We should be careful with this looping technique, as it can produce some unexpected results. Objects can sometimes have properties that they inherit from their prototype chain as well as method names. An additional filtering step is sometimes necessary:
```javascript
for (var planet in planetMoons) {
  // additional filter for object properties:
  if (planetMoons.hasOwnProperty(planet)) {
    //  ...
  }
}
```
# Conclusion
**Because objects are not iterable like arrays, we have to use another type of loop.** We learned about how to iterate over object properties and values using a **for..in loop**. We saw how to use the hasOwnProperty method to ensure we don't get unexpected results.


