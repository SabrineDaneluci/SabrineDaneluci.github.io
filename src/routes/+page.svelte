<script>
    export let title = "Vampiros: Historia e Curiosidades";
  </script>
  
  <svelte:head>
    <title>{title}</title>
  </svelte:head>
  
  <div class="container Dracula">
    <center><h1 style="font-family:Dracula" class="text-5xl text-red-500 mb-6">{title}</h1></center>
    
    <section class="mb-6 text-white historia-container">
      <div class="historia-image">
        <img src="draculaa.jpg" alt="Drácula" class="vampire-image" />
      </div>
      <div class="historia-text">
        <h2 class="text-3xl font-semibold text-red-400">Origens e História</h2>
        <p class="mt-2 text-gray-300">
          A origem do mito dos vampiros remonta a tempos antigos e está profundamente enraizada em crenças culturais de diversas civilizações.
          Na Mesopotâmia, surgiram as primeiras narrativas sobre seres sobrenaturais que se alimentavam da energia vital dos vivos.
          Figuras como Lilitu, no panteão sumério, e Lamastu, na cultura acadiana, eram representações de seres que atacavam à noite e
          se alimentavam do sangue ou da força vital de bebês e mulheres grávidas.
        </p>
        <p class="mt-2 text-gray-300">
          Durante a Idade Média, os relatos sobre cadáveres que voltavam à vida se multiplicaram, especialmente na Europa Oriental.
          O medo da morte e das doenças contribuiu para o surgimento de crenças em vampiros como entidades que retornavam para assombrar os vivos.
          Enterros precários e doenças desconhecidas, como a porfiria, podem ter originado a crença em criaturas que evitavam a luz do sol e precisavam de sangue.
        </p>
        <p class="mt-2 text-gray-300">
          O termo "vampiro" começou a ganhar notoriedade no século XVIII, com relatos de exumações de corpos suspeitos e medidas preventivas,
          como estacas no coração, decapitações e queima dos cadáveres. Foi nesse período que surgiram obras literárias e registros oficiais
          que consolidaram a imagem do vampiro como um ser maldito e perigoso.
        </p>
        <p class="mt-2 text-gray-300">
          No século XIX, o vampiro se transformou em uma figura mais aristocrática e sedutora, principalmente após o lançamento de "Drácula",
          de Bram Stoker, em 1897. Esse romance consolidou a imagem moderna do vampiro como um ser imortal, elegante e dotado de habilidades sobrenaturais,
          como hipnose e metamorfose. Desde então, a figura do vampiro passou por várias transformações, sendo adaptada para diferentes mídias,
          do cinema à literatura contemporânea.
        </p>
      </div>
    </section>
    
    <section class="mb-6 text-white curiosidades-container">
      <div class="curiosidades-text">
        <h2 class="text-3xl font-semibold text-red-400">Curiosidades</h2>
        <ul class="mt-2 list-disc list-inside text-gray-300">
          <li>A palavra "vampiro" tem origem no sérvio "vampir" e entrou na língua inglesa no século XVIII.</li>
          <li>Muitos relatos de vampiros estão ligados a epidemias, onde pessoas eram encontradas exumadas e com sangue ao redor da boca.</li>
          <li>O mito dos vampiros varia globalmente: na China, existe o "Jiangshi", um cadáver reanimado que suga a energia vital.</li>
          <li>Na Grécia antiga, acreditava-se que os mortos poderiam voltar como "vrykolakas" e assombrar suas famílias.</li>
          <li>Na Idade Média, medidas como enterrar os mortos de bruços ou com pedras na boca eram adotadas para evitar que voltassem à vida.</li>
          <li>O alho e o espelho como defesas contra vampiros surgiram da ideia de que essas criaturas possuíam uma alma corrompida e não tinham reflexo.</li>
          <li>Na cultura popular, os vampiros foram transformados em personagens glamorosos, com destaque para romances e séries de televisão.</li>
          <li>Há teorias que relacionam o mito dos vampiros a doenças como raiva e porfiria, que causavam extrema sensibilidade à luz.</li>
          <li>Na mitologia asteca, havia a deusa Cihuateteo, que era um espírito de mulher morta no parto e considerada uma espécie de vampira.</li>
          <li>Algumas culturas acreditam que o sangue dos vampiros pode conceder poderes especiais ou até mesmo a imortalidade.</li>
        </ul>
      </div>
      <div class="curiosidades-image">
        <img src="nosferatu.jpg" alt="Nosferatu" class="vampire-image" />
      </div>
    </section>
    
    <footer class="mt-10 text-gray-400 text-sm">
      <center><p>Feito com sangue e paixão por histórias de vampiros 🧛‍♂️</p></center>
    </footer>
  </div>
  
  <style>
    @import url('https://fonts.googleapis.com/css2?family=UnifrakturMaguntia&display=swap');
  
    body {
        background-color: black;
        color: white;
        font-family: 'UnifrakturMaguntia', cursive;
        text-align: center;
    }
  
    h1 {
        color: red;
        font-size: 150px;
        text-shadow: 4px 4px black;
    }
  
    h2 {
        color: red;
        font-size: 35px;
        text-decoration: underline;
    }
  
    .historia-container {
        display: flex;
        align-items: center;
        justify-content: space-between;
        gap: 20px;
    }
  
    .historia-text {
        flex: 1;
        text-align: left;
    }
  
    .historia-image {
        flex: 1;
        display: flex;
        justify-content: center;
    }
  
    .curiosidades-container {
        display: flex;
        align-items: center;
        justify-content: space-between;
        gap: 20px;
    }
  
    .curiosidades-text {
        flex: 1;
        text-align: left;
    }
  
    .curiosidades-image {
        flex: 1;
        display: flex;
        justify-content: center;
    }
  
    .vampire-image {
        max-width: 500px;
        border: 5px solid red;
        border-radius: 10px;
    }

    li{
        color: black;
        font-size: 25px;
        font-family:'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    }

    p{
        color: black;
        font-size: 25px;
        font-family:'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    }
  </style>
  