#### 🚀 Day 4 – 30-Day Interview Crack Challenge

Welcome to Day 4! Today’s goal was to strengthen core skills across all four preparation areas: DSA, MERN, Aptitude, and Interview Preparation.

---

#### ✅ DSA – String Manipulation

#### Topics Covered:
- String concatenation, slicing, comparison
- Reversing a string
- Palindrome check
- Character counting

#### Sample Problems Practiced:
1. Reverse a string
2. Check if a string is a palindrome
3. Count characters in a string

#### Example Code:
```js
// Reverse a string in JavaScript
const str = "hello";
const reversed = str.split("").reverse().join("");
console.log(reversed); // "olleh"
```
---
#### ✅ MERN Stack – User Schema & Validation
Tasks Done:
Added validation rules to the User schema in Mongoose

Used required, match (email format), and minLength in schema

Tested validation errors via Postman

Sample User Schema:
```
const mongoose = require("mongoose");

const userSchema = new mongoose.Schema({
  name: {
    type: String,
    required: true,
    minLength: 2
  },
  email: {
    type: String,
    required: true,
    match: /.+\@.+\..+/
  },
  password: {
    type: String,
    required: true,
    minLength: 6
  }
});

module.exports = mongoose.model("User", userSchema);
```
---
#### ✅ Aptitude – Percentages
Topics Covered:
Percentage increase and decrease

Basic percentage conversions and shortcuts

Practice Questions:
Calculate percentage marks (e.g., 60 out of 80)

Price increase/decrease scenarios

Salary hike reverse-calculation

Discount-based original price finding

#### 📝 Solved 4–5 problems based on real-life scenarios.
---
#### ✅ Behavioral Interview – Strengths & Weaknesses
STAR-Based Answer
Q: What are your strengths and weaknesses?

S – Situation: Led backend and team management during college hackathon.
T – Task: Build backend API with Node & MongoDB, manage timelines.
A – Action: Divided tasks, helped teammates, wrote modular backend code.
R – Result: Completed on time, praised for teamwork and learning attitude.

Strengths:
Problem-solving

Team collaboration

Curiosity & discipline

Weakness:
Public speaking (improving via practice and mock sessions)

---
#### 📌 Summary
* Track	Topic	Status
* DSA	String Manipulation	✅
* MERN Stack	Schema & Validation	✅
* Aptitude	Percentages	✅
* Interview	Strengths & Weaknesses (STAR)	✅

