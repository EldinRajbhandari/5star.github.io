<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Starry Night Typing Test</title>
<style>
  /* Body & Background */
  body {
    font-family: 'Courier New', monospace;
    margin: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background: radial-gradient(circle at 25% 25%, #fefecd 0%, #ffe5a0 15%, #11193c 80%, #0b0d1f 100%);
    overflow: hidden;
    color: #fff;
    position: relative;
  }

  /* Swirling Stars */
  .star {
    position: absolute;
    border-radius: 50%;
    background: white;
    opacity: 0.8;
    box-shadow: 0 0 10px 2px white;
    animation: swirl linear infinite;
  }

  @keyframes swirl {
    0% { transform: rotate(0deg) translate(0,0); opacity: 0.8; }
    50% { transform: rotate(360deg) translate(10px,10px); opacity: 1; }
    100% { transform: rotate(720deg) translate(0,0); opacity: 0.8; }
  }

  /* Container */
  .container {
    position: relative;
    z-index: 1;
    width: 90%;
    max-width: 600px;
    background: rgba(10, 15, 50, 0.6);
    border-radius: 15px;
    padding: 20px;
    box-shadow: 0 0 25px rgba(255,255,150,0.3);
  }

  /* Text Display */
  #text-display {
    font-size: 18px;
    line-height: 1.6;
    margin-bottom: 15px;
    user-select: none;
    white-space: pre-wrap;
  }
  .correct { color: #22c55e; }
  .incorrect { color: #ef4444; text-decoration: underline; }

  /* Input */
  textarea {
    width: 100%;
    padding: 10px;
    font-size: 16px;
    border: none;
    outline: none;
    border-radius: 6px;
    background: rgba(0,0,50,0.6);
    color: #fff;
    resize: none;
    overflow-y: auto;
    height: 3.2em;
    box-shadow: inset 0 0 5px rgba(255,255,200,0.5);
  }

  /* Info & Controls */
  .info {
    display: flex;
    justify-content: space-between;
    font-size: 14px;
    margin-top: 10px;
    color: #fefecd;
  }
  .controls {
    display: flex;
    justify-content: space-between;
    margin-top: 10px;
    gap: 10px;
  }
  select, button {
    padding: 8px;
    border: none;
    border-radius: 5px;
    background: rgba(255,255,200,0.8);
    color: #111;
    font-weight: bold;
    cursor: pointer;
    transition: 0.3s;
  }
  select:hover, button:hover {
    background: rgba(255,255,200,1);
  }
</style>
</head>
<body>

<div class="container">
  <div id="text-display"></div>

  <textarea id="input" placeholder="Start typing..." disabled rows="3"></textarea>

  <div class="info">
    <span>⏱ <span id="time">60</span>s</span>
    <span>⚡ <span id="wpm">0</span> WPM</span>
    <span>🎯 <span id="accuracy">100</span>%</span>
  </div>

  <div class="controls">
    <select id="difficulty">
      <option value="easy">Easy</option>
      <option value="medium" selected>Medium</option>
      <option value="hard">Hard</option>
    </select>
    <button onclick="startTest()">Start</button>
  </div>
</div>

<script>
  /* Typing Words */
  const wordSets = {
    easy: ["cat","dog","sun","book","pen","tree","fish","milk","home","car","red","blue","run","jump","ball"],
    medium: ["typing","keyboard","screen","random","simple","design","focus","practice","coding","input","output","system"],
    hard: ["performance","javascript","development","complexity","synchronization","architecture","optimization","implementation","functionality","asynchronous"]
  };

  let timer = 60, interval = null, currentText = "", totalTyped = 0;

  const textDisplay = document.getElementById("text-display");
  const input = document.getElementById("input");
  const timeDisplay = document.getElementById("time");
  const wpmDisplay = document.getElementById("wpm");
  const accuracyDisplay = document.getElementById("accuracy");
  const difficultySelect = document.getElementById("difficulty");

  function generateWords(n = 25) {
    const mode = difficultySelect.value;
    const words = wordSets[mode];
    return Array.from({length: n}, () =>
      words[Math.floor(Math.random() * words.length)]
    ).join(" ");
  }

  function loadWords() {
    currentText = generateWords();
    textDisplay.innerHTML = "";
    currentText.split("").forEach(c => {
      const span = document.createElement("span");
      span.innerText = c;
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

    clearInterval(interval);
    interval = setInterval(() => {
      timer--;
      timeDisplay.innerText = timer;
      if (timer === 0) {
        clearInterval(interval);
        input.disabled = true;
      }
    }, 1000);
  }

  input.addEventListener("keydown", e => {
    if (e.key === "Backspace") e.preventDefault();
  });

  document.addEventListener("copy", e => e.preventDefault());
  document.addEventListener("contextmenu", e => e.preventDefault());

  input.addEventListener("input", () => {
    const entered = input.value.split("");
    const spans = textDisplay.querySelectorAll("span");

    let correct = 0;
    spans.forEach((span, i) => {
      const char = entered[i];
      if (char == null) {
        span.className = "";
      } else if (char === span.innerText) {
        span.className = "correct"; // green
        correct++;
      } else {
        span.className = "incorrect"; // red
      }
    });

    accuracyDisplay.innerText = ((correct / entered.length) * 100 || 0).toFixed(0);

    totalTyped++;
    const wpm = Math.round((totalTyped / 5) / ((60 - timer) / 60) || 0);
    wpmDisplay.innerText = wpm;

    if (entered.length === currentText.length) {
      input.value = "";
      loadWords();
    }
  });

  /* Create swirling stars dynamically */
  function createStars(count = 50) {
    for (let i = 0; i < count; i++) {
      const star = document.createElement("div");
      star.classList.add("star");
      star.style.width = `${Math.random()*3 + 1}px`;
      star.style.height = `${Math.random()*3 + 1}px`;
      star.style.left = `${Math.random()*100}%`;
      star.style.top = `${Math.random()*100}%`;
      star.style.animationDuration = `${Math.random()*10 + 5}s`;
      document.body.appendChild(star);
    }
  }

  createStars(70); // number of stars
</script>

</body>
</html>
