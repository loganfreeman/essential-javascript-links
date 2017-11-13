A curated list of frontend interview questions.

# Table of Contents

  1. [General Questions/Ice Breaker](#general)
  1. [Management Questions](#management)
  1. [JavaScript Questions](#javascript)
  1. [HTML Questions](#html)
  1. [CSS Questions](#css)
  1. [HTTP Questions](#http)
  1. [Problem Solving Questions](#problem-solving)
  1. [Algos, Data Structures, & Computer Science Fundamentals Questions](#algorithms)
  1. [General Evaluation Questions](#general-evaluation-questions)
  1. [React](#react)

----

## <a name='general'>General/Ice Breaker</a>

> You're looking for passion and enthusiasm when a candidate discusses their previous projects and any projects they're working on in their spare time. If they get excited talking about these things, they show the kind of passion for software development that is a good indicator of whether they're capable of meeting your bar.
Once you've calmed a nervous candidate's nerves or determined level of passion/enthusiasm, move on to the next set of questions. Try to spend a maximum of 5 minutes on this section.

* Tell us about your most recent project.
* Do you ever do any coding in your personal time (outside of work)?
* Do you have an account on Github?
  * If so, what are some examples of repos you follow?
* Tell us what critical problems you have to handle in your latest projects?
* Walk us through the process of creation of an application or website you've built.
* Why did you get into development?
* How many technical books did you read in the past year?
* What was your favorite technical book in the past year? What did you learn from it?
* What websites do you read regularly, related to development?
* Do you maintain any open-source projects?
* Do you code in your spare time?
* Do you love programming, or do you do it for the money?
* Have you accomplished anything important in your career yet? Do you want to?
* What would make you feel that you have done something important?
* What's your favorite programming language? Why?
* If you could add one feature to your favorite language, what would it be? Why?
* If you could remove one feature from it, what would it be? Why?
* Suppose you could design your dream job that you'll be starting on Monday. It's at your ideal company with your ideal job title and salary. All you have to do is tell them what you want to do at your job and you can have it. What does your job entail? (Thanks! [nczonline](https://www.nczonline.net/blog/2015/09/my-favorite-interview-question/))

## <a name='management'>Management</a>

* How to tackle a story/task which is difficult to estimate and with high risk?
    - Investigate as early as possible
    - Assign senior staffs on the problem
    - More frequent update and more communication
    - Report higher level supervisors to be aware of the situation

* How to react to unexpected/frequent requirement changes, considering PoC phase and production phase.
    - For PoC:
      - communicate with team members to let them know things are changing.
      - Proving the solution is more important than perfect design/implementation. For requirement changes, argue for the reason. If it is the business reason, mostly we should follow. If it is the technical reason, we should discuss first and then make the decision.
    - For production:
      - Setup a process first. A requirement change should result in following reactions after re-plan (re-estimation):
         - If it is not so urgent, keep working, change the future plan
         - If it is urgent, either request resource (considering the
ramp-up cost) or cut features
         - If not possible, suggest delaying the release date

* How to keep a team stable with the limited offer. (How's about if you can't increase the compensation while the competitors can give more)

> Basically, setup a good working environment all the time, making team members work happily, and with good development direction and opportunity. If things really happen, resort to higher-level manager and HR to find out a solution.

## <a name='javascript'>JavaScript</a>

* What is ECMAScript, JScript?

ECMAScript is a subset of JavaScript. JavaScript is basically ECMAScript at its core but builds upon it. Languages such as ActionScript, JavaScript, JScript all use ECMAScript as its core. As a comparison, AS/JS/JScript are 3 different cars, but they all use the same engine... each of their exteriors is different though, and there have been several modifications done to each to make it unique.

The history is, Brendan Eich created Mocha which became LiveScript, and later JavaScript. Netscape presented JavaScript to Ecma International, which develops standards and it was renamed to ECMA-262 aka ECMAScript.

It's important to note that Brendan Eich's "JavaScript" is not the same JavaScript that is a dialect of ECMAScript. He built the core language which was renamed to ECMAScript, which differs from the JavaScript which browser-vendors implement nowadays.

* What is the Document Object Model(DOM)?

The Document Object Model (DOM) is a programming interface for HTML and XML documents. It represents the page so that programs can change the document structure, style and content. The DOM represents the document as nodes and objects. That way, programming languages can connect to the page.

The Document Object Model (DOM) represents that same document so it can be manipulated. The DOM is an object-oriented representation of the web page, which can be modified with a scripting language such as JavaScript.

* What's different between undefined and null? It's better to say something about why we need undefined if we have had null.

In JavaScript, undefined means a variable has been declared but has not yet been assigned a value:
```
var TestVar;
alert(TestVar); //shows undefined
alert(typeof TestVar); //shows undefined
```
null is an assignment value. It can be assigned to a variable as a representation of no value:
```
 var TestVar = null;
 alert(TestVar); //shows null
 alert(typeof TestVar); //shows object
```


* What's JavaScript strict mode? What's the intent for it? What does it do? How do you use it?

Strict mode makes several changes to normal JavaScript semantics. First, strict mode eliminates some JavaScript silent errors by changing them to throw errors. Second, strict mode fixes mistakes that make it difficult for JavaScript engines to perform optimizations: strict mode code can sometimes be made to run faster than identical code that's not strict mode. Third, strict mode prohibits some syntax likely to be defined in future versions of ECMAScript.

* What is AJAX? What the workflow for AJAX? How to implement CORS? What's the difference synchronous and asynchronous for JavaScript?

Ajax is not a programming language or a tool, but a concept. Ajax is a client-side script that communicates to and from a server/database without the need for a postback or a complete page refresh. The best definition I’ve read for Ajax is “the method of exchanging data with a server, and updating parts of a web page – without reloading the entire page.” 

Ajax itself is mostly a generic term for various JavaScript techniques used to connect to a web server dynamically without necessarily loading multiple pages. In a more narrowly-defined sense, it refers to the use of `XmlHttpRequest` objects to interact with a web server dynamically via JavaScript.

While Node itself is single threaded, there are some task that can run in parallel. For example, File System operations occur in a different process.

That's why Node can do async operations: one thread is doing file system operations, while the main Node thread keeps executing your javascript code. In an event-driven server like Node, the file system thread notifies the main Node thread of certain events such as completion, failure, or progress, along with any data associated with that event (such as the result of a database query or an error message) and the main Node thread decides what to do with that data.

`Access-Control-Allow-Origin` only accepts * or a single origin.

If you want to support multiple origins but not all of them, then you must:

look at the `Origin` request header
check if it is on your list of acceptable origins
put it in the `Access-Control-Allow-Origin` response header

* Say something about JavaScript Encapsulation.

Not so simply put, a closure is an inner-scope which has access to all of the variables defined outside of its block, even after those variables would have normally “fallen out of scope.”   Although methods of an object can’t see each other’s local variables, an inner object does have access to the local variables of its parent function.

We’ve created an anonymous function to hide the variables, and then defined the object as an inner object, in order to grant it access to the private variables.  But how do we expose the inner object to the outside world? 

Thankfully the solution is simple: return the inner object when the anonymous function is called, and assign it to the outside variable 

```js
var person = function () {
 
  var fullName = "Jason Shapiro";
  var reg = new RegExp(/\d+/);
 
  return { 
    setFullName : function (newValue) {
      if( reg.test(newValue) ) {
        alert("Invalid Name");
      }
      else {
        fullName = newValue;
      }
    },
    getFullName : function () {
     return fullName; 
    }
  }; // end of the return
}(); // Note the '()', this means we're calling the function 
     // and assigning the *returned object,* instead of 
     // the *function itself* for the value of 'person.'
```

* Say something about JavaScript Inheritance(Classical Versus Modern Inheritance).

Prototype chaining means an objects dunder proto or proto will point to another object instead of pointing to the constructor function prototype. If the other object’s dunder proto or proto property points to another object it will results into chain. This is prototype chaining.

Above code defines two consructor functions, SuperType and SubType. By default, SubType.prototype has a constructor function which points to the constructor function itself and proto property which inherits the default object properties.

Above line rewrites the default prototype or he dunder proto property of the SubType constructon function and makes SubType.prototype to point to an object of SuperType constructor function.
This means that all the properties and methods that typically exists on an instance of SuperType now also on SubType.prototype This means that now, SubType function has access to all the SuperType properties and methods.

To fix this issue, we use constructor to inherit the instance properties and prototype chaining to to inherit methods and share properties


* What is Closure?

Languages such as Java provide the ability to declare methods private, meaning that they can only be called by other methods in the same class.

JavaScript does not provide a native way of doing this, but it is possible to emulate private methods using closures. Private methods aren't just useful for restricting access to code: they also provide a powerful way of managing your global namespace, keeping non-essential methods from cluttering up the public interface to your code.

The shared lexical environment is created in the body of an anonymous function, which is executed as soon as it has been defined. 

Those three public functions are closures that share the same environment. Thanks to JavaScript's lexical scoping, they each have access to the privateCounter variable and changeBy function.


* When and why you need to use `this` keyword?

In most cases, the value of this is determined by how a function is called. It can't be set by assignment during execution, and it may be different each time the function is called. ES5 introduced the bind method to set the value of a function's this regardless of how it's called, and ES2015 introduced arrow functions which do provide their own this binding (it remains the this value of the enclosing lexical context).

* How to handle cookie using JavaScript?



* DOM manipulation – how to add, remove, move, copy, create, and find nodes.



* As for JavaScript regex, what is greediness, lazy, negated character classes matching? How to write a regex to match `<script>greediness</script>`?


* Events - how to use them and the major differences between IE and the DOM event models?

In JavaScript, we can listen to events using this:
```
element.addEventListener(<event-name>, <callback>, <use-capture>);
```

Removing event listeners once they are no longer needed is a best practice (especially in long-running Web applications). To do this, use the element.removeEventListener() method:
```
element.removeEventListener(<event-name>, <callback>, <use-capture>);
```
But `removeEventListener` has one catch: You must have a reference to the callback function that was originally bound. Simply calling element.removeEventListener('click'); will not work.

The event object is created when the event first happens; it travels with the event on its journey through the DOM. The function that we assign as a callback to an event listener is passed the event object as its first argument. We can use this object to access a wealth of information about the event that has occurred.

When a DOM event fires in your app, it doesn’t just fire once where the event originated; it embarks on a journey of three phases. In short, the event flows from the document’s root to the target (i.e. capture phase), then fires on the event target (target phase), then flows back to the document’s root (bubbling phase).

As mentioned, you can listen to events in the capture phase by setting the third argument of addEventListener to true. I have not found many use cases for capture phase listeners, but you could potentially prevent any clicks from firing in a certain element if the event is handled in the capture phase.

Bubbling is useful. It frees us from listening for an event on the exact element it came from; instead, we listen on an element further up the DOM tree, waiting for the event to reach us. 


  
* XMLHttpRequest – what it is, how to perform a complete GET request, how to detect errors?


* JSON – what it is, why you'd want to use it, how to actually use it, implementation details?


* Promise - what it is, and why we need that? What problems do it solve?

The Promise object represents the eventual completion (or failure) of an asynchronous operation, and its resulting value.

A Promise is a proxy for a value not necessarily known when the promise is created. It allows you to associate handlers with an asynchronous action's eventual success value or failure reason. This lets asynchronous methods return values like synchronous methods: instead of immediately returning the final value, the asynchronous method returns a promise to supply the value at some point in the future.

A Promise is in one of these states:

- pending: initial state, neither fulfilled nor rejected.
- fulfilled: meaning that the operation completed successfully.
- rejected: meaning that the operation failed.

* Using only a single event handler on the parent, detect a swipe left and a swipe right and alert() which direction was swiped.


* Write an example of a closure in javascript. It doesn't matter what the code does, as long as it shows a closure is created.


* Difference between `document.write` and `innerHTML`.


* How `delete` operator works in JavaScript? What exactly can and cannot be deleted and why.


* How does prototypal inheritance work?


* What defines a closure?


* How does the meaning of this keyword change?


* How does one use to apply/bind/map/filter/call?


* Say how would you describe the flow-control steps of this program?

  ~~~JavaScript
  makeAjaxRequest( url, function(response){ alert( "Response: " + response ); } );
  ~~~

* Write a factorial function.


* Write a function that accepts a string then reverses it. Recursively is better.
  ~~~JavaScript
  function reverseString(str) {
    return str.split("").reverse().join("");
  }

  // With Recursion
  function reverseString(str) {
    return (str === '') ? '' : reverseString(str.substr(1)) + str.charAt(0);
  }

  // In ES6, you have one more option
  [...str].reverse().join('')
  ~~~

* Write a recursively map function.
  ~~~JavaScript
  function map(arr, fn) {
    if (arr.length === 0) {
      return [];
    }

    return [fn(arr[0])].concat(map(arr.slice(1), fn));
  }
  ~~~

* What is the difference between these four promises?
  ~~~JavaScript
  doSomething().then(function () {
    return doSomethingElse();
  }).then(finalHandler);

  doSomething()
    .then(function () {
      doSomethingElse();
    })
    .then(finalHandler);

  doSomething()
    .then(doSomethingElse())
    .then(finalHandler);

  doSomething()
    .then(doSomethingElse)
    .then(finalHandler);
  ~~~

* What's the result of the below JavaScript snippet in the native implementation?
  ~~~JavaScript
  setTimeout(function(){console.log("three");}, 0);

  Promise.resolve().then(function(){ console.log( "two" ); });

  console.log("one");
  ~~~

* Explain the use cases for, and differences between — `bind`, `apply` and `call`.
* Explain event delegation and why it is useful.

Event delegation allows us to attach a single event listener, to a parent element, that will fire for all descendants matching a selector, whether those descendants exist now or are added in the future.

* What is the event loop?

A JavaScript runtime contains a message queue, which is a list of messages to be processed. A function is associated with each message. When the stack has enough capacity, a message is taken out of the queue and processed. The processing consists of calling the associated function (and thus creating an initial stack frame). The message processing ends when the stack becomes empty again.

Each message is processed completely before any other message is processed. This offers some nice properties when reasoning about your program, including the fact that whenever a function runs, it cannot be pre-empted and will run entirely before any other code runs (and can modify data the function manipulates). This differs from C, for instance, where if a function runs in a thread, it can be stopped at any point to run some other code in another thread.

A downside of this model is that if a message takes too long to complete, the web application is unable to process user interactions like click or scroll. The browser mitigates this with the "a script is taking too long to run" dialog. A good practice to follow is to make message processing short and if possible cut down one message into several messages.

In web browsers, messages are added anytime an event occurs and there is an event listener attached to it. If there is no listener, the event is lost. 

The function setTimeout is called with 2 arguments: a message to add to the queue, and a time value (optional; defaults to 0). The time value represents the (minimum) delay after which the message will actually be executed. If there is no other message in the queue, the message is processed right after the delay; however, if there are messages, the setTimeout message will have to wait for other messages to be processed. For that reason, the second argument indicates a minimum time and not a guaranteed time.


* How does hoisting work in JavaScript?

Within its current scope, regardless of where a variable is declared, it will be, behind the scenes, hoisted to the top. However, only the declaration will be hoisted. If the variable is also initialized, the current value, at the top of the scope, will initially be set to undefined.

```
var myvar = 'my value'; 
  
(function() { 
  alert(myvar); // undefined 
  var myvar = 'local value'; 
})();
```

It should now make perfect sense why myvar is alerting undefined. As we learned, as soon as the local variable, myvar, was declared, it was automatically hoisted to the top of the function scope…above the alert. As a result, the variable had already been declared at the time of the alert; however, because initializations aren’t hoisted as well, the value of the variable is: undefined.


* Which new JavaScript features are you most excited about and why?
* Prototypal inheritance is so cool for JavaScript especially when trying to keep code DRY and maintainable, but do you know what's the output for the code below?
  ~~~JavaScript
  var parent = {
    get: function fn() {
      return this.val;
    },
    val: 42
  };

  var child = Object.create(parent);
  child.val = 3.14159;
  var grandchild = Object.create(child);

  console.log(parent.get());
  console.log(child.get());
  console.log(grandchild.get());
  ~~~
* What is a pure function?

  A pure function is a function which:
    * Given the same input, will always return the same output.
    * Produces no side effects.
    * Relies on no external state.

* How to determine if the value is a number? (Side note: `typeof value === 'number'` would gives the set of numbers **AND** `NaN` )
* How to get the type for the values below:

```
 NaN, 0, 1, Infinity,                // numbers
 null, undefined, false, 'str',      // other primitives
 new String('a'), new Boolean(true), // wrapped primitives
 {}, [], new Map, new WeakSet(),     // containers
 /regex/, new Date(),                // other custom objects
 window, navigator,                  // native objects
 function () {}, (() => {}), atob,   // functions
 Symbol(),                           // symbol
 {[Symbol.toStringTag]: 'Custom'}    // @@ToStringTag
```

* In what order should the logs appear?

```
console.log('script start')
setTimeout(function() {
  console.log('setTimeout')
}, 0)
Promise.resolve()
  .then(function() {
    console.log('promise1')
  })
  .then(function() {
    console.log('promise2')
  })
console.log('script end')

```

## <a name='html'>HTML</a>

* What is `<!DOCTYPE>` tag? How to use it?

Basically, the DOCTYPE describes the HTML that will be used in your page.

Browsers also use the DOCTYPE to determine how to render a page. Not including a DOCTYPE or including an incorrect DOCTYPE can trigger quirks mode. The kicker here is that quirks mode in Internet Explorer is quite different from quirks mode in Firefox (and other browsers), meaning that you'll have a much harder job trying to ensure your page works consistently in all browsers if pages are rendered in quirks mode than you will if they are rendered in standards mode.


* What's the difference between childNodes[] and children[]?
* DOM structure – how nodes are related to one another and how to traverse from one to the next.
* DOM manipulation – how to add, remove, move, copy, create, and find nodes.
* Strict vs quirks modes – how to trigger each and why this matters.
* Block vs inline elements – how to manipulate using CSS, how they effect things around them and your ability to style them.

All HTML elements are naturally displayed in one of the following ways:

- Block
Takes up the full width available, with a new line before and after (display:block;)
- Inline
Takes up only as much width as it needs, and does not force new lines (display:inline;)
- Not displayed
Some tags, like <meta /> and <style> are not visible (display:none;)

A block element is an element that has, but may not be limited to, the following characteristics:

1. If no width is set, will expand naturally to fill its parent container
2. Can have margins and/or padding
3. If no height is set, will expand naturally to fit its child elements (assuming they are not floated or positioned)
4. By default, will be placed below previous elements in the markup (assuming no floats or positioning on surrounding elements)
5. Ignores the vertical-align property

So, for a block element, it’s not necessary to give it a set width or to give it a width of 100% if you want it to fill its parent horizontally.

And, as the fourth item in the above list indicates, it’s also not necessary to “clear” a block element; assuming no floats are affecting the block element, it will be cleared automatically and will start on the next “line” in the page’s output.

An inline element has, but may not be limited to, the following characteristics:

- Flows along with text content, thus
- Will not clear previous content to drop to the next line like block elements
- Is subject to white-space settings in CSS
- Will ignore top and bottom margin settings, but will apply left and right margins, and any padding
- Will ignore the width and height properties
- If floated left or right, will automatically become a block-level element, subject to all block characteristics
- Is subject to the vertical-align property

You have the option to change any block-level element to an inline element, and vice-versa, using the display property.

* Floating elements – how to use them, troubles with them, and how to work around the troubles.

The float CSS property specifies that an element should be placed along the left or right side of its container, allowing text and inline elements to wrap around it. The element is removed from the normal flow of the web page, though still remaining a part of the flow.

As mentioned above, when an element is floated, it is taken out of the normal flow of the document (though still remaining part of it). It is shifted to the left, or right, until it touches the edge of its containing box, or another floated element.


* HTML vs. XHTML(1.x&2) – how they're different, why you might want to use one over the other.
* List semantic elements in HTML5 as much as you can and why we need them.
* Write a 'Hello, Word!' html page. (whether get to know the necessary HTML tag for one page, DOCTYPE definition,...).
* What's difference between XHTML 1.x and HTML4?
* What's the difference between h1~h6? How's about the difference between ul and ol?
* Have you ever got a chance to use dl, dt, dd? What's the semantic for them?
* What's the common properties used with `form`?
* What's going on if we don't set the `type` property for `input` element?
* What's the use case if we set the `type` property as `image` for `input` element?

## <a name='css'>CSS</a>

* What is CSS?
* List the CSS hacks as much as you can.
* What's the possible values of `display` property? What is block and inline element and what the difference between them? List block and inline tags as much as you can.
* The box model - how margin, padding, and border are related and the difference between border-box (standards mode) and content-box (old Internet Explorer) sizing.
* List CSS Layout.
* What is CSS stack and say something about it?
* List the browser compatibility problems you have ever used or known.
* List the possible values for `position` property and the result for every value.
* List the possible values for `display` property and the result for every value.
* What is the distinguishing feature provided by `display: inline-block`?
* Say something about CSS3, such as transition, animation, transform, etc..
* What's box-sizing and when you need it?
* What's CSS transform?
* Say something about Flexbox: why we need it? how does it work? how we use it?
* Why Table are bad for layout?
* What's use case for float property? How to clear float?
* What CSS selector have you ever used?
* What's the difference between `cssRules` and `rules`

## <a name='http'>HTTP</a>

* List HTTP status codes as much as you can.
* What's the meaning for HTTP status of 200, 302, 304, 404, 500, 503.
* Introduce something about Web Cache or HTTP caching, such as what's Conditional GET Requests? Etags? Expires? Cache-Control?
* What's the difference between `Get` and `Post`  method?
* What's the difference between HTTP stateless and `Connection:keep-alive`?
* What's the message structure for HTTP Request/Response?
* What's the difference between HTTP status code 301 and 302? How search engines handle them?
* What's the HTTP Header related with cache? What's the usage for them?
* When you're sending an Ajax request, how to judge whether full server response has been received and it's OK for you to continue processing it?
* Why we could avoid local cache when using CTRL+F5 or refresh button to reload the page?
* Why we should put stylesheets at the top and put the scripts at the Bottom?
* What an HTTP request/response message packet includes?

## <a name='problem-solving'>Problem Solving</a>

* Classic beginner programming problem: the guessing game. Here’s how it works: Our program will generate a random integer between one and a hundred. It will then prompt us to enter a guess. Upon entering our guess, it will tell us if we’re too low or too high. Once we guess correctly, it will congratulate us.
* Add a `unique` method for Array in order to produce a duplicate-free version of the array using [Vanilla JS](https://jsfiddle.net/starandtina/87TSF/) or [with ES5 compatible JS](https://jsfiddle.net/starandtina/b6hbtbhz/).
* Implement deep clone for inheritance by copying properties from the object using Vanilla JS.
* Control the max-length of input element using JavaScript, if it extends the max length and then set the border of input element as red.
* Change all elements with className of `test` to the yellow background using JavaScript or jQuery.
* Write a marquee program using JavaScript.
* Translate your hexadecimal color value to RGB.
* Generate random numbers that are consecutively unique.
* Find the index of the smallest element in a JavaScript array.
* Check whether a value is an integer in JavaScript.
* [Make it work:](https://jsfiddle.net/starandtina/et7dnge8/)

  ~~~JavaScript
  [1, 2, 3].duplicate(); // [1, 2, 3] => [1, 2, 3, 1, 2, 3]
  ~~~
* Checking whether a value is `NaN` in JavaScript?
* How to load CSS/JavaScript files asynchronously? If you know that, then write `loadCSS` and `loadJS` function in order to load CSS/JavaScript files asynchronously.
* Make the codes below work as expected with a simple template engine.

  ~~~JavaScript
  var tpl = template('<p>hey there {{ name }}</p>');
  var div = document.createElement('div');
  div.innerHTML = tpl({ name: 'Neo' });
  document.body.appendChild(div);
  ~~~
* Define a `spacify` function which takes a string as an argument, and returns the same string but with each character separated by a space, for example:

  ~~~JavaScript
  spacify('hello world') // => 'h e l l o w o r l d'
  ~~~~
  If it's right, the follow-up question to this, is to place the `spacify` function directly on the String object, for example:

  ~~~JavaScript
  'hello world'.spacify();
  ~~~~
* [Implement collection pivot](https://jsfiddle.net/starandtina/e6n5h/): Pivot means put all the things left of the middle element right, and vice versa,

  ~~~JavaScript
  Eg: Pivot {A, B, C} should give {C, B, A}
        Pivot { 1, 2, 3, 4 } should give { 3, 4, 1, 2 }
        Pivot { 1, 2, 3, 4, 5, 6, 7 } should give { 5, 6, 7, 4, 1, 2, 3 }
        Pivot { 11, 8, 45 } should give { 45, 8, 11 }
     Hint: What type should input/output be? Why?
  ~~~
* Provide a functional version of `each` or `forEach` used to iterates over a list of elements, yielding each in turn to an iteratee function.
* Provide a functional version of `function.apply`.
* Partially apply a function by filling in any number of its arguments, without changing its dynamic this value.
* Implement _currying_ in which we could pre-fill arguments to a function before it's executed.
* Write your own function composition, returns the composition of a list of functions, where each function consumes the return value of the function that follows. In math terms, composing the functions `f()`, `g()`, and `h()` produces `f(g(h()))`.
* Shuffle an array of numbers using [Fisher-Yates shuffle](http://en.wikipedia.org/wiki/Fisher%E2%80%93Yates_shuffle).
* Provide a polyfill of string trim function.
* Get the max or the min in an array of numbers.
* An HTML escaper function.
* [Find an item by property in an array](https://gist.github.com/starandtina/267f2935c2f3f1553ee5).

## <a name='algorithms'>Algos, Data Structures, & Computer Science Fundamentals</a>

> Algorithm is at the heart of every nontrivial computer application, and algorithmic is a modern and active area of computer science. Every computer scientist and every professional programmer should know about the basic algorithmic toolbox: structures that allow efficient organization and retrieval of data, frequently used algorithms, and basic techniques for modeling, understanding and solving algorithmic problems and our expectation of
event candidates is that they are very strong in this area.

* Merge sort has a complexity of O(n*log n), making it one of the more efficient sorting algorithms available, also it's a stable sort. That's why Firefox and Safari use merge sort for their implementation of `Array.prototype.sort()`. Please implement `Array.prototype.sort()` using merge sort.
* Binary search implementation in JavaScript.
* Define a function that returns n lines of [Pascal’s Triangle](https://en.wikipedia.org/wiki/Pascal%27s_triangle).
* Use recursion to log a Fibonacci sequence of n length. (Notice: only need to log instead of calculating the result)

  ~~~JavaScript
  function fib(depth, n1, n2) {
    if (!depth) { return; }
    console.log(n1);
    fib(depth-1, n2, n1 + n2);
  }
  ~~~
* How to find the longest word in a string with JavaScript?

  ~~~JavaScript
  "The quick brown fox jumped over the lazy dog".split(' ').sort(function (a, b) {
    return b.length - a.length;
  })[0].length;
  ~~~

## <a name='react'>React</a>

> React is a library that’s designed to be one piece of the puzzle. React provides a thin view layer and leaves it to the developer to choose the remaining pieces of the architecture. Nothing comes in the box, so your team has full control over everything that you use. Choose-your-adventure works well if you have a team of experienced JavaScript developers who are comfortable with functional programming and immutable data structures. The React community is on the cutting edge of innovation in the use of web technologies. If your organization needs to target many platforms with the same codebase, knowing React will allow you to write for the web, for native with React Native, and for VR devices with ReactVR.

- When does **React** will trigger re-render?
- What happens when you call setState?
- What’s the difference between an Element and a Component in **React**?
- When would you use a Class Component over a Functional Component?
- What are refs in **React** and why are they important? Can we use the refs in functional components?
- What are keys in **React** and why are they important?
- If you created a **React** element like Twitter below, what would the component definition of Twitter look like?

~~~JavaScript
<Twitter username='starandtina'>
 {(user) => user === null ? <Loading /> : <Badge info={user} />}
</Twitter>
~~~

- What is the difference between a controlled component and an uncontrolled component
- In which lifecycle event do you make AJAX requests and why?
- What does shouldComponentUpdate do and why is it important?
- How do you tell **React** to build in Production mode and what will that do?
- Why would you use `React.Children.map(props.children, () =>)` instead of `props.children.map(() =>)`
- Describe how events are handled in **React**.
- What is the difference between createElement and cloneElement?
- What is the second argument that can optionally be passed to setState and what is its purpose?
- What’s wrong with this code?

~~~JavaScript
this.setState((prevState, props) => {
  return {
    streak: prevState.streak + props.count
  }
})
~~~

- What's the result of `state.count` and why? If it's not what you want and how to fix it?

~~~JavaScript
// assuming state.count === 0
this.setState({count: state.count + 1})
this.setState({count: state.count + 1})
this.setState({count: state.count + 1})
// state.count === 1 or 3
~~~

- What’s **context** why we need it?
- What's the **Presentational** and **Container** components and why it's so important?
- Why this kind of error occurs? **Parse Error: Adjacent JSX elements must be wrapped in an enclosing tag.**
- How would you make the choice between **Redux** and **React's setState**?
- [12 Essential React.js Interview Questions*](https://www.toptal.com/react/interview-questions)
- How should we structure the data in our Redux store?

## <a name='general-evaluation-questions'>General Evaluation Questions</a>

> Here are some general evaluation questions in terms of technical interview for checking candidate's background quickly

~~~
function foo(a, b, c) {
  return a + b + c;
}
console.log(foo(1, 2));

// --------------------------------------

function DB() {
  this.read = function () {
    // ...
    console.log('Call read method')
  }
}
var db = new DB();
var aRead = db.read;

db.read();
aRead();

// --------------------------------------

var parent = {
  get: function fn() {
    return this.val;
  },
  val: 1
};

var child = Object.create(parent);
child.val = 3.14159;
var grandchild = Object.create(child);

console.log(parent.get());
console.log(child.get());
console.log(grandchild.get());

// --------------------------------------

for (var i = 1; i <= 5; i++) {
  setTimeout(function timer() {
    console.log(i);
  }, i * 1000);
}

// --------------------------------------

function foo() {
  console.log(a);
}

function bar() {
  var a = 3;

  foo();
}

var a = 2;

bar();
~~~

## License

[![CC0](https://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)
