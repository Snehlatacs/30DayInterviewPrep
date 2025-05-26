### 📘 DSA Day 2 – Sliding Window Approach

This day's focus was on understanding and implementing the **Sliding Window** technique to optimize problems like finding the **maximum sum subarray of size K** in an array.

---

#### ✅ Problem Statement

Given an array and a number `K`, find the **maximum sum of a subarray** of size `K`.

---
-------------------------------------------
#### 🧪 Brute Force Approach

```
int maxSum = Integer.MIN_VALUE;
for (int i = 0; i <= arr.length - k; i++) {
    int sum = 0;
    for (int j = 0; j < k; j++) {
        sum += arr[i + j];
    }
    maxSum = Math.max(maxSum, sum);
}
return maxSum;
```
##### ❌ Time Complexity:
Outer Loop: O(n - k + 1) ≈ O(n)

Inner Loop: O(k)

Total Time: O(n × k)
-----------------------------------------------------------
##### 🚀 Optimized – Sliding Window Approach
Instead of recalculating the sum every time, subtract the element that goes out of the window and add the new incoming element.
```
int maxSumSubarray(int[] arr, int k) {
    int n = arr.length;
    if (n < k) {
        System.out.println("Array length is less than k");
        return -1;
    }

    int windowSum = 0;
    for (int i = 0; i < k; i++) {
        windowSum += arr[i];
    }

    int max = windowSum;

    for (int i = 1; i <= n - k; i++) {
        windowSum = windowSum - arr[i - 1] + arr[i + k - 1];
        max = Math.max(max, windowSum);
    }

    return max;
}
```
---------------------------------
#### 💡 Why Sliding Window?
Brute force has redundant calculations. For example:

From [1, 4, 2] to [4, 2, 20], the values 4 and 2 are recalculated unnecessarily.
Sliding Window avoids this by updating just the entering and exiting values.

#### 📊 Time Complexity (Sliding Window)
Initialization: O(k)

Update Loop: O(n - k)

Total Time: O(n)

#### 🧮 Sample Example

Array = [1, 4, 2, 10, 23, 3, 1, 0, 20]
k = 3

Window 6: [3, 1, 0] → sum = 4  
Window 7: [1, 0, 20] → sum = 21

#### ✅ Maximum sum = 21
---------------------
#### 📌 Summary
Method	Time Complexity
Brute Force	O(n × k)
Sliding Window	O(n)
-----------------------------
#### 📅 Day Summary
------------------
Understood brute force limitations.

Optimized with Sliding Window.

Implemented and tested example Java code.

--------------------------------------------------------------
---------------------------------------------------------------
### 📘 Day 2 – MERN Stack: MongoDB + Express.js Integration

------------

#### ✅ Goals for the Day
---------------------
- Initialize a Node.js backend project.
- Install required dependencies: `express`, `mongoose`, `dotenv`.
- Connect Express server to **MongoDB Atlas** using Mongoose.
- Create a simple API (`/users`) with POST request handling.
- Store MongoDB URI securely in a `.env` file.
- Test everything using Postman or Thunder Client.

---

### 🏗️ Project Setup
----------
#### 1. Initialize Project

```
npm init -y
npm install express mongoose dotenv
```
#### 2. Folder Structure

mern-backend/
│
├── index.js
├── .env
├── package.json
📄 index.js

