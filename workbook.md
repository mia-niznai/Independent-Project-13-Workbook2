# Web Module Questions

### Functional patterns

:question: **1. What is a callback function?**
* A callback function is passed to another function as an argument and it is executed after that function is invoked. Frequently, callback functions are used to continue code after an asyncronous operation was completed (asyncronous callbacks).

```
async function fetchData(callback) {
    const response = await fetch("fetchLINK");
    const json = await response.json();
    callback(json);
  }

  useEffect(() => {
    fetchData(setData);
  }, []);
```

:question: **2. What is ECMA script ? What is the difference between Javascript & ECMA script ?**

* JavaScript is a programming language initially created by Netscape, whistl ECMAScript consists of specifications (syntax, semantics, structure) for a scripting language created by European Computer Manufacturers Association (ECMA). JavaScript is one implementation based on ECMAScript standards.

-:question: **3. What is the difference between `let` & `var` ?**

* The `let` variables only work inside the block where they are defined (they are blocked-scoped variables). 
On the other hand, the `var` variables are function-scoped variables that, if defined inside a function, are accesible anywhere in that function (including nested blocks or loops), and if they are defined globally, they are accesible globally (in any function, any loop, any block of code).   
Also, `let` variables are a EcmaScript6 features, and `var` variables are a ECMAScript1 feature (the `let` and `const` are modern alternatives included in more recent standards, in order to have better control over variable scoping and to prevent common programming errors).

:question: **4. Write an example where using the `var` declaration instead of the `let` could create a hard to debug code.**

:black_nib:
|                                                                         var                                                                        |                                                                         let                                                                        |
|:--------------------------------------------------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------:|
| function printNumbers(){<br>var num = 10;<br><br>if (true){<br>var num = 20;<br>}<br><br>console.log(num)<br>}<br><br>printNumbers() // Output: 20 | function printNumbers(){<br>let num = 10;<br><br>if (true){<br>let num = 20<br>}<br><br>console.log(num);<br>}<br><br>printNumbers() // Output: 10 |


:question: **5. Give a practical example where you would use the `reduce` function in javascript.**

:black_nib: We can use `reduce` to calculate the sum of all numbers in an array.

```
const numbers = [1, 2, 3, 4, 5];

const sum = numbers.reduce((accumulator, currentValue) => {
  return accumulator + currentValue;
}, 0);

console.log(sum); // Output: 15
```

:question: **6. Give a practical example where you would use the `map` function in javascript.**

:black_nib: We can use `map` to transform each element of an array into another (Celsius degrees into Fahrenheit degrees).
```
const celsiusTemperatures = [0, 10, 20, 30, 40];

const fahrenheitTemperatures = celsiusTemperatures.map((celsius) => {
  return (celsius * 9/5) + 32;
});

console.log(fahrenheitTemperatures); // Output: [32, 50, 68, 86, 104]
```

:question: **7. Give a practical example where you would use the `filter` function in javascript.**

:black_nib: We can use `filter` to create a new array according to our criteria.

```
const people = [
  { name: 'Alice', age: 25 },
  { name: 'Bob', age: 30 },
  { name: 'Charlie', age: 35 },
  { name: 'Dave', age: 40 },
  { name: 'Eve', age: 45 },
];

const peopleOver35 = people.filter(person => person.age > 35);

console.log(peopleOver35); // Output: [ { name: 'Dave', age: 40 }, { name: 'Eve', age: 45 } ]
```

### Web basics

:question: **8 What is a web server?**

*A web server can refer to hardware or software or both.
Commonly, a web server is a software application that receives requests from the clients, processes the data and sends back responses for requested content.

:question: **9 Explain the client-server architecture.**

* According to `Simplilearn.com`, in the IT context, the client is a computer/phone/tablet/device, also called a Host, that uses the service and accepts information. The server is a remote computer that provides access to data and services.
* According to `Wikipedia.com`, the client–server model is a distributed application structure that partitions tasks or workloads between the providers of a resource or service, called servers, and service requesters, called clients.
* In conclusion, the client-server architecture describes the model in which one ore more clients (machines) request and receive services and data from a server over a network.


