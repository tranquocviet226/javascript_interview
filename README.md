## :question: JavaScript Interview Questions & Answers

|No  |Questions  |
|--|--|
|1 |[What are the possible ways to create objects in JavaScript](#what-are-the-possible-ways-to-create-objects-in-javascript)   |
|2 |[What is a prototype chain](#what-is-a-prototype-chain)|
|3 | [What is the difference between Call, Apply and Bind](#what-is-the-difference-between-call-apply-and-bind)

### Content questions

1. ### What are the possible ways to create objects in JavaScript

	1.1 **Object constructor:**
   
		var object = new Object();
      
	1.2 **Object's create method:**
      
		var object = Object.create(null);
      
	1.3  **Object literal syntax:**

		var object = {};

	1.4 **Function constructor:**

		function Person(name){
		   this.name=name;
		   this.age=21;
		}
		var object = new Person("Sudheer");
		
	1.5 **Function constructor with prototype:**
		
		function Person(){}
		Person.prototype.name = "Sudheer";
		var object = new Person();

	1.6 **ES6 Class syntax:**

		class Person {
		   constructor(name) {
		      this.name = name;
		   }
		}
		
		var object = new Person("Sudheer");

	1.7 **Singleton pattern:**

		var object = new function(){
		   this.name = "Sudheer";
		}
		
	**[⬆ Back to Top](#content-questions)**
	
2. ### What is a prototype chain

	**Prototype chaining** is used to build new types of objects based on existing ones. It is similar to inheritance in a class based language.
	Prototype can be used to add a new method or property of an object

	    function Person () {
			this.name = "Viet"
		}
		Person.prototype.age = 25

		const vietPerson = new Person()
		console.log(vietPerson.age)  // 25 

	**[⬆ Back to Top](#content-questions)**

3. ### What is the difference between Call, Apply and Bind

		function  invite(gretting1, gretting2) {
			console.log(gretting1  +  ' '  +  this.firstName  +  ', '  +  gretting2)
		}  

		const  employee1  = { firstName: 'Lan' }
		const  employee2  = { firstName: 'Cuc' } 

		invite.call(employee1, 'Hello', 'How are you?') // Hello Lan, How are you?
		invite.call(employee2, 'Hello', 'How are you?') // Hello Cuc, How are you?
		
