# 📘 Day 8–14: Revision Notes + Mock Test
---
## 🧠 DSA Topics Covered
### Day 8:

Recap Arrays (prefix sum, sliding window)

Practice: Kadane’s Algorithm, Two-pointer approach

### Day 9:

Strings deep dive: isIsogram, character replacement, longest unique substring

### Day 10:

Matrix problems: Spiral traversal, transpose, diagonal sum

### Day 11:

Recursion: Fibonacci, print all subsequences, sum of digits

### Day 12:

HashMap practice: Frequency map, anagram group, majority element

### Day 13:

DSA Mock Set Practice (5 medium-level problems, mix of array/string/recursion)

### Day 14:

DSA Debugging Round: Identify and fix errors in existing solutions

---

## 💻 MERN Stack Progress
### Day 8:

Refresh: RESTful API structure

Routes for /login, /logout

### Day 9:

Implement Login with JWT token generation

### Day 10:

Add Auth Middleware, Protect Routes (e.g., /dashboard)

### Day 11:

Create basic frontend with fetch() API call

### Day 12:

Setup CORS, connect backend & frontend

### Day 13:

Review full Auth flow: Registration → Login → JWT → Protected Route

### Day 14:

Mini MERN Debug Task (Fix a broken login/auth)

---

## 📐 Aptitude Topics Covered
### Day 8:

Time, Speed, Distance: Train, Boat problems

### Day 9:

Ratios & Proportions: Basic + Real-life Qs

### Day 10:

Simple Interest / Compound Interest

### Day 11:

Mixtures & Alligation

### Day 12:

Data Interpretation (basic bar/line/table)

### Day 13:

Solve 15 aptitude problems (revision)

### Day 14:

Aptitude Mock Test #2

---

## 🗣️ Behavioral Interview Prep
** Topics Covered: **

* When did you take initiative?

* Explain a time you failed at something.

* Where do you see yourself in 5 years?

* Describe a situation where you adapted to change quickly.

---

## 📝 Mock Test Paper (Day 8–14)

---

🔹 Section 1: DSA (3 Questions)
Given an array, find the maximum sum of a subarray (Kadane's Algorithm).

Check if a string has all unique characters (JavaScript).

Use recursion to generate all subsets of a string.

---

🔹 Section 2: MERN Stack (3 Questions)
Write login route logic that generates JWT and returns it.

Create a middleware to decode JWT and extract user info.

Write frontend code using fetch() to POST login credentials and handle the token.

---

🔹 Section 3: Aptitude (5 Questions)
A train 150m long passes a pole in 15 seconds. Find its speed in km/h.

Ratio of income to expenditure is 5:4. If savings are ₹5000, what is the income?

Find the compound interest on ₹5000 for 2 years at 10% p.a.

A container contains 40L of milk. 8L is replaced with water. This process is repeated 2 times. Find the final quantity of milk.

What is the average of first 10 natural numbers?

---

🔹 Section 4: Behavioral (2 Questions)
Tell me about a time you had to learn something quickly for a project.

What would you do if your team member missed a deadline?

----

## 🧾 Mock Test Answer Key
### 🔹 Section 1: DSA
** Kadane's Algorithm **
```
function maxSubArraySum(arr) {
  let max = arr[0], curr = arr[0];
  for (let i = 1; i < arr.length; i++) {
    curr = Math.max(arr[i], curr + arr[i]);
    max = Math.max(max, curr);
  }
  return max;
}
```
** All Unique Characters **
```
function hasUniqueChars(str) {
  let set = new Set();
  for (let ch of str) {
    if (set.has(ch)) return false;
    set.add(ch);
  }
  return true;
}
```
** All Subsets (Recursion) **
```
function subsets(str, i = 0, curr = "") {
  if (i === str.length) {
    console.log(curr);
    return;
  }
  subsets(str, i + 1, curr + str[i]);
  subsets(str, i + 1, curr);
}
```
--- 

### 🔹 Section 2: MERN Stack
** Login Route with JWT **
```
const jwt = require("jsonwebtoken");
router.post("/login", async (req, res) => {
  const user = await User.findOne({ email: req.body.email });
  const isMatch = await bcrypt.compare(req.body.password, user.password);
  if (isMatch) {
    const token = jwt.sign({ id: user._id }, process.env.JWT_SECRET);
    res.send({ token });
  } else {
    res.status(400).send("Invalid credentials");
  }
});
```
** Auth Middleware **

```
function auth(req, res, next) {
  const token = req.header("Authorization");
  if (!token) return res.status(401).send("Unauthorized");
  try {
    req.user = jwt.verify(token, process.env.JWT_SECRET);
    next();
  } catch {
    res.status(400).send("Invalid Token");
  }
}
```
** Frontend fetch login **
```
fetch("/login", {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({ email, password })
})
  .then(res => res.json())
  .then(data => localStorage.setItem("token", data.token));
```
---

### 🔹 Section 3: Aptitude
Train Speed: (150/15) = 10 m/s = 36 km/h

Income: 1 part = ₹5000 → 5 parts = ₹25,000

CI: ₹5000 × (1.1)^2 – 5000 = ₹1050

Milk left: M = 40 × (1 – 8/40)^2 = 25.6 L

Average: (1+2+…+10)/10 = 55/10 = 5.5

---

### 🔹 Section 4: Behavioral
Quick Learning: Explain learning React in 2–3 days to complete a project milestone.

Missed Deadline: Talk about your problem-solving and empathy — offering help, adjusting timelines.

---

## 🧠 Flashcards for Quick Revision
|🔑 Topic	|💡 Flashcard|
|---------|-------------|
|Kadane’s Algorithm|	max = max(curr, max + arr[i])|
|Subsets (Recursion)	|Include + exclude character recursively|
|Train Speed	|Speed = Distance / Time|
|JWT	|jwt.sign(payload, secret)|
|Login Route	|Compare password, generate token|
|Frontend Fetch	|fetch() → POST → handle token|
|CI Formula|	P(1 + r/100)^n|
|Alligation	|Repeated replacement → use (1 - x/V)^n|


