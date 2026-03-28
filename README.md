<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  
  <!-- ✅ Important for mobile -->
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>Typing Speed Test</title>

  <style>
    body {
      font-family: Arial, sans-serif;
      background: #0f172a;
      color: #fff;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }

    .container {
      width: 95%;
      max-width: 700px;
      text-align: center;
      background: #1e293b;
      padding: 15px;
      border-radius: 10px;
      box-sizing: border-box;
    }

    h1 {
      font-size: 22px;
      margin-bottom: 10px;
    }

    #text-display {
      margin: 15px 0;
      font-size: 18px;
      line-height: 1.6;
      word-wrap: break-word;
      user-select: none;
    }

    .correct {
      color: #22c55e;
    }

    .incorrect {
      color: #ef4444;
      text-decoration: underline;
    }

    textarea {
      width: 100%;
      height: 90px;
      padding: 10px;
      font-size: 16px; /* prevents zoom on iOS */
      border-radius: 5px;
      border: none;
      outline: none;
      box-sizing: border-box;
    }

    .stats {
      margin-top: 10px;
      display: flex;
      justify-content: space-between;
      font-size: 14px;
    }

    button {
      margin-top: 10px;
      padding: 10px;
      width: 48%;
      border: none;
      background: #3b82f6;
      color: white;
      border-radius: 5px;
      cursor: pointer;
      font-size: 14px;
    }

    .btn-group {
      display: flex;
      justify-content: space-between;
      gap: 10px;
    }

    /* 📱 Extra small screens */
    @media (max-width: 400px) {
      h1 {
        font-size: 18px;
      }

      #text-display {
        font-size: 16px;
      }

      textarea {
        height: 80px;
      }
    }
  </style>
</head>
<body>

<div class="container">
  <h1>Typing Speed Test</h1>
  <p>Time Left: <span id="time">60</span>s</p>

  <div id="text-display"></div>

  <textarea id="input" placeholder="Start typing..." disabled></textarea>

  <div class="stats">
    <p>WPM: <span id="wpm">0</span></p>
    <p>Accuracy: <span id="accuracy">100</span>%</p>
  </div>

  <div class="btn-group">
    <button onclick="startTest()">Start</button>
    <button onclick="resetTest()">Restart</button>
  </div>
</div>

<script>
  const words = [
    "speed","keyboard","javascript","practice","focus","typing",
    "accuracy","challenge","developer","screen","random","words",
    "performance","coding","function","variable","design","input",
    "output","monitor","skill","progress","system","dynamic"
  ];

  let timer = 60;
  let interval = null;
  let currentText = "";
  let totalTyped = 0;

  const textDisplay = document.getElementById("text-display");
  const input = document.getElementById("input");
  const timeDisplay = document.getElementById("time");
  const wpmDisplay = document.getElementById("wpm");
  const accuracyDisplay = document.getElementById("accuracy");

  function generateWords(count = 30) {
    let result = [];
    for (let i = 0; i < count; i++) {
      result.push(words[Math.floor(Math.random() * words.length)]);
    }
    return result.join(" ");
  }

  function loadWords() {
    currentText = generateWords();
    textDisplay.innerHTML = "";

    currentText.split("").forEach(char => {
      const span = document.createElement("span");
      span.innerText = char;
      textDisplay.appendChild(span);
    });
  }

  function startTest() {
    input.disabled = false;
    input.value = "";
    input.focus();

    totalTyped = 0;
    loadWords();

    timer = 60;
    timeDisplay.innerText = timer;

    if (interval) clearInterval(interval);

    interval = setInterval(() => {
      timer--;
      timeDisplay.innerText = timer;

      if (timer === 0) {
        clearInterval(interval);
        input.disabled = true;
      }
    }, 1000);
  }

  // ❌ Disable Backspace
  input.addEventListener("keydown", (e) => {
    if (e.key === "Backspace") {
      e.preventDefault();
    }
  });

  // ❌ Disable shortcuts
  document.addEventListener("keydown", (e) => {
    if (e.ctrlKey && (
      e.key === "c" ||
      e.key === "x" ||
      e.key === "a" ||
      e.key === "u"
    )) {
      e.preventDefault();
    }
  });

  document.addEventListener("copy", (e) => e.preventDefault());
  document.addEventListener("contextmenu", (e) => e.preventDefault());

  input.addEventListener("input", () => {
    const enteredText = input.value.split("");
    const spans = textDisplay.querySelectorAll("span");

    let correct = 0;

    spans.forEach((span, index) => {
      const char = enteredText[index];

      if (char == null) {
        span.classList.remove("correct", "incorrect");
      } else if (char === span.innerText) {
        span.classList.add("correct");
        span.classList.remove("incorrect");
        correct++;
      } else {
        span.classList.add("incorrect");
        span.classList.remove("correct");
      }
    });

    const accuracy = ((correct / enteredText.length) * 100 || 0).toFixed(2);
    accuracyDisplay.innerText = accuracy;

    totalTyped++;
    const wordsTyped = totalTyped / 5;
    const timePassed = 60 - timer;
    const wpm = Math.round(wordsTyped / (timePassed / 60) || 0);
    wpmDisplay.innerText = wpm;

    if (enteredText.length === currentText.length) {
      input.value = "";
      loadWords();
    }
  });

  function resetTest() {
    clearInterval(interval);
    timer = 60;
    timeDisplay.innerText = timer;
    input.value = "";
    input.disabled = true;
    textDisplay.innerHTML = "";
    wpmDisplay.innerText = 0;
    accuracyDisplay.innerText = 100;
  }
</script>

</body>
</html>
