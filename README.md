<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Team Portfolio</title>
<link rel="stylesheet" href="styles.css" />
</head>
<body>
<header>
<h1>5 Star</h1>
</header>
<main>
<section class="portfolio">
<div class="card">
<img src="https://via.placeholder.com/150" alt="Person 1" />
<h2>Eldin Rajbhandari</h2>
<p>Frontend Developer and Backend Developer</p>
<button onclick="showMore('person1')">More Info</button>
<p id="person1" class="hidden">Specializes in HTML, CSS, and React.</p>
</div>
<div class="card">
<img src="https://via.placeholder.com/150" alt="Person 2" />
<h2>Bijay Magar</h2>
<p></p>
<button onclick="showMore('person2')">More Info</button>
<p id="person2" class="hidden">Expert in Node.js and MongoDB.</p>
</div>
<div class="card">
<img src="https://via.placeholder.com/150" alt="Person 3" />
<h2>Surya Bahadur KC</h2>
<p></p>
<button onclick="showMore('person3')">More Info</button>
<p id="person3" class="hidden">Focuses on user-centered design and prototyping.</p>
</div>
<div class="card">
<img src="https://via.placeholder.com/150" alt="Person 4" />
<h2>Swopnil Khadka</h2>
<p></p>
<button onclick="showMore('person4')">More Info</button>
<p id="person4" class="hidden">Manages team workflow and client communication.</p>
</div>
<div class="card">
<img src="https://via.placeholder.com/150" alt="Person 5" />
<h2>Swopnil Shreesh</h2>
<p></p>
<button onclick="showMore('person5')">More Info</button>
<p id="person5" class="hidden">Ensures software quality and performance.</p>
</div>
</section>
</main>
<script src="script.js"></script>
</body>
</html>
