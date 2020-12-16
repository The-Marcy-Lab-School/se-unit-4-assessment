# Unit 4 Assessment
## Coding Challenges

### Directions
Craft solutions to the exercises below. Write your solutions in `solutions.js`. Ensure that your tests pass and your code is eslint error free.

To install dependencies, run `npm install`.
To run tests, run `npm test`.
To run eslint, run `eslint solutions.js`

### Questions
1. Create a function, `makeAccount`, that takes a number parameter representing a starting balance and **returns an object with three methods** - `checkBalance`, `add`, `subtract`. `checkBalance` should return the current balance. `add` should take a number parameter and add it to the current balance. `add` should return `<<number>> added`. `subtract` should take a number parameter and subtract it from the current balance. `subtract` should return `<<number>> subtracted`.

      ```javascript
      const myAccount = makeAccount(100);
      myAccount.checkBalance(); // 100
      myAccount.add(50);        // "50 added"
      myAccount.checkBalance(); // 150 
      myAccount.subtract(30);   // "30 subtracted"
      myAccount.checkBalance(); // 120
      ```
      
2. Use ES6 classes to create a `Phone` class. `Phone` instances should be initialized with a `phoneNumber` string. `Phone` objects should also have a `contacts` property, initialized with a value of an empty array. `Phone`s should have the following methods available to them:
    * `addContact`, which takes a `contact` object as a parameter and adds this object to the `contacts` property. The `contact` objects should consist of two properties, a `name` and a `phoneNumber`. `addContact` should return `<<contact name>> added.` However, if `addContact` is called with a `contact` that does not have a `name` or `phoneNumber` property, the method should simply return `Invalid`. Additionally, all phone numbers **must be a ten digit string**. Calling `addContact` with a `phoneNumber` that is not a ten digit string should return `Invalid`. 
    * `removeContact`, which takes a string (`name`) as a parameter and removes the object with the matching `name` from the `contacts` array. If `removeContact` is called with a `name` that is not in `contacts`, the method should return `"Contact not found"`. Otherwise, it should return `<<contact name>> removed.` 
    * `call`, which takes a string argument which could represent a `name` OR a `phoneNumber`. If the `name` or `phoneNumber` is found in contacts, it should return, `"Calling <<contact name>>..."`. If it is not found it should return, `"Calling <<phone number>>"`if the parameter passed is a 10 digit string. Otherwise, it should return, `"Invalid"`

      ```javascript
      const myPhone = new Phone('3448731233');
      myPhone.phoneNumber; '3448731233';
      myPhone.addContact({name: "Reuben", phoneNumber: '3462217541'}); // "Reuben added."
      myPhone.contacts; // [{name: "Reuben", phoneNumber: '3462217541'}]
      myPhone.addContact({phoneNumber: '3461124321'}); // "Invalid"
      myPhone.addContact({name: "Reuben", phoneNumber: '346'}); // "Invalid"
      myPhone.addContact({name: "Peter", phoneNumber: '3499217541', extraData: 'is perfectly fine'}); // "Peter added."
      myPhone.contacts; // [{name: "Reuben", phoneNumber: '3462217541'}, {name: "Peter", phoneNumber: '3499217541', extraData: 'is perfectly fine'}]
      myPhone.removeContact('Reuben'); // "Reuben removed."
      myPhone.contacts; // [{name: "Peter", phoneNumber: '3499217541', extraData: 'is perfectly fine'}]
      myPhone.removeContact('Paul'); "Contact not found."
      myPhone.call('Peter'); // "Calling Peter..."
      myPhone.call('3499217541'); // "Calling Peter..."
      myPhone.call('1234567890'); // "Calling 1234567890"
      myPhone.call('888'); // "Invalid"
      myPhone.call('Paul'); // "Invalid"
      ```


3. Create an `AppleiPhone` class that inherits from `Phone`. In addition to `Phone` properties, `AppleiPhone`s should be initialized with a `model` property. Additionally, `AppleiPhone`s should have a `sendiMessage` method. `sendiMessage` should take one argument which represents a `Phone` object, and another string argument, which represents the text message. `sendiMessage` should simply return `"Message sent."` if the recipient is an `AppleiPhone` as well. Otherwise, it should return `"Message could not be sent."`

      ```javascript
      const reubenPhone = new AppleiPhone('2234432211', 'iPhone 14');
      const mayasPhone = new AppleiPhone('3349987745', 'iPhone 6');
      const devontesPhone = new Phone('9932103000');
      reubensPhone.sendiMessage(mayasPhone, 'Hey friend!'); // "Message sent."
      mayasPhone.sendiMessage(reubensPhone, 'Hi! 👋🏾'); // "Message sent."
      reubensPhone.sendiMessage(devontesPhone, 'DYFR!'); // "Message could not be sent."
      mayasPhone.sendiMessage(devontesPhone, '☀️'); // "Message could not be sent."
      devontesPhone.sendiMessage(reubensPhone, 'Got you!'); // Uncaught TypeError: devontesPhone.sendiMessage is not a function
      ```