:question: **10 What is the difference between synchronous and asynchronous execution?**

* According to `Stackoverflow.com`, when you execute something synchronously, you wait for it to finish before moving on to another task. When you execute something asynchronously, you can move on to another task before it finishes.
* When you execute code or processes in a computer program, in the synchronous execution, the program waits for each line of code to be completed in sequence. In contrast, in asynchronous execution, the program moves on to the next code regardless of the stage of execution for the previous code.

:question: **11 What is `npm`? Why is it useful?**

*  `npm` is a package manager for Node.js that allows developers to install and manage third-party packages and dependencies for their `Node.js` projects. Developers can specify the dependencies required for their project in the `package.json` file, and then use the `npm install` command to automatically download and install all the required packages and their dependencies.

:question: **12 What is the difference between the `depdendencies` & `devDependencies` in a `package.json` file?**

* Dependencies are packages required for the application in production, whistl devDependencies are packages needed for local development and testing.

:question: **13 What would be the impact of javascript `fetch` if it was not asyncronous?**

* If `fetch()` was not asynchronous, the program would have to wait for the fetch response and the code would not be executed until getting that response, which would make the page slow and unresponsive.

:question: **14 What benefits would bring to a developer to use the `Postman` application?**

* `Postman` is helping developers to save time and effort when building and testing API. Using Postman, you can test, you can collaborate, you can debug, you can understand easier the API documentation.

:question: **15 List the parts of the URL.**

:black_nib: An URL (Uniform Resource Locator) has the following parts:

* [x] a scheme (examples: `http://`, `https://`, `ftp://`, `file://`)
* [x] a domain or host (example: `www.site.com`)
* [x] a top-level domain (examples: `.edu`, `.com`, `.org`, `.net`)
* [x] a second-level domain (what is between www and domain; in previous example: site)
* [x] an optional subdomanin (example: `blog.site.com`)
* [x] a path (example: `/index.html`)
* [x] optional query string(s) (parameter(s) or data in the URL)
* [x] an optional fragment identifier (section or resource preceded by `#` in and URL)

:question: **16 What is query parameter?**

* According to `Branch.io`, query parameters are a defined set of parameters attached to the end of a url. They are extensions of the URL that are used to help define specific content or actions based on the data being passed. 
* To append query params to the end of a URL, a `?` or `?q=` is added, followed by a query parameter. 
* To add multiple parameters, an `&` is added in between each. 
* A query parameter consists of a key-value pair.

`https://example.com/path?name=Branch&products=[Journeys,Email,Universal%20Ads]`
`https://example.com/search?q=apple&category=fruit`

:question: **17 What kind of HTTP status codes do you know?**

* [x] Informational responses (100 – 199)
* [x] Successful responses (200 – 299)
* [x] Redirection messages (300 – 399)
* [x] Client error responses (400 – 499)
* [x] Server error responses (500 – 599)

:question: **18 How does an HTTP Request look like? What are the most relevant HTTP header fields?**

* Here are the most relevant HTTP request components (including headers):

* [x] request method: `GET`, `POST`, `PUT`, `PATCH`, `DELETE`
* [x] request URL 
* [x] request headers: `Content-Type`: `application/json`; `User-Agent`; `Accept`; `Authorization`
* [x] request body 

:question: **19 How does an HTTP Response look like? What are the most relevant HTTP header fields?**

* Relevant components (and headers) for HTTP response:

* [x] status code: informational responses (100 – 199); successful responses (200 – 299); redirection messages (300 – 399); client error responses (400 – 499); server error responses (500 – 599);
* [x] reason phrase (a human-readable explanation for the status code before)
* [x] response headers: `Content-Type`: `application/json`; `Access-Control-Allow-Origin`; `Access-Control-Request-Method: GET`, `Accept-Language`; `User-Agent`;
* [x] response body

:question: **20 Why should you ignore the `node_modules` folder in `.gitignore` ?**

