## **📌 JavaScript-এর Top DOM Methods & তাদের ব্যাখ্যা**  
DOM (Document Object Model) ম্যানিপুলেশনের জন্য JavaScript-এর কিছু গুরুত্বপূর্ণ মেথড আছে, যা ওয়েবপেজের এলিমেন্ট পরিবর্তন, অ্যাট্রিবিউট আপডেট এবং ইভেন্ট হ্যান্ডলিং সহজ করে তোলে।  

---

## **📌 1. Element Select করার মেথড**  
👉 HTML ডকুমেন্ট থেকে এলিমেন্ট সিলেক্ট করার জন্য এই মেথডগুলো ব্যবহৃত হয়।  

### **🔹 1. `document.getElementById(id)` - ID দিয়ে এলিমেন্ট খোঁজা**  
👉 নির্দিষ্ট **ID** দ্বারা একটি নির্দিষ্ট এলিমেন্ট পাওয়া যায়।  
```js
let title = document.getElementById("main-title");
title.innerText = "Updated Title!";
```
✅ **ব্যাখ্যা:**  
এটি `id="main-title"` থাকা এলিমেন্টের টেক্সট পরিবর্তন করবে।  

---

### **🔹 2. `document.getElementsByClassName(className)` - Class দিয়ে খোঁজা**  
👉 নির্দিষ্ট **className** দ্বারা **একাধিক এলিমেন্টের লিস্ট (HTMLCollection)** পাওয়া যায়।  
```js
let items = document.getElementsByClassName("item");
console.log(items[0].innerText); // প্রথম item এর টেক্সট দেখাবে
```
✅ **ব্যাখ্যা:**  
এটি `.item` ক্লাসযুক্ত সব এলিমেন্টকে খুঁজে পাবে এবং প্রথমটির টেক্সট দেখাবে।  

---

### **🔹 3. `document.getElementsByTagName(tagName)` - ট্যাগের মাধ্যমে খোঁজা**  
👉 নির্দিষ্ট **HTML ট্যাগ** অনুযায়ী **একাধিক এলিমেন্ট** পাওয়া যায়।  
```js
let paragraphs = document.getElementsByTagName("p");
console.log(paragraphs.length); // কতগুলো <p> আছে তা দেখাবে
```
✅ **ব্যাখ্যা:**  
সব `<p>` ট্যাগ সংগ্রহ করবে এবং কয়টি আছে তা দেখাবে।  

---

### **🔹 4. `document.querySelector(selector)` - CSS Selector দিয়ে একক এলিমেন্ট সিলেক্ট করা**  
👉 **প্রথম মিল খাওয়া এলিমেন্ট** রিটার্ন করে।  
```js
let firstItem = document.querySelector(".item");
firstItem.style.color = "red";
```
✅ **ব্যাখ্যা:**  
প্রথম `.item` ক্লাসযুক্ত এলিমেন্টকে লাল করে দেবে।  

---

### **🔹 5. `document.querySelectorAll(selector)` - CSS Selector দিয়ে সব এলিমেন্ট সিলেক্ট করা**  
👉 **সব মিল খাওয়া এলিমেন্ট** সংগ্রহ করে।  
```js
let allItems = document.querySelectorAll(".item");
allItems.forEach(item => item.style.fontWeight = "bold");
```
✅ **ব্যাখ্যা:**  
সব `.item` এলিমেন্টকে বোল্ড করে দেবে।  

---

## **📌 2. Content Manipulation (কনটেন্ট পরিবর্তনের মেথড)**  

### **🔹 6. `innerText` - শুধুমাত্র টেক্সট পরিবর্তন করা**  
```js
document.getElementById("title").innerText = "New Title!";
```
✅ **ব্যাখ্যা:**  
এটি শুধুমাত্র টেক্সট পরিবর্তন করবে, কিন্তু কোনো HTML ট্যাগ ইনসার্ট করতে পারবে না।  

---

### **🔹 7. `innerHTML` - HTML সহ পরিবর্তন করা**  
```js
document.getElementById("content").innerHTML = "<h2>Updated Content</h2>";
```
✅ **ব্যাখ্যা:**  
এটি **HTML সহ কনটেন্ট পরিবর্তন করতে পারে।**  

---

