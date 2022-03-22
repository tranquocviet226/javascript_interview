## :question: JavaScript Interview Questions & Answers

|No  |Questions  |
|--|--|
|1 |[What are the possible ways to create objects in JavaScript](#what-are-the-possible-ways-to-create-objects-in-javascript)   |
|2 |[What is a prototype chain](#what-is-a-prototype-chain)|
|3 |[What is the difference between Call, Apply and Bind](#what-is-the-difference-between-call-apply-and-bind)

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

