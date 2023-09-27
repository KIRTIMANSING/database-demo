<!DOCTYPE html>
<html>
<head>
  <title>JavaScript Quiz App</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;700&display=swap');

body {
  font-family: 'Poppins', sans-serif;
  background: #b9b3a9;
  display: flex;
  justify-content: center;
}

.container {
  width: 450px;
  padding: 20px;
  margin-top: 80px;
  background-color: #fff;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  border-radius: 20px;
}

h1 {
  text-align: center;
}

.question {
  font-weight: bold;
  margin-bottom: 10px;
}

.options {
  margin-bottom: 20px;
}

.option {
  display: block;
  margin-bottom: 10px;
}

.button {
  display: inline-block;
  padding: 10px 20px;
  background-color: #428bca;
  color: #fff;
  border: none;
  cursor: pointer;
  font-size: 16px;
  border-radius: 4px;
  transition: background-color 0.3s;
  margin-right: 10px;
}

.button:hover {
  background-color: #3071a9;
}

.result {
  text-align: center;
  margin-top: 20px;
  font-weight: bold;
}

.hide{
  display: none;
}
  </style>
</head>
<body>
  <div class="container">
    <h1>Quiz App</h1>
    <div id="quiz"></div>
    <div id="result" class="result"></div>
    <button id="submit" class="button">Submit</button>
    <button id="retry" class="button hide">Retry</button>
    <button id="showAnswer" class="button hide">Show Answer</button>
  </div>
  <script >let input = document.getElementById('inputBox');
let buttons = document.querySelectorAll('button');

let string = "";
let arr = Array.from(buttons);
arr.forEach(button => {
    button.addEventListener('click', (e) =>{
        if(e.target.innerHTML == '='){
            string = eval(string);
            input.value = string;
        }

        else if(e.target.innerHTML == 'AC'){
            string = "";
            input.value = string;
        }
        else if(e.target.innerHTML == 'DEL'){
            string = string.substring(0, string.length-1);
            input.value = string;
        }
        else{
            string += e.target.innerHTML;
            input.value = string;
        }

    })
})</script>
</body>
</html>