* It is better to put the `node_modules` folder in the `.gitignore` file because it gets too much space from the Git repository (the folder has a large size). It is enough to have them in the "package.json" so that you can use npm install and get them again when you need them. Also, it is better for the security of the project to include the "node_modules" in the ".gitignore" file.


### Rest API: Serve and Fetch

:question: **21 Why is it recommend for a developer to use the http methods `get`, `put`, `delete`?**

* HTTP methods are secure and efficient ways to work with data on a server.
* We use the `GET` method to retrieve data.
* We use the `PUT` (or `PATCH`) method to update data.
* We use `DELETE` method to delete data.

:question: **22 How does a `POST` request look like when it is made from a web browser (on the frontend written)?**

:black_nib:
```
<form method="POST" action="/submit-form">
  <label for="name">Name:</label>
  <input type="text" id="name" name="name"><br>

  <label for="email">Email:</label>
  <input type="email" id="email" name="email"><br>

  <label for="message">Message:</label>
  <textarea id="message" name="message"></textarea><br>

  <button type="submit">Submit</button>
</form>
```

:question: **23 What is an API?**

* API (Application Programming Interface) is a set of definitions, protocols, routines and tools for building and integrating application software (source: `Redhat.com`).
* According to `Ibm.com`, an application programming interface is a set of rules that define how applications or devices can connect and communicate with each other.

:question: **24 What is REST API?**

* REST APIs or RESTful APIs follow the principles and procedures of the Representational State Transfer architectural style for web services.
* The client (browser/ device) communicates with the server (application/ service) in a flexible and standardized way, using almost any programming language and data formats.

:question: **25 What is JSON and how do we use it?**

* JavaScript Object Notation (JSON) is a text-based way of representing JavaScript object literals, arrays, scalar data (source: `Oracle.com`).
* JSON format is both easy for humans to read and write and for the machines to parse and generate, and it can be used with any programming language.
* In order to use JSON, we convert data from the programming language that we use into JSON string or data structure, with the help of a JSON encoder, and we store it into a file.

:question: **26 What is API versioning?**

* API versioning allow developers to make changes to an API without breaking the clients' apllications that rely on that API. 
* The changes can be integrated in URL versioning (include change in API Url), query versioning (include change in API parameter), header versioning (include change in header) and media type versioning (include change in media type of response).

:question: **27 Give 3 examples of HTTP response status codes. Explain what each number means.**

* From 201 to 299: message indicates succes in retrieving the data. Example: `200 OK`.
* From 401 to 499: message indicates error on client side and that the server is unable to find the requested data. Example: `404 not find`.
* From 501 to 599: message indicates error on server side. Example: `500 Internal Server Error`.

### Advanced JavaScript

:question: **28 How does the `ternary operator` looks like in javascript?**

* According to MDN (`developer.mozilla.org`), the conditional (ternary) operator is the only JavaScript operator that takes three operands: a condition followed by a question mark (?), then an expression to execute if the condition is truthy followed by a colon (:), and finally the expression to execute if the condition is falsy.

:black_nib:

`condition ? expression1 : expression2`

:question: **29 How to import a function from another module in JavaScript?**

* We can use `import` statement to import a function from another module (from which we export the function using the `export` statement).

:black_nib: Example from `Stackoverflow.com`:
* models/course.js
```
export function Course() {
    this.id = '';
    this.name = '';
};
```
* models/student.js
```
import { Course } from './course.js';

export function Student() {
    this.firstName = '';
    this.lastName = '';
    this.course = new Course();
};
```
* index.html
```
<div id="myDiv">
</div>
<script type="module">
    import { Student } from './models/student.js';

    window.onload = function () {
        var x = new Student();
        x.course.id = 1;
        document.getElementById('myDiv').innerHTML = x.course.id;
    }
</script>
```

:question: **30 What is a shallow copy on an object?**

* A shallow copy (or shallow clone) of an object can be created with the spread operator (`...`) and it will generate a new object which properties will use the same memory space as the ones of the original object. This way, if we change a property value of the copy we also change the property value of the original.
* Another way to create a shallow clone is with `Object.assign()` or `slice()`.
* In order to create a copy that doesn't use the same memory space, we need to create a deep copy (deep clone), using the `JSON.parse()` and `JSON.stringify` methods.

