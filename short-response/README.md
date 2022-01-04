# Unit 4 Assessment - Object-Oriented JavaScript
## Short Response Section

### Directions
Answer each of the questions below clearly and concisely. Include code snippets when appropriate to illustrate your responses. Write your solutions directly in this markdown file.

**1. What is `this`?**



**2. What will the following code produce? Why?** 

  ```javascript
  let a = 10;
  let b = 10;
  let c = {
    a: -10,
    b: -10,
  };

  function add() {
    return this.a + b;
  }

  c.add = add;

  console.log(add());
  console.log(c.add());
  ```


**3. What is a closure? How does it allow us to create private data?**


**4. What is encapsulation? How do classes in JavaScript help us write encapsulated programs?**


**5. What is polymorphism?**
