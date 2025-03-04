ES6 (ECMAScript 2015) JavaScript-এর সবচেয়ে শক্তিশালী এবং গুরুত্বপূর্ণ বৈশিষ্ট্যগুলি এনেছে, যা কোড লিখতে অনেক সুবিধা এবং সরলতা আনে। ES6-এর কিছু প্রধান বৈশিষ্ট্য বা "কিওয়ার্ড" এখানে ব্যাখ্যা করা হলো:

### **1. `let` এবং `const`**
- **`let`**: এটি একটি ব্লক-স্কোপড (block-scoped) ভেরিয়েবল ডিক্লেয়ার করতে ব্যবহার হয়, যা `var` এর চেয়ে আরও নিরাপদ এবং পূর্বানুমানযোগ্য।
- **`const`**: এটি এমন ভেরিয়েবল ডিক্লেয়ার করতে ব্যবহৃত হয় যেগুলির মান পুনরায় নির্ধারণ করা যাবে না। এটি ইনমিউটেবল কোড লেখার জন্য উপকারী।

```js
let x = 5;    // ব্লক-স্কোপড
const y = 10; // পুনরায় নির্ধারণ করা যাবে না
```

### **2. Arrow Functions (`=>`)**
এগুলি সংক্ষিপ্ত সিনট্যাক্সে ফাংশন এক্সপ্রেশন লিখতে সাহায্য করে এবং এটি `this` কে "লেক্সিক্যালি" ইনহেরিট করে, যা কলব্যাক ফাংশনগুলিতে খুব উপকারী।

```js
// সাধারণ ফাংশন
function add(a, b) {
  return a + b;
}

// Arrow function
const add = (a, b) => a + b;
```

### **3. Template Literals (`` ` ``)**
এই ফিচারের মাধ্যমে আপনি স্ট্রিংয়ে এক্সপ্রেশন এম্বেড করতে পারবেন। `${}` ব্যবহার করে আপনি ভেরিয়েবল এবং এক্সপ্রেশনকে স্ট্রিংয়ের মধ্যে বসাতে পারেন।

```js
const name = "John";
const greeting = `Hello, ${name}!`;  // "Hello, John!"
```

### **4. Destructuring Assignment**
এই ফিচারের মাধ্যমে আপনি অ্যারে বা অবজেক্ট থেকে ভ্যালু আলাদা আলাদা ভেরিয়েবলে বের করতে পারবেন। এটি কোডকে অনেক বেশি পাঠযোগ্য এবং সংক্ষিপ্ত করে তোলে।

- **Array Destructuring**:
```js
let [a, b] = [1, 2]; // a = 1, b = 2
```

- **Object Destructuring**:
```js
let person = { name: "John", age: 25 };
let { name, age } = person;  // name = "John", age = 25
```

### **5. Spread Operator (`...`)**
স্প্রেড অপারেটর ব্যবহার করে আপনি অ্যারে বা অবজেক্টের উপাদানগুলোকে প্রসারিত বা বিস্তৃত করতে পারবেন।

- **Arrays**:
```js
const arr1 = [1, 2];
const arr2 = [...arr1, 3, 4]; // arr2 = [1, 2, 3, 4]
```

- **Objects**:
```js
const obj1 = { a: 1, b: 2 };
const obj2 = { ...obj1, c: 3 };  // obj2 = { a: 1, b: 2, c: 3 }
```

### **6. Default Parameters**
ফাংশনের প্যারামিটারগুলির জন্য ডিফল্ট মান প্রদান করা যায়, যদি সেগুলি পাস না করা হয় বা `undefined` হয়।

```js
function greet(name = "Guest") {
  console.log(`Hello, ${name}!`);
}

greet("Alice");  // Output: "Hello, Alice!"
greet();         // Output: "Hello, Guest!"
```

### **7. Rest Parameters (`...`)**
রেস্ট প্যারামিটার ফাংশনে একটি অপরিবর্তনীয় সংখ্যক আর্গুমেন্টকে অ্যারে হিসেবে গ্রহণ করতে ব্যবহৃত হয়।

```js
function sum(...numbers) {
  return numbers.reduce((acc, num) => acc + num, 0);
}

console.log(sum(1, 2, 3));  // Output: 6
```

### **8. Classes**
ES6 এ অবজেক্ট-ওরিয়েন্টেড প্রোগ্রামিংয়ের জন্য `class` সিস্টেম এসেছে, যা `prototype` ভিত্তিক অবজেক্ট নির্মাণের তুলনায় আরও পরিচিত।

```js
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  sayHello() {
    console.log(`Hello, my name is ${this.name}`);
  }
}

const john = new Person("John", 30);
john.sayHello();  // Output: "Hello, my name is John"
```

