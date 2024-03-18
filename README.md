Click Here to take the Quiz: <a href="https://xiachen97.github.io/XiaChen_hw5TH_csi3150_fs2023/">Click here to quiz!<a/>

# Quiz App Tutorial and code Explanation 
## Problem Statement of the Page
This tutorial guides you through building a quiz app—a web application designed to provide users with a fun and interactive learning experience by testing their knowledge through a set of questions. Users will be able to participate in timed quizzes, receive real-time feedback on their answers, and view their final scores
## Functional Features
- Start Quiz Button: Users can initiate the quiz by clicking the "start quiz" button.
- Instruction Box: Users are presented with rules before starting the quiz, guiding them on how to proceed or exit.
- Timed Questions: Each question is displayed individually with a time limit of 15 seconds, enhancing the challenge.
- Answer Selection: Users must choose an answer before the timer expires, - promoting active participation.
- No Answer Change: Once an answer is selected, users cannot alter their choice, adding to the quiz's authenticity.
- Immediate Feedback: The app instantly informs users whether their answer is correct or incorrect, aiding in learning.
- Score Calculation: Users' final scores are computed based on the number of correct answers, providing a measure of performance.
- Replay or Exit: Upon completing the quiz, users have the option to replay it for further practice or exit the app as desired.
## Programming language
- HTML: Used for creating the structure and content of the quiz app's web pages.
- CSS: Employed to style the HTML elements, enhancing the visual presentation and user interface of the app.
- JavaScript: Utilized for implementing interactive functionalities such as timer management, question loading, answer validation, score calculation, and result display, making the quiz app dynamic and engaging.

## Project Directroy 
C:\Desktop\GitHub\quizapp
├─ index.html
├─ css
|  └─ style.css
├─ js
|  ├─ questions.js
|  └─ quizApp.js
└─ README.md

## Index.html code explanation 

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Quiz App Demo</title>

    <!-- CSS FILE -->
    <link rel="stylesheet" href="css/style.css">
    <!-- This is my personal font awesome kit code. you will have to add your own after you register with email-->
    <script src="https://kit.fontawesome.com/4a4f4b55b0.js" crossorigin="anonymous"></script>

     <!-- Add questions list -->
    <script src="js/questions.js" defer></script>

    <!-- Main logic of the app -->
    <script src="js/quizApp.js" defer></script>
</head>





