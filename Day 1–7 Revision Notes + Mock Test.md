#### 📘 Day 1–7 Revision Notes + Mock Test

---

#### 🧠 DSA Topics Covered

**Day 1:**

* Arrays: Traversal, access by index
* Java Arrays (looping, even number logic)
* JavaScript Arrays (access elements, basic syntax)

**Day 2:**

* 2D Arrays: Matrix traversal, common questions

**Day 3:**

* Strings: Reversal, palindrome check, frequency count

**Day 4:**

* String manipulation: isAnagram, capitalizeWords, removeDuplicates

**Day 5:**

* Recursion basics: factorial, sum, power

**Day 6:**

* Hashing: HashMap, frequency counter, finding duplicates

**Day 7:**

* Revision + DSA Mock Questions

---

#### 💻 MERN Stack Progress

**Day 1:**

* MERN project setup
* Installed: Express, Nodemon

**Day 2:**

* MongoDB Atlas setup
* `mongoose.connect()` used
* `.env` configuration

**Day 3:**

* Created User schema
* POST `/register` route to save users

**Day 4:**

* Validations in Mongoose schema
* Required fields and structure improved

**Day 5:**

* Created `README.md` for GitHub
* Discussed endpoints and usage

**Day 6:**

* Register API + Password hashing with `bcryptjs`
* JWT authentication added
* Middleware created for protected routes

**Day 7:**

* Full codebase revision
* Bug fixes and cleanup

---

#### 📐 Aptitude Topics Covered

**Day 1:**

* Divisibility rules

**Day 2:**

* Time & Work basics

**Day 3:**

* Profit & Loss: Marked price, cost price, selling price

**Day 4:**

* Percentages: Basic % problems and shortcuts

**Day 5:**

* Number Series: Patterns and logic

**Day 6:**

* Profit & Loss advanced: Successive profit/loss problems

**Day 7:**

* Mixed aptitude revision questions

---

#### 🗣️ Behavioral Interview Prep

**Topics Covered:**

* Tell me about yourself
* Strengths and Weaknesses
* Why Amazon / Google / Capgemini?
* Teamwork and conflict resolution examples

---

#### 📝 Mock Test Paper (Day 1–7)

#### Section 1: DSA (3 Questions)

1. Write a function to check if a string is a palindrome in JavaScript.
2. Given an array of integers, return the first duplicate value.
3. Implement a recursive function to calculate factorial of a number.

#### Section 2: MERN Stack (3 Questions)

1. Write Express.js code to connect MongoDB using Mongoose.
2. Create a protected route using JWT middleware.
3. Show how to hash passwords using `bcryptjs`.

#### Section 3: Aptitude (5 Questions)

1. A shopkeeper marks his goods at 40% above cost price and allows a discount of 10%. What is his gain %?
2. 6 men can complete a task in 12 days. How many men are needed to complete it in 9 days?
3. Is 924 divisible by 2, 3, and 6?
4. What is 25% of 640?
5. Find the next number in the series: 2, 4, 8, 16, ?

#### Section 4: Behavioral (2 Questions)

1. Describe a time you faced a challenge while working in a team.
2. Why do you want to work at Amazon as a MERN stack developer?

---

### 🧾 Mock Test Answer Key

#### 🔹 Section 1: DSA

1. **Palindrome in JavaScript**

```js
function isPalindrome(str) {
  str = str.replace(/[^a-z0-9]/gi, '').toLowerCase();
  return str === str.split('').reverse().join('');
}
```

2. **First Duplicate Value**

```js
function firstDuplicate(arr) {
  const seen = new Set();
  for (let num of arr) {
    if (seen.has(num)) return num;
    seen.add(num);
  }
  return -1;
}
```

3. **Recursive Factorial Function**

```js
function factorial(n) {
  if (n === 0) return 1;
  return n * factorial(n - 1);
}
```

---

#### 🔹 Section 2: MERN Stack

1. **MongoDB Connection with Mongoose**

```js
const mongoose = require("mongoose");
mongoose.connect(process.env.MONGODB_URI)
  .then(() => console.log("Connected"))
  .catch((err) => console.error("Error:", err));
```

2. **JWT Middleware**

```js
const jwt = require("jsonwebtoken");
function authMiddleware(req, res, next) {
  const token = req.header("Authorization");
  if (!token) return res.status(401).send("Access Denied");

  try {
    const verified = jwt.verify(token, process.env.JWT_SECRET);
    req.user = verified;
    next();
  } catch (err) {
    res.status(400).send("Invalid Token");
  }
}
```

3. **Password Hashing with bcryptjs**

```js
const bcrypt = require("bcryptjs");
const hashed = await bcrypt.hash(req.body.password, 10);
```

---

#### 🔹 Section 3: Aptitude

1. **Gain %**: SP = 140% of CP → After 10% discount = 126% → Gain = 26%
2. **Work Problem**: 6 × 12 = x × 9 ⇒ x = 8 men
3. **Divisibility of 924**: ✅ Yes, divisible by 2, 3, and 6
4. **25% of 640**: = 160
5. **Next Number in Series**: ×2 ⇒ 2, 4, 8, 16, **32**

---

#### 🔹 Section 4: Behavioral

1. **Team Challenge**: Mention a college project or team task with challenges like communication gaps or role conflicts. Explain how you contributed to solving it.

2. **Why Amazon (MERN Stack Role)**: Talk about Amazon’s innovation culture, large-scale systems, and your interest in solving problems using MERN technologies.

---

#### 🧠 Flashcards for Quick Revision

| 🔑 Topic                  | 💡 Flashcard                               |
| ------------------------- | ------------------------------------------ |
| **Palindrome**            | `str === str.split('').reverse().join('')` |
| **First Duplicate**       | Use `Set()` to track seen elements         |
| **Factorial (Recursion)** | `return n * factorial(n - 1)`              |
| **MongoDB Connect**       | `mongoose.connect(URI)`                    |
| **Hashing**               | `bcrypt.hash(password, saltRounds)`        |
| **JWT Middleware**        | `jwt.verify(token, secret)`                |
| **Gain %**                | (SP - CP) / CP × 100                       |
| **Time & Work**           | Men × Days = Constant                      |
| **Divisibility by 6**     | Must be divisible by 2 **and** 3           |
| **Percentages**           | % = (part / whole) × 100                   |

---

Stay consistent 💪

\#30DayInterviewCrackChallenge #100DaysOfCode
