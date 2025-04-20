
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Team Portfolio</title>
<style>
    body {
      font-family: Arial, sans-serif;
      background: #f9f9f9;
      margin: 0;
      padding: 0;
      text-align: center;
    }

    header {
      background: #333;
      color: #fff;
      padding: 1rem 0;
    }
    #darkModeBtn{
    padding: 0.5rem 1rem;
    color:white;
    border:none;
    border-radius: 4px;
    cursor: pointer;
    }
    #darkModeBtn:hover{
    background: #666;
    }
    .portfolio {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 1.5rem;
      padding: 2rem;
    }

    .card {
      background: white;
      border-radius: 8px;
      box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
      padding: 1rem;
      width: 200px;
    }

    .card img {
      width: 100%;
      border-radius: 50%;
    }

    .card button {
      margin-top: 0.5rem;
      padding: 0.5rem 1rem;
      background: #007bff;
      color: white;
      border: none;
      border-radius: 4px;
      cursor: pointer;
    }

    .card button:hover {
      background: #0056b3;
    }

    .hidden {
      display: none;
    }
</style>
</head>
<body>
<header>
<h1>5 Star</h1>
    <button onclick="toggleDarkMode()" id="darkModeBtn">Toggle Dark Mode</button>
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
<p>??</p>
<button onclick="showMore('person2')">More Info</button>
<p id="person2" class="hidden">??</p>
</div>
<div class="card">
<img src="https://via.placeholder.com/150" alt="Person 3" />
<h2>Surya Bahadur KC</h2>
<p>??</p>
<button onclick="showMore('person3')">More Info</button>
<p id="person3" class="hidden">??</p>
</div>
<div class="card">
<img src="https://via.placeholder.com/150" alt="Person 4" />
<h2>Swopnil Khadka</h2>
<p>??</p>
<button onclick="showMore('person4')">More Info</button>
<p id="person4" class="hidden">??</p>
</div>
<div class="card">
<img src="https://via.placeholder.com/150" alt="Person 5" />
<h2>Swopnil Shreesh</h2>
<p>??</p>
<button onclick="showMore('person5')">More Info</button>
<p id="person5" class="hidden">??</p>
</div>
</section>
</main>
<script>
    function showMore(id) {
      const element = document.getElementById(id);
      element.classList.toggle("hidden");
    }
</script>
</body>
</html>
