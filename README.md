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


## question.js Code Explanation:
```
let questions = [
  {
    numb: 1,
    question: "What does HTML stand for?",
    answer: "Hyper Text Markup Language",
    options: [
      "Hyper Text Preprocessor",
      "Hyper Text Markup Language",
      "Hyper Text Multiple Language",
      "Hyper Tool Multi Language",
    ],
  },
```
#### Creating an Array of Objects:
This code snippet creates an array named `questions` that contains objects. Each object represents a single quiz question and its associated information.
- The object properties include:
  - `numb`: Represents the question number.
  - `question`: Represents the question itself.
  - `answer`: Represents the correct answer to the question.
  - `options`: Represents an array of options for the question, including the correct answer as well as other choices.

#### Example Objects:
1. **Object 1:**
   - Question Number: 1
   - Question: "What does HTML stand for?"
   - Correct Answer: "Hyper Text Markup Language"
   - Options: ["Hyper Text Preprocessor", "Hyper Text Markup Language", "Hyper Text Multiple Language", "Hyper Tool Multi Language"]


## quiz.js Code Explanation:
```
//selecting all required elements from html document
const start_btn = document.querySelector(".start_btn button");
const info_box = document.querySelector(".info_box");
const exit_btn = info_box.querySelector(".buttons .quit");
const continue_btn = info_box.querySelector(".buttons .restart");
const quiz_box = document.querySelector(".quiz_box");
const result_box = document.querySelector(".result_box");
const restart_quiz = result_box.querySelector(".buttons .restart");
const quit_quiz = result_box.querySelector(".buttons .quit");
const option_list = document.querySelector(".option_list");
const time_line = document.querySelector("header .time_line");
const timeText = document.querySelector(".timer .time_left_txt");
const timeCount = document.querySelector(".timer .timer_sec");
const next_btn = document.querySelector("footer .next_btn");
const bottom_ques_counter = document.querySelector("footer .total_que");

```
#### Selecting Required HTML Elements:
This code snippet selects various elements from the HTML document using querySelector method and assigns them to respective variables.
- `start_btn`: Selects the button element with the class "start_btn" inside the HTML document.
- `info_box`: Selects the element with the class "info_box" inside the HTML document.
- `exit_btn`: Selects the button with the class "quit" inside the "info_box" element.
- `continue_btn`: Selects the button with the class "restart" inside the "info_box" element.
- `quiz_box`: Selects the element with the class "quiz_box" inside the HTML document.
- `result_box`: Selects the element with the class "result_box" inside the HTML document.
- `restart_quiz`: Selects the button with the class "restart" inside the "result_box" element.
- `quit_quiz`: Selects the button with the class "quit" inside the "result_box" element.
- `option_list`: Selects the element with the class "option_list" inside the HTML document.
- `time_line`: Selects the element with the class "time_line" inside the "header" element.
- `timeText`: Selects the element with the class "time_left_txt" inside the "timer" element.
- `timeCount`: Selects the element with the class "timer_sec" inside the "timer" element.
- `next_btn`: Selects the button with the class "next_btn" inside the "footer" element.
- `bottom_ques_counter`: Selects the element with the class "total_que" inside the "footer" element.

