### DSA: Arrays
Definition: Array is a linear data structure that stores values in a contiguous memory location of the same type. Each element is accessed via index starting from 0.

Code Example (Find first number divisible by 7):
```
int[] arr = {2, 4, 9, 23, 41, 15};
for (int i = 0; i < arr.length; i++) {
    if (arr[i] % 7 == 0) {
        System.out.println(arr[i]);
        break;
    }
}
```
Output: 42 (if it were present)

### MERN Stack
What is MERN?
------------
|Stack Part	|Technology	Role|
|-----------|---------------|
| M	       |  MongoDB	Database|
|  E	      |   Express.js	Server-side framework|
|  R	      |   React.js	Frontend UI|
|  N	      |   Node.js	JavaScript runtime for backend|

MERN Setup Steps:
*Create a folder in your computer.
*Open that folder in VS Code.
*Initialize Node.js project:
```
npm init -y
```

Install Express:
```
npm install express
```

Create server.js inside the folder.
🔹 Express.js Sample Code
```
const express = require('express');
const app = express();

app.get('/', (req, res) => {
  res.send('Server is running');
});

const PORT = 5000;
app.listen(PORT, () => {
  console.log(`Server is running on port ${PORT}`);
});
```
Run using: node server.js
Open in browser: http://localhost:5000

### Aptitude: Divisibility Rules
|Number	|Divisible If...|
|-------|----------------|
|2	|Last digit is even (0, 2, 4, 6, 8)|
|3	|Sum of digits divisible by 3|
|4	|Last 2 digits divisible by 4|
|5	|Last digit is 0 or 5|
|6	|Divisible by both 2 and 3|
|8	|Last 3 digits divisible by 8|
|9	|Sum of digits divisible by 9|
|11	|Alternate sum of digits divisible by 11|

Example:
Is 438 divisible by 3 and 9?

Sum = 4 + 3 + 8 = 15

15 is divisible by 3 ✅

15 is NOT divisible by 9 ❌
✅ Divisible by 3 only

### Behavioral Interview Prep
Q: Tell me about yourself?
```
Hello, my name is Snehlata. I recently completed my B.Tech in Computer Science from Radharaman Institute of Technology & Science with a CGPA of 8.36.
I’m currently preparing for a MERN stack development role.
I have experience with core Java, HTML, CSS, JavaScript, and have built projects like Tic-Tac-Toe and a DevTinder app.
I’m punctual, focused, and excited to continue learning and contributing to a top company.
```
