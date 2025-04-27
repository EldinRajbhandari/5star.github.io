<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Team Portfolio</title>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" />
<script src="https://cdn.jsdelivr.net/npm/typed.js@2.0.12"></script>
<script src="https://cdn.jsdelivr.net/npm/particles.js@2.0.0/particles.min.js"></script>
<style>
    body {
      font-family: Arial, sans-serif;
      background-color: #121212;
      color: #f1f1f1;
      margin: 0;
      padding: 0;
      text-align: center;
      overflow-x: hidden;
    }

    #particles-js {
      position: fixed;
      top: 0; left: 0;
      width: 100%;
      height: 100%;
      z-index: -1;
    }

    header {
      background: #1c1c1c;
      color: #fff;
      padding: 1rem 2rem;
    }

    .portfolio {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 1.5rem;
      padding: 2rem;
    }

    .card {
      background: #1e1e1e;
      color: #f1f1f1;
      border-radius: 8px;
      box-shadow: 0 2px 10px rgba(0, 0, 0, 0.5);
      padding: 1rem;
      width: 220px;
      transition: transform 0.3s ease, box-shadow 0.3s ease;
    }

    .card:hover {
      transform: translateY(-10px);
      box-shadow: 0 8px 30px rgba(0, 255, 204, 0.2);
    }

    .card img {
      width: 100%;
      border-radius: 50%;
    }

    .card button {
      margin-top: 0.5rem;
      padding: 0.5rem 1rem;
      background: #00b894;
      color: white;
      border: none;
      border-radius: 4px;
      cursor: pointer;
    }

    .card button:hover {
      background: #019875;
    }

    .social-icons a {
      margin: 0 5px;
      color: #f1f1f1;
      text-decoration: none;
      font-size: 1.2rem;
    }

    .social-icons a:hover {
      color: #00ffcc;
    }

    .hidden {
      display: none;
    }

    .contact {
      padding: 2rem;
      background: #1a1a1a;
    }

    .contact form {
      max-width: 400px;
      margin: 0 auto;
      display: flex;
      flex-direction: column;
      gap: 1rem;
    }

    .contact input, .contact textarea {
      padding: 0.8rem;
      border-radius: 5px;
      border: 1px solid #444;
      background: #2a2a2a;
      color: #f1f1f1;
    }

    .contact button {
      padding: 0.8rem;
      background: #00b894;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }

    .contact button:hover {
      background: #019875;
    }

    footer {
      background: #111;
      color: #aaa;
      padding: 1rem;
    }

    

    @media (max-width: 768px) {
      .portfolio {
        flex-direction: column;
        align-items: center;
      }
      .card {
        width: 90%;
      }
      header {
        flex-direction: column;
        text-align: center;
      }
      .contact form {
        width: 90%;
      }
    }
</style>
</head>
<body>
<div id="particles-js"></div>

<header>
<h1><span id="typed"></span></h1>
</header>

<main>
<section class="portfolio">
    <div class="card">
        <h2>Eldin Rajbhandari</h2>
         <p></p>
         <div class="social-icons">
           <a href="https://www.instagram.com/eldin_rajbhandari?igsh=MTl3ODl0bGR2Z2czdg==" target="_blank"><i class="fab fa-instagram"></i></a>
         </div>
         <button onclick="showMore('person1')">More Info</button>
         <p id="person1" class="hidden">Specializes in HTML,CSS and technical field🧑🏻‍💻</p>
       </div>
       <div class="card">  
         <h2>Bijaya Gharti Magar</h2>
         <p></p>
         <div class="social-icons">
           <a href="https://www.instagram.com/bijaygharti_?igsh=dWV1N3R5dWNzOGlw" target="_blank"><i class="fab fa-instagram"></i></a>
         </div>
         <button onclick="showMore('person2')">More Info</button>
         <p id="person2" class="hidden">A Very Awesome Futsal player having more than 4+ years of experience!⚽</p>
       </div>
       <div class="card">
         <h2>Surya Bahadur KC  (Ukesh)</h2>
         <p></p>
         <div class="social-icons">
           <a href="https://www.instagram.com/ukesh__cheetri?igsh=ZTNqYzZ3Zzd0OTk1" target="_blank"><i class="fab fa-instagram"></i></a>
         </div>
         <button onclick="showMore('person3')">More Info</button>
         <p id="person3" class="hidden">Expert in Mobile/PC GAMING. He plays video games really NICE!🎮</p>
       </div>
       <div class="card">
         <h2>Swopnil Khadka</h2>
         <p></p>
         <div class="social-icons">
           <a href="https://www.instagram.com/swopnil__09?igsh=MXdvdzF3NWxrcjBlNA==" target="_blank"><i class="fab fa-instagram"></i></a>
         </div>
         <button onclick="showMore('person4')">More Info</button>
         <p id="person4" class="hidden">Active in Studies and is Expert in Mathematics!😂</p>
       </div>
       <div class="card">
         <h2>Swopnil Shreesh</h2>
         <p></p>
         <div class="social-icons">
           <a href="https://www.instagram.com/swopnil_shreesh?igsh=MWI3bzF5eTJrb3RjeA==" target="_blank"><i class="fab fa-instagram"></i></a>
         </div>
         <button onclick="showMore('person5')">More Info</button>
         <p id="person5" class="hidden">Playing Guitar since the age of 10.His Guitar play sounds really Mindblowing🎸</p>
       </div>
<!-- Add more team member cards here -->
</section>

<section class="contact">
<h2>Contact Us</h2>
<form action="https://formspree.io/f/mldbrnwb" method="POST">
<input type="text" name="name" placeholder="Your Name" required />
<input type="email" name="email" placeholder="Your Email" required />
<textarea name="message" rows="4" placeholder="Your Message" required></textarea>
<button type="submit">Send Message</button>
</form>
</section>
</main>

<footer>
<p>&copy; 2025 5 Star Team. All rights reserved.</p>
</footer>



<script>
    particlesJS("particles-js", {
      particles: {
        number: { value: 60, density: { enable: true, value_area: 800 } },
        color: { value: "#00ffcc" },
        shape: { type: "circle" },
        opacity: { value: 0.5 },
        size: { value: 3 },
        line_linked: { enable: true, distance: 150, color: "#00ffcc", opacity: 0.4, width: 1 },
        move: { enable: true, speed: 3 }
      },
      interactivity: {
        events: {
          onhover: { enable: true, mode: "repulse" },
          onclick: { enable: true, mode: "push" }
        }
      }
    });

    var typed = new Typed("#typed", {
      strings: ["5 Star Team"],
      typeSpeed: 100,
      backSpeed: 50,
      loop: true
    });

    function showMore(id) {
      document.getElementById(id).classList.toggle("hidden");
    }

    function scrollToTop() {
      window.scrollTo({ top: 0, behavior: 'smooth' });
    }
</script>
</body>
</html>