```
// if startQuiz button clicked
start_btn.addEventListener("click", (e) => {
  info_box.classList.add("activeInfo"); //show info box
});

// if exitQuiz button clicked
exit_btn.addEventListener("click", (e) => {
  info_box.classList.remove("activeInfo"); //hide info box
});

// if continueQuiz button clicked
continue_btn.addEventListener("click", (e) => {
  info_box.classList.remove("activeInfo"); //hide info box
  quiz_box.classList.add("activeQuiz"); //show quiz box
  showQuetions(0); //calling showQestions function
  queCounter(1); //passing 1 parameter to queCounter
  startTimer(15); //calling startTimer function
  startTimerLine(0); //calling startTimerLine function
});

// Variables to control quiz operations
let timeValue = 15;
let que_count = 0;
let que_numb = 1;
let userScore = 0;
let counter;
let counterLine;
let widthValue = 0;

// if restartQuiz button clicked
restart_quiz.addEventListener("click", (e) => {
  quiz_box.classList.add("activeQuiz"); //show quiz box
  result_box.classList.remove("activeResult"); //hide result box
  timeValue = 15;
  que_count = 0;
  que_numb = 1;
  userScore = 0;
  widthValue = 0;
  showQuetions(que_count); //calling showQestions function
  queCounter(que_numb); //passing que_numb value to queCounter
  clearInterval(counter); //clear counter
  clearInterval(counterLine); //clear counterLine
  startTimer(timeValue); //calling startTimer function
  startTimerLine(widthValue); //calling startTimerLine function
  timeText.textContent = "Time Left"; //change the text of timeText to Time Left
  next_btn.classList.remove("show"); //hide the next button
});
```
### JavaScript Code Explanation:

#### Event Listeners:
- `start_btn.addEventListener("click", (e) => {...})`: Adds an event listener to the "start_btn" button. When clicked, it shows the info box by adding the "activeInfo" class.
- `exit_btn.addEventListener("click", (e) => {...})`: Adds an event listener to the "exit_btn" button inside the info box. When clicked, it hides the info box by removing the "activeInfo" class.
- `continue_btn.addEventListener("click", (e) => {...})`: Adds an event listener to the "continue_btn" button inside the info box. When clicked, it hides the info box, shows the quiz box, calls the `showQuetions()` function to display the first question, calls the `queCounter()` function to set the question number, and starts the timer by calling the `startTimer()` and `startTimerLine()` functions.

#### Variables:
- `timeValue`: Represents the initial time value for the timer.
- `que_count`: Represents the current question count.
- `que_numb`: Represents the current question number.
- `userScore`: Represents the score of the user.
- `counter`: Holds the setInterval ID for the timer.
- `counterLine`: Holds the setInterval ID for the timer line animation.
- `widthValue`: Represents the initial width value for the timer line.

