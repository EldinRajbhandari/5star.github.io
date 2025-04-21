
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Team Portfolio</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" />
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
      display: flex;
      justify-content: center;
      align-items: center;
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
      background: white;
      border-radius: 8px;
      box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
      padding: 1rem;
      width: 220px;
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
    .social-icons a {
      margin: 0 5px;
      color: #333;
      text-decoration: none;
      font-size: 1.2rem;
    }
    .social-icons a:hover {
      color: #e1306c; /* Instagram color */
    }
    .hidden {
      display: none;
    }
    .contact {
      padding: 2rem;
      background: #f1f1f1;
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
      border: 1px solid #ccc;
    }
    .contact button {
      padding: 0.8rem;
      background: #28a745;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    .contact button:hover {
      background: #218838;
    }
    footer {
      background: #222;
      color: #ccc;
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
  <header>
    <h1>5 Star</h1>
  </header>
  <main>
    <section class="portfolio">
      <div class="card">
        <img src="https://via.placeholder.com/150" alt="Person 1" />
        <h2>Eldin Rajbhandari</h2>
        <p>Frontend Developer and Backend Developer</p>
        <div class="social-icons">
          <a href="#"><i class="fab fa-instagram"></i></a>
        </div>
        <button onclick="showMore('person1')">More Info</button>
        <p id="person1" class="hidden">Specializes in HTML, CSS, and React.</p>
      </div>
      <div class="card">
        <img src="https://via.placeholder.com/150" alt="Person 2" />
        <h2>Bijay Magar</h2>
        <p></p>
        <div class="social-icons">
          <a href="https://www.instagram.com/roji__khadka_chhetri?igsh=MWtscmdsMzkxcTdyeQ=="><i class="fab fa-instagram"></i></a>
        </div>
        <button onclick="showMore('person2')">More Info</button>
        <p id="person2" class="hidden">Expert in Node.js and MongoDB.</p>
      </div>
      <div class="card">
        <img src="https://via.placeholder.com/150" alt="Person 3" />
        <h2>Surya Bahadur KC</h2>
        <p></p>
        <div class="social-icons">
          <a href="https://www.instagram.com/ukesh__cheetri?igsh=d3BjYmJzcTJmbTYy"><i class="fab fa-instagram"></i></a>
        </div>
        <button onclick="showMore('person3')">More Info</button>
        <p id="person3" class="hidden">Focuses on user-centered design and prototyping.</p>
      </div>
      <div class="card">
        <img src="https://via.placeholder.com/150" alt="Person 4" />
        <h2>Swopnil Khadka</h2>
        <p></p>
        <div class="social-icons">
          <a href="https://www.instagram.com/swopnil__09?igsh=MXgxaGQ3OWEwNjFjaw=="><i class="fab fa-instagram"></i></a>
        </div>
        <button onclick="showMore('person4')">More Info</button>
        <p id="person4" class="hidden">Manages team workflow and client communication.</p>
      </div>
      <div class="card">
        <img src="https://via.placeholder.com/150" alt="Person 5" />
        <h2>Swopnil Shreesh</h2>
        <p></p>
        <div class="social-icons">
          <a href="https://www.instagram.com/swopnil_shreesh?igsh=MWpkazF2YmRqbnJ4cg=="><i class="fab fa-instagram"></i></a>
        </div>
        <button onclick="showMore('person5')">More Info</button>
        <p id="person5" class="hidden">Ensures software quality and performance.</p>
      </div>
    </section>

    <section class="contact">
      <h2>Contact Us</h2>
      <form>
        <input type="text" placeholder="Your Name" required />
        <input type="email" placeholder="Your Email" required />
        <textarea rows="4" placeholder="Your Message" required></textarea>
        <button type="submit">Send Message</button>
      </form>
    </section>
  </main>
  <footer>
    <p>&copy; 2025 5 Star Team. All rights reserved.</p>
  </footer>
  <script>
    function showMore(id) {
      const element = document.getElementById(id);
      element.classList.toggle("hidden");
    }
  </script>
</body>
</html>
