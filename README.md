## :question: JavaScript Interview Questions & Answers

|No  |Questions  |
|--|--|
|1 |[What are the possible ways to create objects in JavaScript](#what-are-the-possible-ways-to-create-objects-in-javascript)   |

1. ### What are the possible ways to create objects in JavaScript
There are many ways to create objects in javascript as below

   1.1 **Object constructor:**

      The simplest way to create an empty object is using the Object constructor. Currently this approach is not recommended.

     ```javascript
     var v1 = {};
     var v2 = "";
     var v3 = 0;
     var v4 = false;
     var v5 = [];
     var v6 = /()/;
     var v7 = function(){};
     ```

   1.2 **Object's create method:**

      The create method of Object creates a new object by passing the prototype object as a parameter

      ```javascript
      var object = Object.create(null);
      ```