:question: **31 What is a callback function? Tell some examples of its usage.**

* I already gave an example at :question:1

* In JavaScript, a callback function is a function that is passed as an argument to another function, and is executed when a certain event or action occurs. The main purpose of a callback function is to allow a function to be more flexible and reusable, by allowing different behaviors to be passed as arguments.

:black_nib: Example:
```
document.querySelector('button').addEventListener('click', function() {
  // Do something when the button is clicked
});
```

```
const numbers = [1, 2, 3, 4, 5];

const doubledNumbers = numbers.map(function(number) {
  return number * 2;
});

console.log(doubledNumbers);
```

:question: **32 What is object destructuring in JavaScript?**

* According to `Tutorialspoint.com`, JavaScript Object Destructuring is an expression which allows us to access the data from objects and assign it to new variables. Through this object destructuring, we can create variables easily from the object’s properties. 

* Syntax:
```
const [a,b] = array;
const [a,b…t] = array;

const {a:a1,b:b1} = obj;
const {a:a1, b:b1,…..t:t1} = obj
```

:black_nib: Example:
```
const person = {
  name: 'John Doe',
  age: 30,
  address: {
    street: '123 Main St',
    city: 'Anytown',
    state: 'CA',
    zip: '12345'
  }
};

// Extract properties using destructuring
const { name, age, address: { city } } = person;

console.log(name);  // 'John Doe'
console.log(age);   // 30
console.log(city);  // 'Anytown'
```

:question: **33 What is array destructuring in JavaScript?**

* With the help of array destructuring we can extract element from an array and assign them to new variables at the same time.

:black_nib: Example:
```
const array = [1,2,3,4,5];
const [a,b] = array; // a : 1 , b :2 (values of a,b)
```

:question: **34 What is the spread operator in `js`?**

* The spread operator (`...`) allows us to create a shallow copy of an array or object or iterable at at the same time to expand it in individual elements.

:black_nib: Example:
```
const numbers = [1, 2, 3, 4, 5];

function sum(a, b, c, d, e) {
  return a + b + c + d + e;
}

const result = sum(...numbers);

console.log(result); 
```

:question: **35 What are the differences between the `arrow` function and the regular `function`?**

|          **Differences**         |                                                     **Arrow function**                                                    |                                             **Regular function**                                             |
|:--------------------------------:|:-------------------------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------:|
|            **Syntax**            | const arrowFunction = (x, y) => {return x+y};<br>or, also possible and even better:<br>const arrowFunction =(x,y) => x+y; | function regularFunction (x, y){<br>return x+y;}                                                             |
|       **Arguments binding**      | No argument binding.                                                                                                      | Yes.<br>let myFunction(){<br>showArgs(){<br>console.log(arguments)<br>}<br>}<br>myFunction.showArgs(1,2,3,4) |
| **Acceptance of "this" keyword** | No.                                                                                                                       | Yes.                                                                                                         |
|      **Acceptance of "new"**     | No.                                                                                                                       | Yes.                                                                                                         |
|     **Duplicate parameters**     | Never.                                                                                                                    | Only in non-strict mode.                                                                                     |

:question: **36 What is the `import` keyword used for?**

* The `import` keyword is used to include external modules or dependencies into a JavaScript file in frontend.

:question: **37 What is the `require` used for?**

The `require` keyword is used to include external modules or dependencies into a JavaScript file in backend.

:question: **38 What are template literals?**

* Template literals (template strings) allow us to embed expressions and variables inside a string using backticks instead of single or double quotes.

### Testing basics

:question: **39 What is code coverage? Why is it used?**

* Code coverage indicates the proportion of lines, functions and branches of the code that were covered by a test. It helps to measure how much of the code has been tested.

:question: **40 What is a test case? What is an assertion? Give examples!**

* A test case is a scenario that defines the input values, expected output, and any other relevant conditions or requirements for a test.
* An assertion is a statement that checks whether an expected condition is true or false.

:black_nib: Example: 

