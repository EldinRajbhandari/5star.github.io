<!DOCTYPE html><html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Team Portfolio</title>
<style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }
    body {
      font-family: Arial, sans-serif;
      background: #f0f2f5;
      padding: 2rem;
    }
    h1 {
      text-align: center;
      margin-bottom: 2rem;
    }
    .team {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 2rem;
    }
    .card {
      background: #fff;
      border-radius: 12px;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
      padding: 1.5rem;
      text-align: center;
      transition: transform 0.3s;
    }
    .card:hover {
      transform: translateY(-5px);
    }
    .avatar {
      width: 100px;
      height: 100px;
      border-radius: 50%;
      margin-bottom: 1rem;
    }
    .name {
      font-size: 1.2rem;
      font-weight: bold;
      margin-bottom: 0.5rem;
    }
    .role {
      font-size: 1rem;
      color: #777;
      margin-bottom: 1rem;
    }
    .bio {
      font-size: 0.9rem;
      color: #555;
    }
</style>
</head>
<body>
<h1>Our Team</h1>
<div class="team" id="team-container">
<!-- Cards will be inserted here -->
</div><script>
    const teamMembers = [
      {
        name: "Alice Johnson",
        role: "Frontend Developer",
        bio: "Specializes in responsive design and UI/UX.",
        avatar: "https://i.pravatar.cc/100?img=1"
      },
      {
        name: "Bob Smith",
        role: "Backend Developer",
        bio: "Expert in databases and server-side logic.",
        avatar: "https://i.pravatar.cc/100?img=2"
      },
      {
        name: "Carla Gomez",
        role: "Project Manager",
        bio: "Keeps projects on track and under budget.",
        avatar: "https://i.pravatar.cc/100?img=3"
      },
      {
        name: "David Lee",
        role: "UI Designer",
        bio: "Designs sleek, user-friendly interfaces.",
        avatar: "https://i.pravatar.cc/100?img=4"
      },
      {
        name: "Eva Chen",
        role: "QA Engineer",
        bio: "Ensures top quality with thorough testing.",
        avatar: "https://i.pravatar.cc/100?img=5"
      }
    ];

    const container = document.getElementById("team-container");

    teamMembers.forEach(member => {
      const card = document.createElement("div");
      card.className = "card";
      card.innerHTML = `
<img class="avatar" src="${member.avatar}" alt="${member.name}" />
<div class="name">${member.name}</div>
<div class="role">${member.role}</div>
<div class="bio">${member.bio}</div>
      `;
      container.appendChild(card);
    });
</script></body>
</html>
