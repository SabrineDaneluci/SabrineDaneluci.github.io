<script>
    let links = [
      { name: "Vampires", href: "/", icon: "/icons/vampiro.png" },
      { name: "Caixão", href: "/caixao", icon: "/icons/casa-assombrada.png" },
      { name: "Quiz", href: "/quiz", icon: "/icons/morcegos.png" }
    ];
  </script>
  
  <nav class="navbar">
    <ul>
      {#each links as link}
        <li>
          <a href={link.href}>
            <img src={link.icon} alt={link.name} class="icon" />
            {link.name}
          </a>
        </li>
      {/each}
    </ul>
  </nav>
  
  <style>
    .navbar {
      background-color: #222;
      padding: 1rem;
    }
    .navbar ul {
      list-style: none;
      display: flex;
      gap: 1rem;
      align-items: center;
    }
    .navbar li {
      display: flex;
      align-items: center;
    }
    .navbar li a {
      color: white;
      text-decoration: none;
      font-weight: bold;
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }
    .navbar li a:hover {
      color: #f39c12;
    }
    .icon {
      width: 40px;
      height: 40px;
    }
  </style>
  