```
Test Case:
A login form that accepts a username and password.

Assertions:

When the correct username and password are entered, the user should be logged in successfully.
When an incorrect username or password is entered, the user should not be logged in.
When the login form is submitted without any input, an error message should be displayed.
```

:question: **41 What are the unit testing best practices? (Eg. how many assertion should a test case contain?)**

:black_nib: Some rules to follow:

* [x] include a single assertion in one test method (test one thing at a time; one assertion per test case)
* [x] use clear test cases
* [x] run tests frequently
* [x] write tests during development


:question: **42 What is arrange/act/assert pattern?**

* The Arrange-Act-Assert (AAA) pattern is used in unit testing to structure and organize test cases.

:question: **43 How do you test asynchronous code with `jest` ?**

* We can test asynchronous with `jest` using:
* [x] `done()`
* [x] `promises`
* [x] `async/ await`
* [x] `done()` + `async/ await`

:question: **44 What is `setup` & `teardown` in jest?**

* In `jest`, `setup` and `teardown` are functions that we can use to define actions to be performed before and after running every test.

:question: **45 Give an example when you would use in `jest` the `toBe` & `toEqual` assertions.**

* The `toBe` assertion tests for strict equality between two values.

:black_nib: Example:
```
test('addition works correctly', () => {
  expect(3 * 3).toBe(9);
});
```

* The `toEqual` assertion, on the other hand, tests for deep equality between two values. 

:black_nib: Example:
```
test('objects are equal', () => {
  const obj1 = { foo: 'bar', baz: 3000 };
  const obj2 = { foo: 'bar', baz: 3000 };
  expect(obj1).toEqual(obj2);
});
```

### React basics

:question: **46 What benefits does it bring for a developer to use `components` (opposed of writing all the code in a single file)?**

* Some benefits of using components instead of writing all code in one place:
* [x] code is more suple and easy to follow
* [x] it is easier to test/ debug the code
* [x] it is easier to re-use the code
* [x] it is easier to collaborate
* [x] makes things more clear and helps the logic
* [x] it is easier to make changes in the code

:question: **47 What is the difference between Element and Component?**

* Usually, an element refers to a HTML tag, whistl a component is more complex and dynamic and encapsulates more elements.

:question: **48 How do you pass values between components in `react`?**

* To pass values between components in React, we can use:
* [x] props
* [x] useContext
* [x] specific libraries
* [x] event handling

:question: **49 What is `key` prop?**

* When working with a list and using `.map()` we need to include a key so that React keeps track more efficiently of what we changed, added or deleted from the list.

:black_nib: Example: 

```
function MyList(props) {
  const items = props.data.map((item) => (
    <li key={item.id}>
      {item.name}
      <ul>
        {item.children.map((child) => (
          <li key={child.id}>{child.name}</li>
        ))}
      </ul>
    </li>
  ));
  return <ul>{items}</ul>;
}
```

:question: **50 How does a child component pass data to it's parent component?**

* To pass data from a child component to its parent component, we can use props or useContext.

:question: **51 Write the code to create in JSX an HTML DIV element that has the innerText the contents of the variable `let name = 'Andrew'`**

:black_nib: Example: 

```
import React from 'react';

function MyComponent() {
  let name = 'Andrew';

  return (
    <div>{name}</div>
  );
}

export default MyComponent;
```

:question: **52 Write the code to create in JSX an unordered list from the array `let names = ["Mathew", "John", "Maverik"]`**

:black_nib: Example:
```
import React from 'react';

function MyComponent() {
  let names = ["Mathew", "John", "Maverik"];

  return (
    <ul>
      {names.map((name) => (
        <li key={name}>{name}</li>
      ))}
    </ul>
  );
}

export default MyComponent;
```

:question: **53 Write the code to set the background color red of a div in JSX.**

:black_nib: Example:
```
import React from 'react';

function MyComponent() {
  return (
    <div style={{ backgroundColor: 'red' }}>Hello, world!</div>
  );
}

export default MyComponent;
```

### Testing react

:question: **54 What are unit tests, integration tests? What is the major difference between these two?**

