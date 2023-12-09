function processQuestion() {
  const nextButton = document.getElementsByClassName("QuestionPage_buttonAgTVr")[0];
  const submitButton = document.getElementsByClassName("QuestionPage_buttonAgTVr")[0];
  const questionElement = document.getElementsByClassName("QuestionPage_question0cU21")[0];
  const inputField = document.getElementsByClassName("QuestionPage_inputJ6nfI")[0];

  if (nextButton && nextButton.innerText === "Next") {
    nextButton.click();
  }

  if (questionElement && inputField) {
    const numbers = questionElement.innerText.match(/\d+/g);
    if (numbers && numbers.length >= 2) {
      const result = parseInt(numbers[0]) * parseInt(numbers[1]);

      // Simulate typing the calculated result into the input field
      inputField.value = result;

      // Introduce a delay (adjust as needed) to ensure the input value is set before clicking submit
      setTimeout(() => {
        // Check if there's a submit button and click it after setting the value
        if (submitButton) {
          submitButton.click();
        }
      }, 10); // Adjust the delay (in milliseconds) as needed

      // Trigger the click event to proceed to the next question
      if (nextButton && nextButton.innerText === "Next") {
        nextButton.click();
      }
    }
  }
}

// Repeat the process every 1000 milliseconds (1 second)
setInterval(processQuestion, 10);