```
const express = require("express");
const mongoose = require("mongoose");
require("dotenv").config();

const app = express();
app.use(express.json());

// Connect to MongoDB Atlas
mongoose.connect(process.env.MONGO_URI, {
  useNewUrlParser: true,
  useUnifiedTopology: true,
})
.then(() => console.log("✅ MongoDB Connected Successfully"))
.catch((err) => console.error("❌ DB Connection Error:", err));

// User Schema
const userSchema = new mongoose.Schema({
  name: String,
  email: String,
});
const User = mongoose.model("User", userSchema);

// GET route
app.get("/", (req, res) => {
  res.send("🚀 Server & MongoDB connected");
});

// POST route
app.post("/users", async (req, res) => {
  try {
    const user = new User(req.body);
    const savedUser = await user.save();
    res.status(201).json(savedUser);
  } catch (err) {
    res.status(400).json({ error: err.message });
  }
});

// Start Server
const PORT = 5000;
app.listen(PORT, () => {
  console.log(`🌐 Server running at http://localhost:${PORT}`);
});
```
##### 🔐 .env File
```
MONGO_URI=mongodb+srv://<username>:<password>@cluster0.mongodb.net/mernapp?retryWrites=true&w=majority
```
#### ⚠️ Don't forget to add .env to .gitignore.

#### 🧪 API Testing (using Postman or Thunder Client)
GET /
Response: "🚀 Server & MongoDB connected"

POST /users
Body (JSON):
```
{
  "name": "Snehlata",
  "email": "sneh@example.com"
}
```
Response:
```
{
  "_id": "unique_object_id",
  "name": "Snehlata",
  "email": "sneh@example.com",
  "__v": 0
}
```
-----------

### 📊 Day 2 Progress Table
Task	Status
Initialized Node.js project (npm init)	✅
Installed dependencies (express, mongoose, dotenv)	✅
Connected Express app to MongoDB Atlas	✅
Created .env file and used environment variables securely	✅
Built a working /users POST API route	✅
Tested API using Postman	✅
Debugged MongoDB connection issues	✅
Verified working server with GET /	✅

-----------
### 🧠 Learnings
Mongoose makes it easy to work with MongoDB using schemas.

.env file keeps credentials secure.

Express routes (GET, POST) used for backend communication.

MongoDB Atlas allows cloud-based database hosting.

--------------------
---------------------

#### 📘 Day 2 – Aptitude: Percentages, Number Series & Puzzles (Basics)

---

#### ✅ Goals for the Day

- Understand and practice basic **Percentage** problems.
- Learn how to solve **Number Series** questions.
- Get introduced to **Puzzle** problem types commonly asked in interviews.

---

#### 📊 Percentages

### 🔹 Basic Formula:

`Percentage (%) = (Value / Total) × 100`

### 🔹 Examples:

1. **What is 20% of 150?**  
   `= (20 / 100) × 150 = 30`

2. **If a value increases by 25%, it becomes?**  
   `New Value = Original + 25% of Original = Original × 1.25`
   
---   

4. **Shortcut Tips:**
| Fraction        | Percentage |
|-----------------|------------|
| 1/2             | 50%        |
| 1/4             | 25%        |
| 1/5             | 20%        |
| 1/8             | 12.5%      |
| 1/10            | 10%        |

---

#### 🔢 Number Series

#### 🔹 Concept:

Identify the **pattern** or **rule** used to generate the sequence.

### 🔹 Example Questions:

1. **2, 4, 8, 16, ?**  
   `Pattern: ×2 → Next is 32`

2. **5, 11, 17, 23, ?**  
   `Pattern: +6 → Next is 29`

3. **81, 27, 9, 3, ?**  
   `Pattern: ÷3 → Next is 1`

#### 🔍 Tips:

- Check for differences (+/-)
- Try multiplication/division
- Look for alternating patterns
- Check squares, cubes, or primes

---

#### 🧩 Puzzle Basics

#### 🔹 Puzzle Types Practiced:

- **Arrangement puzzles** (seating/circular/linear)
- **Family relation puzzles** (blood relations, tree logic)
- **Position-based puzzles** (who sits where, who is taller/shorter)

#### 🔹 Example:

**Q: A, B, C, D, E are sitting in a row. C is to the right of A but left of D. Who is in the middle?**

🧠 Try visualizing positions.

**Answer: Likely C**

---

## 📝 Day Summary

| Topic         | Practiced Concepts                    | Status |
|---------------|----------------------------------------|--------|
| Percentages   | Basic formula, fraction to percent     | ✅      |
| Number Series | +/-, ×/÷ patterns, skipping, primes    | ✅      |
| Puzzles       | Basic linear arrangements, logic       | ✅      |

---

#### 🔁 Revision Tips

- Practice at least **5-10 questions** from each topic daily.
- Focus on **accuracy first**, then **speed**.
- Use timer-based quizzes to build real exam strategy.

---
---
#### 💼 Day 2 – Behavioral Interview Prep

#### 🎯 Focus Question: “Why Google?”

---

#### ✅ Objective

Prepare a strong, confident, beginner-friendly answer to the frequently asked HR question:

> **"Why do you want to work at Google?"**

---

#### 🗣️ Sample Answer (Beginner Level – Personalized)

I want to join Google because it's a company that sets the global benchmark for innovation, creativity, and impact.

As someone starting my software development journey, I truly admire how Google continues to solve large-scale problems and build products like Google Search, Gmail, and Android that billions of people rely on every day.

I'm excited by the opportunity to grow in a company that values learning, collaboration, and curiosity. Google’s engineering culture, focus on open-source contributions, and encouragement of experimentation align with my own goals of becoming a better developer and making a meaningful impact on people's lives.

Joining Google would not only be a dream opportunity but also the perfect place to learn from the best and contribute to something that matters globally.

---

#### 🌟 STAR Format Breakdown

| Section         | Details                                                                 |
|----------------|-------------------------------------------------------------------------|
| **S**ituation   | Recent B.Tech graduate, MERN stack learner                             |
| **T**ask        | Looking to grow in a tech environment that supports innovation          |
| **A**ction      | Practicing coding daily, building projects, preparing for interviews    |
| **R**esult      | Eager to join Google to grow professionally and contribute meaningfully |

---

#### 🧠 Tips to Personalize

- Mention a Google product you admire (e.g., Google Maps, Chrome, TensorFlow).
- Talk about your learning mindset and desire for mentorship.
- Show how Google’s values align with yours (inclusion, curiosity, innovation).

---

#### 📝 Summary

| Task                        | Status |
|-----------------------------|--------|
| Understood STAR technique   | ✅      |
| Practiced “Why Google?”     | ✅      |
| Personalized the response   | ✅      |
| Ready for mock delivery     | ✅      |

---
