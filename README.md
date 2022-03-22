## :question: JavaScript Interview Questions & Answers

|No  |Questions  |
|--|--|
|1 |[What are the possible ways to create objects in JavaScript](#what-are-the-possible-ways-to-create-objects-in-javascript)   |

1. ### What are the possible ways to create objects in JavaScript
There are many ways to create objects in javascript as below

   1.1 **Object constructor:**

      The simplest way to create an empty object is using the Object constructor. Currently this approach is not recommended.

      ```javascript
      var object = new Object();
      ```

   1.2 **Object's create method:**

      The create method of Object creates a new object by passing the prototype object as a parameter

      ```javascript
      var object = Object.create(null);
      ```
