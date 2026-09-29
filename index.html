<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Pokédex Web</title>
<style>
  /* Reset básico */
  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: #f0f2f5;
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    padding: 20px;
  }

  /* Container principal */
  .pokedex-container {
    background-color: #dc0a2d;
    width: 100%;
    max-width: 380px;
    padding: 30px 20px;
    border-radius: 20px;
    box-shadow: 0 15px 25px rgba(0, 0, 0, 0.3);
    text-align: center;
  }

  header h1 { color: white; font-size: 28px; margin-bottom: 5px; }
  header p  { color: #ffcccc; font-size: 14px; margin-bottom: 25px; }

  /* Busca */
  .search-area { display: flex; gap: 10px; margin-bottom: 20px; }

  .search-area input {
    flex: 1;
    min-width: 0;
    padding: 12px;
    border: none;
    border-radius: 8px;
    font-size: 16px;
    outline: none;
  }
  .search-area input:focus-visible { box-shadow: 0 0 0 3px #ffcccc; }

  .search-area button {
    background-color: #2d3436;
    color: white;
    border: none;
    padding: 12px 18px;
    border-radius: 8px;
    font-weight: bold;
    cursor: pointer;
    transition: 0.3s;
  }
  .search-area button:hover { background-color: #636e72; }
  .search-area button:focus-visible { outline: 3px solid #ffcccc; outline-offset: 2px; }

  .oculto { display: none !important; }

  #mensagemErro { color: white; font-weight: bold; margin-bottom: 15px; }

  /* Cartão do resultado */
  .pokemon-card {
    background-color: white;
    border-radius: 15px;
    padding: 20px;
    box-shadow: inset 0 0 10px rgba(0, 0, 0, 0.1);
    animation: fadeIn 0.4s ease-in-out;
  }

  .pokemon-card img {
    width: 150px;
    height: 150px;
    background-color: #f1f2f6;
    border-radius: 50%;
    margin-bottom: 15px;
    border: 4px solid #dfe4ea;
  }

  .badge {
    background-color: #747d8c;
    color: white;
    padding: 4px 10px;
    border-radius: 12px;
    font-size: 12px;
    font-weight: bold;
  }

  .info h2 {
    color: #2f3542;
    text-transform: capitalize;
    margin: 10px 0;
    font-size: 24px;
  }
  .info p { color: #57606f; font-size: 15px; margin-bottom: 5px; }

  @keyframes fadeIn {
    from { opacity: 0; transform: scale(0.9); }
    to   { opacity: 1; transform: scale(1); }
  }

  @media (prefers-reduced-motion: reduce) {
    .pokemon-card { animation: none; }
    .search-area button { transition: none; }
  }
</style>
</head>
<body>
  <main class="pokedex-container">
    <header>
      <h1>Pokédex Digital 🔴</h1>
      <p>Digite o nome ou número do Pokémon</p>
    </header>

    <!-- Área de busca -->
    <section class="search-area">
      <input type="text" id="inputPokemon" placeholder="Ex: pikachu ou 25" autocomplete="off">
      <button id="btnBuscar">Buscar</button>
    </section>

    <!-- Mensagem de carregamento/erro -->
    <p id="mensagemErro" class="oculto" role="status">Carregando...</p>

    <!-- Cartão do resultado -->
    <section id="cardPokemon" class="pokemon-card oculto">
      <img id="imagemPokemon" src="" alt="Imagem do Pokémon">
      <div class="info">
        <span id="numeroPokemon" class="badge">#000</span>
        <h2 id="nomePokemon">Nome</h2>
        <p>Tipo: <strong id="tipoPokemon">---</strong></p>
        <p>Peso: <strong id="pesoPokemon">---</strong> kg</p>
        <p>Altura: <strong id="alturaPokemon">---</strong> m</p>
      </div>
    </section>
  </main>

<script>
  async function buscarPokemon() {
    // 1. Captura o valor digitado (a API exige minúsculas e sem espaços)
    const input = document.getElementById('inputPokemon').value.toLowerCase().trim();
    const card = document.getElementById('cardPokemon');
    const msg = document.getElementById('mensagemErro');

    // Validação de campo vazio
    if (input === "") {
      alert("Por favor, digite um nome ou número!");
      return;
    }

    // Esconde o card e mostra "carregando"
    card.classList.add('oculto');
    msg.classList.remove('oculto');
    msg.innerText = "Buscando na internet... 📡";

    try {
      // 2. Requisição HTTP (GET) para a API pública
      const resposta = await fetch(`https://pokeapi.co/api/v2/pokemon/${encodeURIComponent(input)}`);

      // 3. fetch NÃO lança erro em 404, então verificamos manualmente
      if (!resposta.ok) {
        throw new Error("Pokémon não encontrado!");
      }

      // 4. Converte a resposta para objeto JavaScript
      const dados = await resposta.json();

      // 5. Atualiza o DOM com os dados recebidos
      document.getElementById('nomePokemon').innerText = dados.name;
      document.getElementById('numeroPokemon').innerText = "#" + dados.id;

      // Peso: hectogramas -> kg | Altura: decímetros -> m
      document.getElementById('pesoPokemon').innerText = (dados.weight / 10).toFixed(1);
      document.getElementById('alturaPokemon').innerText = (dados.height / 10).toFixed(1);

      // Todos os tipos (alguns Pokémon têm dois)
      document.getElementById('tipoPokemon').innerText =
        dados.types.map(t => t.type.name.toUpperCase()).join(" / ");

      // Imagem oficial, com sprite pequeno como plano B
      const imagem = document.getElementById('imagemPokemon');
      imagem.src = dados.sprites.other['official-artwork'].front_default
                || dados.sprites.front_default;
      imagem.alt = "Imagem de " + dados.name;

      // Esconde a mensagem e mostra o cartão
      msg.classList.add('oculto');
      card.classList.remove('oculto');

    } catch (erro) {
      msg.innerText = "❌ Ops! Pokémon não encontrado.";
      console.error(erro);
    }
  }

  // Botão e tecla Enter
  document.getElementById('btnBuscar').addEventListener('click', buscarPokemon);
  document.getElementById('inputPokemon').addEventListener('keydown', (e) => {
    if (e.key === 'Enter') buscarPokemon();
  });
</script>
</body>
</html>
