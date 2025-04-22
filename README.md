
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Team Portfolio - Dark Mode</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" />
  <script src="https://cdn.jsdelivr.net/npm/typed.js@2.0.12"></script>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #121212;
      color: #f1f1f1;
      margin: 0;
      padding: 0;
      text-align: center;
    }

    #loader {
      position: fixed;
      width: 100vw;
      height: 100vh;
      background: #111;
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 1000;
    }

    .spinner {
      border: 6px solid #333;
      border-top: 6px solid #00ffcc;
      border-radius: 50%;
      width: 50px;
      height: 50px;
      animation: spin 1s linear infinite;
    }

    @keyframes spin {
      0% { transform: rotate(0deg); }
      100% { transform: rotate(360deg); }
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
      animation: fadeInUp 0.8s ease forwards;
      opacity: 0;
    }

    .card:hover {
      transform: translateY(-10px);
      box-shadow: 0 8px 30px rgba(0, 255, 204, 0.2);
    }

    @keyframes fadeInUp {
      from {
        opacity: 0;
        transform: translateY(30px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
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
  <div id="loader"><div class="spinner"></div></div>

  <header>
    <h1><span id="typed"></span></h1>
  </header>

  <main style="display:none;" id="mainContent">
    <section class="portfolio">
      <!-- Repeat this block for each team member -->
      <div class="card">
       <h2>Eldin Rajbhandari</h2>
        <p>Frontend Developer and Backend Developer</p>
        <div class="social-icons">
          <a href="https://www.instagram.com/eldin_rajbhandari?igsh=MTl3ODl0bGR2Z2czdg==" target="_blank"><i class="fab fa-instagram"></i></a>
        </div>
        <button onclick="showMore('person1')">More Info</button>
        <p id="person1" class="hidden">Specializes in HTML, CSS, and React.</p>
      </div>
      <div class="card">  
        <h2>Bijay Magar</h2>
        <p></p>
        <div class="social-icons">
          <a href="https://www.instagram.com/bijaygharti_?igsh=dWV1N3R5dWNzOGlw" target="_blank"><i class="fab fa-instagram"></i></a>
        </div>
        <button onclick="showMore('person2')">More Info</button>
        <p id="person2" class="hidden">Expert in Node.js and MongoDB.</p>
      </div>
      <div class="card">
        <h2>Surya Bahadur KC(Ukesh)</h2>
        <p></p>
        <div class="social-icons">
          <a href="https://www.instagram.com/ukesh__cheetri?igsh=ZTNqYzZ3Zzd0OTk1" target="_blank"><i class="fab fa-instagram"></i></a>
        </div>
        <button onclick="showMore('person3')">More Info</button>
        <p id="person3" class="hidden">Focuses on user-centered design and prototyping.</p>
      </div>
      <div class="card">
        <h2>Swopnil Khadka</h2>
        <p></p>
        <div class="social-icons">
          <a href="https://www.instagram.com/swopnil__09?igsh=MXdvdzF3NWxrcjBlNA==" target="_blank"><i class="fab fa-instagram"></i></a>
        </div>
        <button onclick="showMore('person4')">More Info</button>
        <p id="person4" class="hidden">Manages team workflow and client communication.</p>
      </div>
      <div class="card">
        <h2>Swopnil Shreesh</h2>
        <p></p>
        <div class="social-icons">
          <a href="https://www.instagram.com/swopnil_shreesh?igsh=MWI3bzF5eTJrb3RjeA==" target="_blank"><i class="fab fa-instagram"></i></a>
        </div>
        <button onclick="showMore('person5')">More Info</button>
        <p id="person5" class="hidden">Ensures software quality and performance.</p>
      </div>
      <!-- Add more team members as needed -->
    </section>

    <section class="contact">
      <h2>Contact Us</h2>
      <form action="https://formspree.io/f/your-form-id" method="POST">
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
    var typed = new Typed("#typed", {
      strings: ["5 Star Team"],
      typeSpeed: 100,
      backSpeed: 50,
      loop: true
    });

    window.addEventListener("load", function () {
      document.getElementById("loader").style.display = "none";
      document.getElementById("mainContent").style.display = "block";
    });

    function showMore(id) {
      const element = document.getElementById(id);
      element.classList.toggle("hidden");
    }
  </script>
</body>