* Unit tests are used to test a single unit or function of an application.
* Integration tests are used to test the interaction between different parts of an application.

:question: **55 What is unit testing?**

* Unit testing is designed to test individual units or components, isolated from the rest of the application.

:question: **56 What does `mocking` mean from a testing perspective ? Give an example when you would use it.**

* When testing, mocking means to create a simulated version for the data that the code we want to test relies on.
* A frequent example of recently used mocking was to add data to see it create-read-update-delete operations work as expected.

:question: **57 How do you test that function was called `at least` 2 times using `jest`?**

:black_nib: Example:
```
function myFunction() {
  // ...
}

// Test case
test('myFunction is called at least 2 times', () => {
  // Call the function twice
  myFunction();
  myFunction();

  // Assert that the function was called at least 2 times
  expect(myFunction).toHaveBeenCalledTimes(2);
  expect(myFunction).toBeGreaterThanOrEqual(2);
});
```

:question: **58 Name 4 benefits a developer gets from writing tests.**

:black_nib: Some benefits for a developer to write tests:

* [x] catch and prevent bugs
* [x] better structure the code
* [x] prevent isssues in an early stage

### React patterns

:question: **59 What is the difference between Real DOM and Virtual DOM?**

| **Differences** |                       **Real DOM**                       |                      **Virtual DOM**                      |
|:---------------:|:--------------------------------------------------------:|:---------------------------------------------------------:|
|        1        | Represents the current stage of the web page.            | Represents a copy of the Real DOM that was stored.        |
|        2        | Can change on-screen elements.                           | Cannot change on-screen elements.                         |
|        3        | Any change updates the entire DOM structure.             | Any change only updates the relevant node.                |
|        4        | Slow update.                                             | Fast update.                                              |
|        5        | Browser re-renders the entire page to reflect an update. | Framework updates only the changed parts of the Real DOM. |

:question: **60 When adding an item to an array, why is it necessary to pass a new array to the `useState` hook?**

* When we update an array, the state variable is updated too and a new copy of the variable is created instead of changing the original, in order to be able to re-render the component.

:question: **61 Describe what techniques or tools you use to debug a react app.**

:black_nib: Techniques and tools that we use to debug a React application:
* [x] add console.log() statements everytime we need
* [x] use browser's debugger
* [x] use VSC debugger
* [x] get help from colleagues and mentors

:question: **62 What is the difference between a react `class` component & a `functional` component?**

* A functional component is an easy to read, write and test component that consists of a function where we can use React hooks (useState, useEffect).
* A class component usses `class` keyword and extends `React.Component` and uses render() method.

:question: **63 Name 3 lifecycle states in a react `functional` component.**

:black_nib: Three lifecycle states in a React functional component:
* [x] useState
* [x] useEffect
* [x] useContext

:question: **64 What is conditional rendering in `react` ? Give an example.**

* Conditional rendering means to render different parts of the code based on certain conditions.

:black_nib: Example from `legacy.reacjs.org`:
```
render() {
  const count = 0;
  return (
    <div>
      {count && <h1>Messages: {count}</h1>}
    </div>
  );
}
```

:question: **65 Write the code that prints to the console `component destroyed` when the component it is part of is removed from the DOM tree.**

```
import React, { useEffect } from 'react';

function DestroyedComponent() {
  useEffect(() => {
    return () => {
      console.log('component destroyed');
    };
  }, []);

  return (
    <div>
      <h1>Destroyed component</h1>
      <p>This is my component</p>
    </div>
  );
}

export default DestroyedComponent;
```

:question: **66 Why is there an infinite loop in this code?**

```function App() {
  const [count, setCount] = useState(0); //initial value of this 
  useEffect(() => {
    setCount((count) => count + 1); //increment this Hook
  }); //no dependency array.
  return (
    <div className="App">
      <p> value of count: {count} </p>
    </div>
  );
}
```
* The useEffect hook should have a dependency array, in this case [count], in order to only render when the count is changed.

:question: **67 Why is there an infinite loop in this code?**

