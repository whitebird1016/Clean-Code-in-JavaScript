# Learning Clean-Code-in-JavaScript with Shikamaru

![shikamaru](https://github.com/whitebird1016/Clean-Code-in-JavaScript/blob/main/CUEVhE5.webp)


<h2> 7 JavaScript clean coding tips every developer should know</h2>


<h3>1. Use Object Destructuring </h3>
<ul><li>Using multiple properties from an object.</li>
<li>Using the same property multiple times.</li>
<li>Using a property that is deeply nested in an object.</li>
</ul>

```

  const employee = {name: ‘white’, email: ‘takus.superdev@gmail.com’'};

  //with destucturing

  const {name, email} = employee;

  //without destucturing

  const name = employee.name;

  const email = employee.email;
  
```


<h3>2. Use Multiple Parameters Over Single Object Parameter </h3>
<ul><li>When declaring a function, we should always use multiple input parameters instead of single object inputs. This approach helps developers easily understand the minimum number of parameters that need to be passed by looking at the method signature.</li>
<li>Also, it improves the application performance since there is no need to create object parameters or collect garbage.</li>
</ul>

```

//recommended
function CustomerDetail (CustomerName, CustomerType, Order){    
  console.log('This is ${CustomerName} of ${CustomerType} and need ${Order}');
} 
//not-recommended
function CustomerDetail (User){    
  console.log('This is ${User.CustomerName} of ${User.CustomerType} and need ${User.Order}');
}
  
```

<h3>3. Make Use of Arrow Functions
 </h3>
<ul><liArrow functions provide a concise way of writing JavaScript functions while resolving the problem of accessing this property inside callbacks.
If you are using arrow functions, curly braces, parenthesis, function, and return keywords become optional. Most importantly, your code becomes more understandable and clearer..</li>
</ul>

```

// Arrow function
const myOrder = order => console.log(`Customer need ${order}`);
// Regular Function
function(order){
   console.log(`Customer need ${order}`);
}
  
```

<h3>4. Use Template Literals for String Concatenations
 </h3>
<ul>Template literals are literals delimited with backticks (`). It provides an easy way to create multiline strings and perform string interpolation.
</li>
</ul>

```

//before
var name = 'Peter';
var message = 'Hi'+ name + ',';
//after
var name = 'Peter';
var message = `Hi ${name},`;
  
```

<h3>5. Spread Extension Operator
 </h3>
<ul><li>The spread extension operator (…) is another feature introduced with ES6. It is capable of expanding the literals like arrays into individual elements with a single line of code.
</li>
<li>This operator is really useful when we need to put an array or object into a new array or object or to combine multiple parameters in the array.
</li>
</ul>

```
let x = [car, bus,van];
let y = [bike, truck, ..x, lorry]
console.log (y);
// bike, truck, car, bus, van, lorry
  
```

<h3>6. Avoid Callbacks
 </h3>
<ul><li>Callbacks used to be the most popular way to express and handle asynchronous functions in JavaScript programs. However, if you are still using it, I hope you already know the pain of handling multiple nested callbacks.
</li>
</ul>

```

function1(function (err, data) { 
  ...  
  function2(user, function (err, data) {
    ...
     function3(profile, function (err, data) {
      ...
      function4(account, function (err, data) {
        ....
      }); 
    }); 
  });
});
  
```
<ul><li>As a solution, ES6 and ES7 introduced, Promises and Async/Await to handle asynchronous functions, and they are much easier to use and makes your code easily understandable to others.
</li><li>
But, if you use Promises or Async/Await, your code will be clean and much easy to understand.</li>
</ul>

```
// Promises
function1() 
.then(function2) 
.then(function3) 
.then(function2) 
.catch((err) => console.error(err));
// Async/Await
async function myAsyncFunction() {  
try {    
  const data1= await function1();    
  const data2= await function2(data1);    
  const data3= await function3(data2);    
  return function4(data4);  
} 
catch (e) {    
  console.error(err);  
}}

```

<h3>7. Use Shorthand Whenever Possible

 </h3>
<ul><li>When working with conditions, the shorthand method can save you a lot of time and space.

</li>
</ul>

```
if (x !== “” && x !== null && x !== undefined) { ... }
```
<ul><li>However, if you are using the shorthand operator, you just need to write a single condition like below:
</li>
</ul>

```
if ( !!x ) { ... }
```

