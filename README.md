<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Fluxograma - História do Superman</title>
  <script src="https://cdn.jsdelivr.net/npm/mermaid/dist/mermaid.min.js"></script>
  <style>
    body {
      font-family: 'Poppins', sans-serif;
      background: url('https://wallpapers.com/images/hd/superman-artwork-4k-tzghs0wx7ptk73kx.jpg') no-repeat center center fixed;
      background-size: cover;
      color: #fff;
      padding: 20px;
      margin: 0;
    }
    h1 {
      color: #0074cc;
      text-align: center;
      font-size: 2.5rem;
      margin-top: 10px;
      text-shadow: 2px 2px 8px rgba(0, 0, 0, 0.8);
    }
    #container {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      gap: 20px;
    }
    #flowchart {
      flex: 2;
      background-color: rgba(0, 0, 0, 0.8);
      padding: 20px;
      border-radius: 15px;
      box-shadow: 0 8px 15px rgba(0, 0, 0, 0.8);
    }
    #story {
      flex: 1;
      background-color: rgba(255, 255, 255, 0.9);
      padding: 20px;
      border-radius: 15px;
      color: #000;
      font-size: 1rem;
      box-shadow: 0 8px 15px rgba(0, 0, 0, 0.5);
      overflow-y: auto;
      height: 600px;
    }
    .mermaid {
      color: #fff;
    }
    footer {
      text-align: center;
      margin-top: 30px;
      font-size: 1rem;
      color: #aaa;
    }
    footer a {
      color: #0074cc;
      text-decoration: none;
    }
    footer a:hover {
      text-decoration: underline;
    }
  </style>
</head>
<body>
  <h1>Fluxograma da História do Superman</h1>
  <div id="container">
    <div id="flowchart">
      <div class="mermaid">
        graph TD
          krypton([🌌 Krypton está em perigo]):::bubble --> kalel([👶 Kal-El é enviado à Terra]):::bubble
          kalel --> clark([🌽 Criado no Kansas como Clark Kent]):::bubble
          clark --> poderes([🦸 Descobre seus incríveis poderes]):::bubble
          poderes --> superman([💪 Decide usar seus poderes como Superman]):::bubble
          superman --> vilões([⚔️ Enfrenta vilões como Lex Luthor]):::bubble
          vilões --> esperança([💡 Torna-se um símbolo de esperança e justiça]):::bubble

        classDef bubble fill:#0074cc,stroke:#fff,stroke-width:2px,color:#fff,font-size:14px,font-weight:bold;
      </div>
    </div>
    <div id="story">
      <h2>História do Superman</h2>
      <p>Clique em uma etapa do fluxograma para ver a história aqui!</p>
    </div>
  </div>
  <footer>
    <p>Desenvolvido com <a href="https://mermaid.js.org/">Mermaid.js</a>.</p>
  </footer>
  <script>
    mermaid.initialize({ startOnLoad: true, theme: "dark" });

    // Histórias detalhadas
    const stories = {
      krypton: `
        Krypton está em perigo! O núcleo do planeta está se desestabilizando, e Jor-El, o maior cientista kryptoniano, 
        tenta avisar a população. Ele e sua esposa Lara decidem salvar seu filho recém-nascido, Kal-El, enviando-o à Terra 
        em uma nave antes que Krypton seja destruído.
      `,
      kalel: `
        A nave de Kal-El aterrissa no Kansas, onde ele é encontrado por Jonathan e Martha Kent. O casal o adota e o cria como Clark Kent. 
        Eles ensinam a Kal-El valores importantes, como bondade e responsabilidade, enquanto ele cresce como um humano comum.
      `,
      clark: `
        Durante sua infância e adolescência, Clark Kent começa a descobrir habilidades extraordinárias, como superforça, invulnerabilidade, 
        visão de calor e capacidade de voar. Apesar disso, ele enfrenta dilemas sobre como usar seus poderes enquanto mantém sua identidade em segredo.
      `,
      poderes: `
        Ao atingir a maturidade, Clark percebe que seus poderes podem ser usados para ajudar a humanidade. Inspirado pelos ensinamentos de seus pais 
        adotivos, ele adota a responsabilidade de proteger os mais fracos e combater as injustiças.
      `,
      superman: `
        Clark decide usar um traje icônico e adota o nome "Superman". Em Metrópolis, ele trabalha como jornalista no Planeta Diário para se manter próximo das 
        notícias e continuar sua missão de proteger o mundo sem revelar sua identidade.
      `,
      vilões: `
        Superman enfrenta diversos inimigos poderosos ao longo de sua jornada. Lex Luthor, um gênio do mal, é seu maior adversário humano, enquanto 
        vilões kryptonianos, como General Zod, e ameaças cósmicas, como Brainiac, desafiam sua força e coragem.
      `,
      esperança: `
        Ao longo dos anos, Superman se torna um símbolo de esperança, justiça e altruísmo. Ele inspira outros heróis e pessoas comuns a fazerem o bem, 
        provando que mesmo o mais poderoso entre nós pode ser humilde e compassivo.
      `
    };

    // Adiciona eventos de clique para exibir as histórias
    document.addEventListener("click", function (event) {
      const targetId = event.target.closest("g")?.getAttribute("data-id");
      if (stories[targetId]) {
        document.querySelector("#story").innerHTML = `
          <h2>${event.target.textContent || "Detalhe"}</h2>
          <p>${stories[targetId]}</p>
        `;
      }
    });
  </script>
</body>
</html>
