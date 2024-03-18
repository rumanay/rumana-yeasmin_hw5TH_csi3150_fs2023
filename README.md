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
```
## Project Directroy 
C:\Desktop\GitHub\quizapp
├─ index.html
├─ css
|  └─ style.css
├─ js
|  ├─ questions.js
|  └─ quizApp.js
└─ README.md
```
## Index.html code explanation 
```
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
```
- <head>: This section contains metadata about the HTML document, such as character encoding, viewport settings, and the title of the page.
- <script src="js/questions.js" defer></script>: This imports an external JavaScript file named "questions.js" located in the "js" folder. The defer attribute tells the browser to defer executing the script until after the document has been parsed. This is typically used to ensure that scripts do not block the rendering of the page.
- <link rel="stylesheet" href="css/style.css">: This links an external CSS file named "style.css" located in the "css" folder. This CSS file likely contains styling rules for the HTML elements in the document.
- </head>: This tag marks the end of the <head> section.

```
<body>
    <!-- Quiz START Button -->
    <div class="start_btn"><button>Start Quiz</button></div>

    <!-- Instruction box wrapper -->
    <div class="info_box">
        <div class="info-title"><span>Some Rules of this Quiz</span></div>
        <div class="info-list">
            <div class="info">1. You will have only <span>15 seconds</span> per each question.</div>
            <div class="info">2. Once you select your answer, it can't be undone.</div>
            <div class="info">3. You can't select any option once time goes off.</div>
            <div class="info">4. You can't exit from the Quiz while you're playing.</div>
            <div class="info">5. You'll get points on the basis of your correct answers.</div>
        </div>
        <div class="buttons">
            <button class="quit">Exit Quiz</button>
            <button class="restart">Continue</button>
        </div>
    </div>
```
- Body Section - Start Button
- <div class="start_btn"><button>Start Quiz</button></div>: Creates a button labeled "Start Quiz" to initiate the quiz.
Instruction Box
- <div class="info_box">: Wraps the instruction box for the quiz.
- <div class="info-title"><span>Some Rules of this Quiz</span></div>: Contains a title for the instruction box.
- <div class="info-list">: Contains a list of rules for the quiz.
- Rules are presented within individual <div> elements.
- <div class="buttons">: Wraps buttons within the instruction box.
- <button class="quit">Exit Quiz</button>: Allows participants to exit the quiz.
- <button class="restart">Continue</button>: Allows participants to proceed with the quiz after reading the instructions.

```
<!-- Quiz Box -->
    <div class="quiz_box">
        <header>
            <div class="title">Demo Quiz App in JavaScript</div>
            <div class="timer">
                <div class="time_left_txt">Time Left</div>
                <div class="timer_sec">15</div>
            </div>
            <div class="time_line"></div>
        </header>
        <section>
            <div class="que_text">
                <!-- Insert questions from ./js/questions.js -->
            </div>
            <div class="option_list">
                <!-- Insert options to questions from ./js/questions.js -->
            </div>
        </section>

        <!-- footer of Quiz Box -->
        <footer>
            <div class="total_que">
                <!-- insert Question Count Number dynamically from JavaScript App logic -->
            </div>
            <button class="next_btn">Next Que</button>
        </footer>
    </div>

    <!-- Result Box -->
    <div class="result_box">
        <div class="icon">
            <i class="fas fa-crown"></i>
        </div>
        <div class="complete_text">You've completed the Quiz!</div>
        <div class="score_text">
            <!-- insert dynamic user score as Result from JavaScript -->
        </div>
        <div class="buttons">
            <button class="restart">Replay Quiz</button>
            <button class="quit">Quit Quiz</button>
        </div>
    </div>

</body>
```

```
Quiz Box:
 - <header>: Contains the title of the quiz, timer display, and a time line.
<section>: Contains the question text and options list.
<div class="que_text">: Placeholder for the question text.
<div class="option_list">: Placeholder for the options list.
<footer>: Contains the total question count and a button to navigate to the next question.
Result Box:
- <div class="icon">: Displays an icon (a crown in this case) to represent completion.
- <div class="complete_text">: Displays a completion message.
- <div class="score_text">: Placeholder for displaying the user's score.
- <div class="buttons">: Contains buttons for replaying or quitting the quiz.
```