### **9. Modules (`import` / `export`)**
ES6 মডিউল সিস্টেমটি কোডের ভগ্নাংশ বা মডিউল তৈরি এবং একে অপরের মধ্যে ইম্পোর্ট/এক্সপোর্ট করার সুবিধা দেয়, যা কোডের পুনঃব্যবহারযোগ্যতা এবং সংগঠনে সহায়ক।

- **Exporting a function**:
```js
export function greet(name) {
  return `Hello, ${name}!`;
}
```

- **Importing a function**:
```js
import { greet } from './greet.js';
```

### **10. Promises**
প্রমিস হলো একটি প্লেসহোল্ডার যা ভবিষ্যতে কোন মান রেজলভ বা রিজেক্ট হবে তা প্রতীক্ষা করে। এটি অ্যাসিঙ্ক্রোনাস অপারেশনকে আরও কার্যকরভাবে পরিচালনা করতে সহায়ক।

```js
let promise = new Promise((resolve, reject) => {
  let success = true;
  
  if (success) {
    resolve("Operation was successful");
  } else {
    reject("Something went wrong");
  }
});

promise
  .then(result => console.log(result))    // Output: "Operation was successful"
  .catch(error => console.log(error));    // Output: "Something went wrong"
```

### **11. `async` / `await`**
`async` এবং `await` ব্যবহার করে অ্যাসিঙ্ক্রোনাস কোডকে আরও সিঙ্ক্রোনাসভাবে লেখা যায়।

```js
async function fetchData() {
  let response = await fetch('https://jsonplaceholder.typicode.com/users');
  let data = await response.json();
  console.log(data);
}

fetchData();
```

### **12. `for...of` Loop**
`for...of` লুপটি অ্যারে বা স্ট্রিংয়ের মতো ইটারেবল অবজেক্টের উপাদানগুলোকে লুপ করার জন্য ব্যবহৃত হয়।

```js
let arr = [10, 20, 30];

for (let num of arr) {
  console.log(num);
}
// Output: 10, 20, 30
```

### **13. `Map` এবং `Set`**
- **`Map`**: এটি একটি কনটেইনার যেটি কী-ভ্যালু পেয়ার হিসাবে কাজ করে, যেখানে কী যেকোনো ডেটাটাইপ হতে পারে।
```js
let map = new Map();
map.set('name', 'John');
map.set('age', 25);
console.log(map.get('name')); // Output: "John"
```

- **`Set`**: এটি একটি সেট যা ইউনিক ভ্যালু (ডুপ্লিকেট না থাকা) ধারণ করে।
```js
let set = new Set();
set.add(1);
set.add(2);
set.add(2); // Duplicate, will be ignored
console.log(set); // Output: Set { 1, 2 }
```

---

### **ES6 এর প্রধান বৈশিষ্ট্যগুলির সংক্ষিপ্ত বিবরণ:**

1. **`let` / `const`** – ব্লক-স্কোপড ভেরিয়েবল
2. **Arrow functions** (`=>`) – সংক্ষিপ্ত ফাংশন সিনট্যাক্স
3. **Template literals** – স্ট্রিংয়ের মধ্যে এক্সপ্রেশন এম্বেড করা
4. **Destructuring** – অ্যারে/অবজেক্ট থেকে ভ্যালু বের করা
5. **Spread operator** (`...`) – অ্যারে/অবজেক্টের উপাদান প্রসারিত করা
6. **Default parameters** – ফাংশনের প্যারামিটারগুলির জন্য ডিফল্ট মান
7. **Rest parameters** (`...`) – ভেরিয়েবল আর্গুমেন্ট সংগ্রহ করা
8. **Classes** – অবজেক্ট-ওরিয়েন্টেড প্রোগ্রামিং
9. **Modules** (`import`/`export`) – কোডের ভগ্নাংশ তৈরি ও ব্যবহার
10. **Promises** – অ্যাসিঙ্ক্রোনাস অপারেশন পরিচালনা
11. **`async`/`await`** – সিঙ্ক্রোনাসের মতো অ্যাসিঙ্ক্রোনাস কোড লেখা
12. **`for...of`** – ইটারেবল অবজেক্টে লুপ করা
13. **`Map` / `Set`** – নতুন ডেটা স্ট্রাকচার

এসব ES6 বৈশিষ্ট্যগুলি JavaScript কোড লেখার জন্য আরও শক্তিশালী এবং সহজ করেছে। যদি কোন বিষয় সম্পর্কে বিস্তারিত জানতে চান, আমাকে জানাতে পারেন! 😊