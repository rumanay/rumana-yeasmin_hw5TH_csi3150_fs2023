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
- `<head>`: This section contains metadata about the HTML document, such as character encoding, viewport settings, and the title of the page.

- `<script src="js/questions.js" defer></script>`: This imports an external JavaScript file named "questions.js" located in the "js" folder. The defer attribute tells the browser to defer executing the script until after the document has been parsed. This is typically used to ensure that scripts do not block the rendering of the page.

- `<link rel="stylesheet" href="css/style.css">`: This links an external CSS file named "style.css" located in the "css" folder. This CSS file likely contains styling rules for the HTML elements in the document.

- `</head>`: This tag marks the end of the `<head>` section.

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
* **Class: `start_btn`**
    - Description: A button element that users can click to start or begin answering questions.

* **Class: `info_box`**
    - Description: A wrapper containing the rules for answering questions, including a title, a list of rules, and buttons (quit and start).

* **Class: `quiz_box`**
    - Description: The main answering area, including title, timer, question text, answer options, dynamic statistics questions, and next question button.

* **Class: `result_box`**
    - Description: Result display area, including a crown icon, completion text, user score text, and restart/exit button.
1. **`start_btn` Class:**
    - This class represents a button that initiates the quiz or starts the process of answering questions.

2. **`info_box` Class:**
    - This class encapsulates information and rules related to answering questions.
    - It typically contains:
        - A title describing the purpose or topic of the quiz.
        - A list of rules specifying guidelines for answering questions.
        - Buttons for actions like quitting or starting the quiz.
3. **`quiz_box` Class:**
    - This class denotes the primary area where users interact with questions and answers during the quiz.
    - Components within this box usually include:
        - A title indicating the section or topic of the quiz.
        - A timer displaying the remaining time for each question.
        - The question text prompting the user for an answer.
        - Options for the user to select as answers.
        - Dynamic statistics indicating the current question number or progress.
        - A button to proceed to the next question.
4. **`result_box` Class:**
    - This class represents the section where the quiz results are displayed.
    - Contents of this box commonly include:
        - An icon, often a crown, symbolizing completion.
        - Text indicating the completion of the quiz.
        - User score displayed dynamically.
        - Buttons for restarting the quiz or exiting.


## styles.css code explanation 
```
/* importing google fonts */
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@200;300;400;500;600;700&display=swap");
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Poppins", sans-serif;
}

body {
  background: #a020f0;
}

::selection {
  color: #fff;
  background: #a020f0;
}

.start_btn,
.info_box,
.quiz_box,
.result_box {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
}

.info_box.activeInfo,
.quiz_box.activeQuiz,
.result_box.activeResult {
  opacity: 1;
  z-index: 5;
  pointer-events: auto;
  transform: translate(-50%, -50%) scale(1);
}
```
### CSS Code Explanation:

#### Importing Google Fonts:
This section imports the Google Font "Poppins" with multiple weights to be used in the project.

#### Global Styles:
This section sets global styles for all elements:
- Resets margin and padding to zero.
- Ensures that box-sizing is border-box for all elements.
- Sets the default font family to "Poppins" with a fallback of sans-serif.

#### Body Styles:
This section sets the background color of the body to a shade of purple.

#### Selection Styles:
This section styles the text selection with white text on a purple background.

#### Box Styles:
This section sets the positioning and box-shadow for the main components of the project (start button, info box, quiz box, result box).

#### Active States:
This section defines the active state styles for info box, quiz box, and result box.

#### Button Styles:
This section styles the start button with a specific font size, weight, padding, color, background, and border-radius.

#### Info Box Styles:
This section styles the info box with a specific width, background color, border-radius, initial opacity, and transition effects.

#### Active Info Box Styles:
This section defines the active state styles for the info box.