### **🔹 8. `textContent` - সব টেক্সট পরিবর্তন করা (hidden text সহ)**  
```js
document.getElementById("title").textContent = "Updated Text!";
```
✅ **ব্যাখ্যা:**  
👉 `innerText` এর মতোই, তবে এটি **hidden text**-ও পরিবর্তন করতে পারে।  

---

## **📌 3. Attribute Manipulation (অ্যাট্রিবিউট পরিবর্তনের মেথড)**  

### **🔹 9. `setAttribute(attribute, value)` - নতুন অ্যাট্রিবিউট যোগ বা পরিবর্তন করা**  
```js
document.getElementById("image").setAttribute("src", "new-image.jpg");
```
✅ **ব্যাখ্যা:**  
👉 `src` পরিবর্তন করে **নতুন ইমেজ সেট করবে**।  

---

### **🔹 10. `getAttribute(attribute)` - নির্দিষ্ট অ্যাট্রিবিউটের মান পাওয়া**  
```js
let link = document.getElementById("myLink");
console.log(link.getAttribute("href")); // লিংকের URL দেখাবে
```
✅ **ব্যাখ্যা:**  
👉 `href` এর মান দেখাবে।  

---

### **🔹 11. `removeAttribute(attribute)` - অ্যাট্রিবিউট রিমুভ করা**  
```js
document.getElementById("image").removeAttribute("alt");
```
✅ **ব্যাখ্যা:**  
👉 **alt অ্যাট্রিবিউট রিমুভ করবে।**  

---

## **📌 4. Adding & Removing Elements (নতুন এলিমেন্ট যোগ বা ডিলিট করার মেথড)**  

### **🔹 12. `createElement(tagName)` - নতুন এলিমেন্ট তৈরি করা**  
```js
let newDiv = document.createElement("div");
newDiv.innerText = "This is a new div!";
document.body.appendChild(newDiv);
```
✅ **ব্যাখ্যা:**  
👉 এটি নতুন `<div>` তৈরি করে **body তে যোগ করবে**।  

---

### **🔹 13. `appendChild(newElement)` - একটি এলিমেন্টে নতুন এলিমেন্ট যোগ করা**  
```js
let ul = document.getElementById("list");
let newItem = document.createElement("li");
newItem.innerText = "New List Item";
ul.appendChild(newItem);
```
✅ **ব্যাখ্যা:**  
👉 `<ul>`-এর শেষে একটি নতুন `<li>` যোগ করবে।  

---

### **🔹 14. `removeChild(childElement)` - একটি নির্দিষ্ট এলিমেন্ট ডিলিট করা**  
```js
let list = document.getElementById("list");
let firstItem = list.firstElementChild;
list.removeChild(firstItem);
```
✅ **ব্যাখ্যা:**  
👉 লিস্টের প্রথম এলিমেন্ট ডিলিট করবে।  

---

### **🔹 15. `replaceChild(newChild, oldChild)` - একটি এলিমেন্ট পরিবর্তন করা**  
```js
let list = document.getElementById("list");
let newItem = document.createElement("li");
newItem.innerText = "Replaced Item";
list.replaceChild(newItem, list.firstElementChild);
```
✅ **ব্যাখ্যা:**  
👉 লিস্টের প্রথম আইটেমকে নতুন আইটেম দিয়ে রিপ্লেস করবে।  

---

## **📌 5. Event Handling (ইভেন্ট হ্যান্ডলিং)**  

### **🔹 16. `addEventListener(event, function)` - ইভেন্ট যোগ করা**  
```js
document.getElementById("btn").addEventListener("click", function () {
    alert("Button Clicked!");
});
```
✅ **ব্যাখ্যা:**  
👉 যখন **"btn" আইডির** বাটনে ক্লিক করা হবে, তখন **অ্যালার্ট দেখাবে**।  

---

### **🔹 17. `removeEventListener(event, function)` - ইভেন্ট রিমুভ করা**  
```js
function sayHello() {
    console.log("Hello!");
}
document.getElementById("btn").addEventListener("click", sayHello);
document.getElementById("btn").removeEventListener("click", sayHello);
```
✅ **ব্যাখ্যা:**  
👉 প্রথমে ইভেন্ট যোগ করা হয়েছিল, পরে তা রিমুভ করা হলো।  

---

**🔹 এই মেথডগুলোর মাধ্যমে DOM ম্যানিপুলেশন সহজে করা যায়।** 😊  
