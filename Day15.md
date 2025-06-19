# ✅ Day 15: Core Concepts, Practice & Progress

---

## 🧠 DSA – Sorting (Part 1)
### 📚 Learn:
* Bubble Sort

* Selection Sort

* Insertion Sort
* 
(Understand Time Complexities: Best, Worst, Average)

#### 🧪 Practice (Implement all 3):
Bubble Sort – ascending & descending

Selection Sort – on a random array

Insertion Sort – insert new elements into a sorted list

#### 📌 Bonus:
Write a custom comparator for sorting an array of objects by age or marks.

---

## 💻 MERN Stack – Project Feature: Tasks CRUD
### 🚧 Goal:
Add Task Routes: Create, Read, Update, Delete

🔨 Backend (Express + MongoDB):
✅ POST /tasks: Create a new task

✅ GET /tasks: Fetch all tasks (only for logged-in user)

✅ PUT /tasks/:id: Update task

✅ DELETE /tasks/:id: Delete task

📦 Mongoose Schema:
```
const taskSchema = new mongoose.Schema({
  title: String,
  completed: Boolean,
  userId: {
    type: mongoose.Schema.Types.ObjectId,
    ref: 'User',
    required: true
  }
});
```
#### 🔒 Don’t forget:
Protect all routes using your JWT auth middleware.

---

## 📐 Aptitude – Averages + Ages
### 📚 Learn:
Average = (Sum of observations) / (Number of observations)

Problems on:

* Average of groups

* Finding missing data using average

* Age-based word problems

#### 🧪 Practice:
8–10 MCQs from each type

Try mock set from previous company papers (Wipro/Capgemini-style)

---

## 🗣️ Behavioral Interview – STAR Format Training
### 🎯 Today’s Focus:
 * "Describe a time you solved a difficult problem."

#### 👉 Use the STAR method:

Situation – set the context

Task – what needed to be done

Action – what you did

Result – how it ended positively

Write your answer and time it to 90 seconds.

---

## 📝 Deliverables by End of Day 15
Task	Output
#### 🔢 DSA Sorting	JS functions for Bubble, Selection, Insertion Sort
#### 🛠️ Task Routes	All 4 task APIs with JWT protection (CRUD complete)
#### 📊 Aptitude	Practice sheet: 10 problems on averages/ages
#### 🗣️ Behavioral Qn	Answer written + practiced using STAR format
#### 📌 Git Commit	Push changes to backend repo


