## :question: JavaScript Interview Questions & Answers

|No  |Questions  |
|--|--|
|1 |[What are the possible ways to create objects in JavaScript](#what-are-the-possible-ways-to-create-objects-in-javascript)   |
|2 |[What is a prototype chain](#what-is-a-prototype-chain)|
|3 |[What is the difference between Call, Apply and Bind](#what-is-the-difference-between-call-apply-and-bind)|
|4 | [What is the difference between slice and splice](#what-is-the-difference-between-slice-and-splice)|
|5 | [What is the difference between == and === operators](#what-is-the-difference-between--and--operators)|
|6 | [What are lambda or arrow functions](#what-are-lambda-or-arrow-functions)| 

### Content questions

1. ### What are the possible ways to create objects in JavaScript

	1.1 **Object constructor:**
   
	```javascript
	var object = new Object();
    ```
      
	1.2 **Object's create method:**
      
	```javascript
	var object = Object.create(null);
	```
      
	1.3  **Object literal syntax:**

	```javascript
	var object = {};
	```

	1.4 **Function constructor:**

	```javascript
		function Person(name){
			this.name=name;
			this.age=21;
		}
		var object = new Person("VietTQ");	
	```
		
	1.5 **Function constructor with prototype:**
		
	```javascript
	function Person(){}
	Person.prototype.name = "VietTQ";
	var object = new Person();
	```
	
	1.6 **ES6 Class syntax:**

	```javascript
	class Person {
		constructor(name) {
			this.name = name;
		}
	}
	
	var object = new Person("VietTQ");
	```
		
	1.7 **Singleton pattern:**

	```javascript
	var object = new function(){
		this.name = "Sudheer";
	}
	```
				
	**[⬆ Back to Top](#content-questions)**
	
2. ### What is a prototype chain

	**Prototype chaining** is used to build new types of objects based on existing ones. It is similar to inheritance in a class based language.
	Prototype can be used to add a new method or property of an object

	```javascript
    function Person () {
		this.name = "Viet"
	}
	Person.prototype.age = 25

	const vietPerson = new Person()
	console.log(vietPerson.age)  // 25 
	```

	**[⬆ Back to Top](#content-questions)**

3. ### What is the difference between Call, Apply and Bind

	**Call:** The call() method invokes a function with a given `this` value and arguments provided one by one

	```javascript
	function invite(gretting1, gretting2) {
		console.log(gretting1  +  ' '  +  this.firstName  +  ', '  +  gretting2)
	}  

	const employee1 = { firstName: 'Lan' }
	const employee2 = { firstName: 'Cuc' } 

	invite.call(employee1, 'Hello', 'How are you?') // Hello Lan, How are you?
	invite.call(employee2, 'Hello', 'How are you?') // Hello Cuc, How are you?
	```
	**Apply:** Invokes the function with a given `this` value and allows you to pass in arguments as an array
	```javascript
	function invite(gretting1, gretting2) {
		console.log(gretting1  +  ' '  +  this.firstName  +  ', '  +  gretting2)
	}  

	const employee1 = { firstName: 'Lan' }
	const employee2 = { firstName: 'Cuc' } 

	invite.apply(employee1, ['Hello', 'How are you?']) // Hello Lan, How are you?
	invite.apply(employee2, ['Hello', 'How are you?']) // Hello Cuc, How are you?
	```
	**Bind:** returns a new function, allowing you to pass any number of arguments

	```javascript
	function invite(gretting1, gretting2) {
		console.log(gretting1  +  ' '  +  this.firstName  +  ', '  +  gretting2)
	}  

	const employee1 = { firstName: 'Lan' }
	const employee2 = { firstName: 'Cuc' } 

	const inviteEmployee1 = invite.bind(employee1)
	const inviteEmployee2 = invite.bind(employee2)

	inviteEmployee1('Hello', 'How are you?') // Hello Lan, How are you?
	inviteEmployee2('Hello', 'How are you?') // Hello Cuc, How are you?
	```
	**[⬆ Back to Top](#content-questions)**

4. ### What is the difference between slice and splice

	4.1 **Slice**
	The **slice()** method returns the selected elements in an array as a new array object. It selects the 	elements starting at the given start argument, and ends at the given optional end argument without including the last element. If you omit the second argument then it selects till the end.
	```javascript
	let arrayIntegers = [1, 2, 3, 4, 5];
	let arrayIntegers1 = arrayIntegers.slice(0,2); // returns [1,2]
	let arrayIntegers2 = arrayIntegers.slice(2,3); // returns [3]
	let arrayIntegers3 = arrayIntegers.slice(4); //returns [5]
	```

	4.2 **Splice**
	The  **splice()**  method is used either adds/removes items to/from an array, and then returns the removed item. The first argument specifies the array position for insertion or deletion whereas the optional second argument indicates the number of elements to be deleted. Each additional argument is added to the array.
	```javascript
	let arrayIntegersOriginal1 = [1, 2, 3, 4, 5];
	let arrayIntegersOriginal2 = [1, 2, 3, 4, 5];
	let arrayIntegersOriginal3 = [1, 2, 3, 4, 5];

	let arrayIntegers1 = arrayIntegersOriginal1.splice(0,2); // returns [1, 2]; original array: [3, 4, 5]
	let arrayIntegers2 = arrayIntegersOriginal2.splice(3); // returns [4, 5]; original array: [1, 2, 3]
	let arrayIntegers3 = arrayIntegersOriginal3.splice(3, 1, "a", "b", "c"); //returns [4]; original array: [1, 2, 3, "a", "b", "c", 5]
	```
	
	4.3 **Some of the major difference**
	
	| Slice | Splice |
	|--|--
	|Doesn't modify the original array(immutable)|Modifies the original array(mutable) | 
	|Returns the subset of original array|Returns the deleted elements as array|
	|Used to pick the elements from array|Used to insert or delete elements to/from array|

	**[⬆ Back to Top](#content-questions)**
	
5. ### What is the difference between == and === operators

	```javascript
	0 == false   // true
	0 === false  // false
	1 == "1"     // true
	1 === "1"    // false
	null == undefined // true
	null === undefined // false
	'0' == false // true
	'0' === false // false
	[]==[] or []===[] //false, refer different objects in memory
	{}=={} or {}==={} //false, refer different objects in memory
	```
	**[⬆ Back to Top](#content-questions)**
	
6. ### What are lambda or arrow functions
	An arrow function is a shorter syntax for a function expression and does not have its own **this, arguments, super, or new.target**. These functions are best suited for non-method functions, and they cannot be used as constructors.
	
	**[⬆ Back to Top](#content-questions)**

7. ### What is