#### Restart Quiz Event Listener:
- `restart_quiz.addEventListener("click", (e) => {...})`: Adds an event listener to the "restart_quiz" button inside the result box. When clicked, it resets the quiz by showing the quiz box, hiding the result box, resetting the timer and question variables, displaying the first question, and starting the timer again.
```
quit_quiz.addEventListener("click", (e) => {
  window.location.reload(); //reload the current window
});

// if Next Question button is clicked
next_btn.addEventListener("click", (e) => {
  //check if it does not exceed max questions
  if (que_count < questions.length - 1) {
    que_count++; //increment the que_count value
    que_numb++; //increment the que_numb value
    showQuetions(que_count); //calling showQestions function
    queCounter(que_numb); //passing que_numb value to queCounter
    clearInterval(counter); //clear counter
    clearInterval(counterLine); //clear counterLine
    startTimer(timeValue); //calling startTimer function
    startTimerLine(widthValue); //calling startTimerLine function
    timeText.textContent = "Time Left"; //change the timeText to Time Left
    next_btn.classList.remove("show"); //hide the next button
  } else {
    clearInterval(counter); //clear counter
    clearInterval(counterLine); //clear counterLine
    showResult(); //calling showResult function
  }
});

// getting questions and options from array
// If you have lesser or more number of options you need to change this code
function showQuetions(index) {
  const que_text = document.querySelector(".que_text");

  //creating a new span and div tag for question and option and passing the value using array index
  // self exercise: re-write the following using backtick syntax for string in JS instead of concatenation operator
  let que_tag =
    "<span>" +
    questions[index].numb +
    ". " +
    questions[index].question +
    "</span>";
  let option_tag =
    '<div class="option"><span>' +
    questions[index].options[0] +
    "</span></div>" +
    '<div class="option"><span>' +
    questions[index].options[1] +
    "</span></div>" +
    '<div class="option"><span>' +
    questions[index].options[2] +
    "</span></div>" +
    '<div class="option"><span>' +
    questions[index].options[3] +
    "</span></div>";
  que_text.innerHTML = que_tag; //adding new (child) span tag inside que_tag
  option_list.innerHTML = option_tag; //adding new (child) div tag inside option_tag

  const option = option_list.querySelectorAll(".option");

  // set onclick attribute to all available options
  for (i = 0; i < option.length; i++) {
    option[i].setAttribute("onclick", "optionSelected(this)");
  }
}
// create new div tags for right or wrong tick icons
let tickIconTag = '<div class="icon tick"><i class="fas fa-check"></i></div>';
let crossIconTag = '<div class="icon cross"><i class="fas fa-times"></i></div>';

//if user clicked on option
function optionSelected(answer) {
  clearInterval(counter); //clear counter
  clearInterval(counterLine); //clear counterLine
  let userAns = answer.textContent; //getting user selected option
  let correcAns = questions[que_count].answer; //getting correct answer from array
  const allOptions = option_list.children.length; //getting all option items

  //if user selected option is equal to array's correct answer
  if (userAns == correcAns) {
    userScore += 1; //update total score value increment by 1
    answer.classList.add("correct"); //add green color to correct selected option
    answer.insertAdjacentHTML("beforeend", tickIconTag); //add tick icon to correct selected option
    console.log("Correct Answer");
    console.log("Your correct answers = " + userScore);
  } else {
    answer.classList.add("incorrect"); //add red color to correct selected option
    answer.insertAdjacentHTML("beforeend", crossIconTag); //add cross icon to correct selected option
    console.log("Wrong Answer");

    for (i = 0; i < allOptions; i++) {
      if (option_list.children[i].textContent == correcAns) {
        //if there is an option which is matched to an array answer
        option_list.children[i].setAttribute("class", "option correct"); //add green color to matched option
        option_list.children[i].insertAdjacentHTML("beforeend", tickIconTag); //add tick icon to matched option
        console.log("Auto selected correct answer.");
      }
    }
  }
  for (i = 0; i < allOptions; i++) {
    option_list.children[i].classList.add("disabled"); //once user select an option, disable all options
  }
  next_btn.classList.add("show"); //show the next button if user selected any option
}

// display for result box based on user performance
function showResult() {
  info_box.classList.remove("activeInfo"); //hide info box
  quiz_box.classList.remove("activeQuiz"); //hide quiz box
  result_box.classList.add("activeResult"); //show result box
  const scoreText = result_box.querySelector(".score_text");
  if (userScore > 3) {
    // if user scored more than 3
    //create a new span tag and pass the user score number and total question number
    let scoreTag =
      "<span>and congrats! , You got <p>" +
      userScore +
      "</p> out of <p>" +
      questions.length +
      "</p></span>";
    scoreText.innerHTML = scoreTag; //add new span tag inside score_Text
  } else if (userScore > 1) {
    // if user scored more than 1
    let scoreTag =
      "<span>and nice , You got <p>" +
      userScore +
      "</p> out of <p>" +
      questions.length +
      "</p></span>";
    scoreText.innerHTML = scoreTag;
  } else {
    // if user scored less than 1
    let scoreTag =
      "<span>and sorry , You got only <p>" +
      userScore +
      "</p> out of <p>" +
      questions.length +
      "</p></span>";
    scoreText.innerHTML = scoreTag;
  }
}

// control the timer and actions associated to it
function startTimer(time) {
  counter = setInterval(timer, 1000);
  function timer() {
    timeCount.textContent = time; //change the value of timeCount with time value
    time--; //decrement the time value
    if (time < 9) {
      //if timer is less than 9
      let addZero = timeCount.textContent;
      timeCount.textContent = "0" + addZero; //add a 0 before time value
    }
    if (time < 0) {
      //if timer is less than 0
      clearInterval(counter); //clear counter
      timeText.textContent = "Time Off"; //change the time text to time off
      const allOptions = option_list.children.length; //get all option items
      let correcAns = questions[que_count].answer; //get correct answer from array
      for (i = 0; i < allOptions; i++) {
        if (option_list.children[i].textContent == correcAns) {
          //if there is an option which is matched to an array answer
          option_list.children[i].setAttribute("class", "option correct"); //add green color to matched option
          option_list.children[i].insertAdjacentHTML("beforeend", tickIconTag); //add tick icon to matched option
          console.log("Time Off: Auto selected correct answer.");
        }
      }
      for (i = 0; i < allOptions; i++) {
        option_list.children[i].classList.add("disabled"); //once user select an option then disabled all options
      }
      next_btn.classList.add("show"); //show the next button if user selected any option
    }
  }
}
```
## Event Listeners:

- `quit_quiz.addEventListener("click", (e) => {...})`: Reloads the current window when the "quit_quiz" button is clicked, effectively restarting the quiz.

- `next_btn.addEventListener("click", (e) => {...})`: Checks if the current question count does not exceed the maximum number of questions when the "next_btn" button is clicked. If it doesn't, it increments the question count, displays the next question, updates the question number, restarts the timer, and adjusts the UI accordingly. If the maximum number of questions is reached, it calls the `showResult()` function to display the result.

## Functions:

- `showQuetions(index)`: Retrieves questions and options from the `questions` array and displays them on the UI. It dynamically generates HTML elements for questions and options based on the provided index.

- `optionSelected(answer)`: Handles the user's selection of an option. It compares the selected option with the correct answer, updates the user's score, styles the selected option, and shows the correct answer if the user's choice is incorrect.

- `showResult()`: Displays the result box based on the user's performance. It calculates the user's score and displays a message accordingly.

- `startTimer(time)`: Controls the timer for each question. It starts a countdown timer and updates the timer display every second. When the time runs out, it automatically selects the correct answer and disables further interaction with options.
```
function queCounter(index) {
  //creating a new span tag and passing the question number and total question
  let totalQueCounTag =
    "<span><p>" +
    index +
    "</p> of <p>" +
    questions.length +
    "</p> Questions</span>";
  bottom_ques_counter.innerHTML = totalQueCounTag; //adding new span tag inside bottom_ques_counter
}
```
## Functions:

- `queCounter(index)`: Creates and updates the question counter displayed at the bottom of the quiz. It dynamically generates HTML content showing the current question number and the total number of questions in the quiz. The function then updates the HTML content inside the `bottom_ques_counter` element to reflect the current question count.

## Purpose

The JavaScript code provided implements the functionality of a quiz application. Its main objectives include:

1. **Quiz Initialization**: Setting up event listeners for buttons and elements to control the quiz flow.

2. **Displaying Questions**: Functions to display questions and options retrieved from an array of objects containing quiz questions.

3. **Handling User Interaction**: Managing user interaction by allowing them to select options and advancing to the next question.

4. **Scoring**: Tracking the user's score based on their selected answers and displaying the result at the end of the quiz.

5. **Timer Functionality**: Incorporating a timer feature to limit the time for each question and provide a time-based challenge.

6. **UI Updates**: Dynamically updating UI elements to reflect the current state of the quiz, such as showing question numbers, hiding/showing quiz components, and displaying results.


# Quiz Application Page Summary

## Summary

This repository contains the code for a quiz application implemented using HTML, CSS, and JavaScript. The application provides users with a quiz experience where they can answer multiple-choice questions and receive feedback on their performance.

### HTML
The HTML file (`index.html`) defines the structure of the quiz application. It includes elements for displaying questions, options, timer, and result. It also links external CSS and JavaScript files.

### CSS
The CSS file (`style.css`) contains styles to enhance the visual appearance and layout of the quiz application. It provides styling for buttons, question containers, timer, and result display.

### JavaScript
The JavaScript file (`quizApp.js`) implements the functionality of the quiz application. It handles user interaction, such as selecting options, advancing to the next question, and tracking the user's score. Additionally, it incorporates timer functionality to limit the time for each question and provides dynamic updates to the UI.