```
  async function App() {
  const [count, setCount] = useState("");
  setCount(count + 1);
  return (
    <div className="App">
      <p> value of count: {count} </p>
    </div>
  );
}
```
* The first problem is that the initial state of the useState hook is set to a string, which is not correct for a count (should be a number or should be set to 0 or null).
* Another problem is that the setCount should depend on a function or a button handler or a condition - so that we know when to increment the count.
* Also, it is enough to write count++ instead of count+1.

:black_nib: The reviewed version for the code should be something like this: 
```
function App() {
  const [count, setCount] = useState(0);

  const incrementCount = () => {
    setCount(count + 1);
  };

  return (
    <div className="App">
      <p> value of count: {count} </p>
      <button onClick={incrementCount}>Increment</button>
    </div>
  );
}
```

### Mongo & mongoose

:question: **68 What is a database schema?**

* A database schema in MongoDB describes the structure of data and specifies hot to store the data, what type is the data and so on.

:question: **69 Why is the `id` unique in a database?**

* Every ObjectId in MongoDB is generated automatically and is unique, because the `_id` field is the primary key for each document, in order to efficiently retrieve the document from a collection.

:question: **70 What are the advatanges & disadvatages of using `lean()` function in a mongo query?**

| **lean() method in Mongoose** |   **Advantages**   |   **Disadvantages**   |
|:-----------------------------:|:------------------:|:---------------------:|
|               1               | faster             | limited functionality |
|               2               | use less memory    | no schema validation  |
|               3               | better performance | no data manipulation  |

:question: **71 Write the code to store the object `{name: "Andrew", age: 10}` to a mongo database. You can ignore the part of connection parameters.**

```
const mongoose = require('mongoose');

const personSchema = new mongoose.Schema({
  name: String,
  age: Number
});

const Person = mongoose.model('Person', personSchema);

// Connect to the database (you can ignore the connection parameters)
mongoose.connect('mongodb://localhost/...');

// Create a new user object
const person = new Person({
  name: 'Andrew',
  age: 10
});

// Save the user to the database
person.save((err, person) => {
  if (err) {
    console.error(err);
  } else {
    console.log(`User ${person.name} saved to the database.`);
  }
});
```

:question: **72 Write the code to delete from a mongo database all employees that are over 18 years. The scheme for an employee is `{name: string, age: int}`. You can ignore the part of connection parameters.**

:question: **73 Write the code to display in the console from a mongo database the employees who are over 18 years. The scheme for an employee is `{name: string, age: int}`. You can ignore the part of connection parameters.**

:question: **74 Write the code to update from a mongo database the employees with name='John' and set the new age to 8. The scheme for an employee is `{name: string, age: int}`. You can ignore the part of connection parameters.**


### Authentication (cookies + google)

:question: **75 How to properly store passwords?**

:question: **76 What is encryption and decryption?**

:question: **77 What is hashing?**

:question: **78 What is OAuth2?**

:question: **79 What is the difference between encryption and hashing? When would you use which?**

:question: **80 How/where would you store sensitive data (like db password, API key, ...) of your application?**

:question: **81 What would you use a session for?**

:question: **82 What would you use a cookie for?**

### Mern stack

:question: **83 What does `MERN` stand for in the context of web development?**

* MERN stands for Mongoose-Express-React-Node.

:question: **84 What is routing in the context of a `react` app?**

* In the context of React, routing means to determine what should be displayed in a given URL path.

:question: **85 What is routing in the context of an `express` app?**

* In the context of Express, routing means to determine which server-side function should handle a specific HTTP request using a HTTP method.

:question: **86 What is `CORS` policy?**

* CORS (Cross-Origin Resource Sharing) policy is a security mechanism designed to prevent malicious scripts from stealing or manipulating data from sites.

```
app.use((req, res, next) => {
  res.setHeader('Access-Control-Allow-Origin', '*');
  res.setHeader('Access-Control-Allow-Methods', 'GET, POST, PUT, DELETE');
  res.setHeader('Access-Control-Allow-Headers', 'Content-Type');
  next();
});
```

:question: **87 What advantages does a developer have for using `bootstrap` or `material ui`?**

