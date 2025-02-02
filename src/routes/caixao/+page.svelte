<script>
    import { onMount } from 'svelte';
  
    let nome = '';
    let idade = '';
    let fraqueza = '';
    let habilidade = '';
    let estilo = '';
    let resultado = '';
  
    function criarVampiro() {
      if (!nome || !idade || !fraqueza || !habilidade || !estilo) {
        resultado = 'Preencha todos os campos para criar seu vampiro!';
        return;
      }
      resultado = `Seu vampiro se chama ${nome}, tem ${idade} anos de existência.
        Sua maior fraqueza é ${fraqueza}, mas em compensação possui a habilidade de ${habilidade}.
        Ele prefere um estilo ${estilo} e vaga pelas noites em busca de novos desafios.`;
    }
  </script>
  
  <svelte:head>
    <title>Crie seu Próprio Vampiro</title>
  </svelte:head>
  
  <div class="container">
    <h1 class="title">Crie seu Proprio Vampiro 🧛‍♂️</h1>
    <div class="form">
      <input type="text" placeholder="Nome do Vampiro" bind:value={nome} />
      <input type="number" placeholder="Idade (anos)" bind:value={idade} />
      <select bind:value={fraqueza}>
        <option value="">Escolha uma fraqueza...</option>
        <option value="Luz do sol">Luz do sol</option>
        <option value="Estacas de madeira">Estacas de madeira</option>
        <option value="Água benta">Água benta</option>
        <option value="Prata">Prata</option>
      </select>
      <select bind:value={habilidade}>
        <option value="">Escolha uma habilidade...</option>
        <option value="Hipnose">Hipnose</option>
        <option value="Transformação em morcego">Transformação em morcego</option>
        <option value="Regeneração">Regeneração</option>
        <option value="Controle das sombras">Controle das sombras</option>
      </select>
      <select bind:value={estilo}>
        <option value="">Escolha um estilo...</option>
        <option value="Aristocrático">Aristocrático</option>
        <option value="Gótico sombrio">Gótico sombrio</option>
        <option value="Caçador solitário">Caçador solitário</option>
        <option value="Misterioso e sedutor">Misterioso e sedutor</option>
      </select>
      <button on:click={criarVampiro}>Criar Vampiro</button>
    </div>
    <p class="resultado">{resultado}</p>
  </div>
  
  <style>
    h1{
        font-family: Dracula;
    }
    .container {
      max-width: 2000px;
      margin: auto;
      padding: 20px;
      text-align: center;
      background: black;
      color: white;
      font-family: 'UnifrakturMaguntia', cursive;
    }
  
    .title {
      color: red;
      font-size: 90px;
      text-shadow: 2px 2px black;
    }
  
    .form {
      display: flex;
      flex-direction: column;
      gap: 10px;
      margin-top: 20px;
    }
  
    input, select, button {
      padding: 10px;
      font-size: 16px;
      border: none;
      border-radius: 5px;
    }
  
    input, select {
      background: #333;
      color: white;
    }
  
    button {
      background: red;
      color: white;
      cursor: pointer;
      transition: 0.3s;
    }
  
    button:hover {
      background: darkred;
    }
  
    .resultado {
      margin-top: 20px;
      font-size: 30px;
    }
  </style>
  