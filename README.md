


<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<style>
  @import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Sans:wght@300;400;500;600&display=swap');

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    font-family: 'DM Sans', sans-serif;
    background: #0d0d0d;
    color: #f0ece0;
    min-height: 100vh;
  }

  header {
    background: #0d0d0d;
    border-bottom: 1px solid #2a2a2a;
    padding: 1.5rem 2rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    position: sticky;
    top: 0;
    z-index: 100;
  }

  .logo {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 28px;
    letter-spacing: 3px;
    color: #e8c05a;
  }

  .logo span { color: #f0ece0; }

  .progress-wrap {
    display: flex;
    align-items: center;
    gap: 12px;
  }

  .progress-bar-outer {
    width: 160px;
    height: 6px;
    background: #2a2a2a;
    border-radius: 3px;
    overflow: hidden;
  }

  .progress-bar-inner {
    height: 100%;
    background: linear-gradient(90deg, #e8c05a, #c97c2a);
    border-radius: 3px;
    transition: width 0.4s ease;
  }

  .progress-text {
    font-size: 13px;
    color: #888;
    font-weight: 500;
    white-space: nowrap;
  }

  .hero {
    background: #111;
    border-bottom: 1px solid #2a2a2a;
    padding: 2.5rem 2rem;
    text-align: center;
  }

  .hero h1 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 52px;
    letter-spacing: 4px;
    color: #f0ece0;
    line-height: 1;
    margin-bottom: 0.5rem;
  }

  .hero h1 em {
    color: #e8c05a;
    font-style: normal;
  }

  .hero p {
    color: #888;
    font-size: 14px;
    letter-spacing: 1px;
    text-transform: uppercase;
  }

  .stats-row {
    display: flex;
    justify-content: center;
    gap: 2rem;
    margin-top: 1.5rem;
  }

  .stat {
    text-align: center;
  }

  .stat-num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 32px;
    color: #e8c05a;
    line-height: 1;
  }

  .stat-label {
    font-size: 11px;
    color: #666;
    text-transform: uppercase;
    letter-spacing: 1px;
  }

  .filter-row {
    display: flex;
    gap: 8px;
    padding: 1.2rem 2rem;
    border-bottom: 1px solid #1e1e1e;
    flex-wrap: wrap;
    align-items: center;
  }

  .filter-label {
    font-size: 12px;
    color: #666;
    text-transform: uppercase;
    letter-spacing: 1px;
    margin-right: 4px;
  }

  .filter-btn {
    background: transparent;
    border: 1px solid #333;
    color: #888;
    padding: 5px 14px;
    border-radius: 20px;
    font-size: 12px;
    cursor: pointer;
    transition: all 0.2s;
    font-family: 'DM Sans', sans-serif;
  }

  .filter-btn:hover, .filter-btn.active {
    background: #e8c05a;
    border-color: #e8c05a;
    color: #0d0d0d;
    font-weight: 600;
  }

  .grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 1px;
    background: #1e1e1e;
    padding: 0;
  }

  .card {
    background: #111;
    padding: 1.5rem;
    transition: background 0.2s;
    position: relative;
    cursor: pointer;
  }

  .card:hover { background: #161616; }

  .card.done { background: #0f1a10; }
  .card.done:hover { background: #131f14; }

  .card-top {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    margin-bottom: 1rem;
  }

  .day-badge {
    display: flex;
    flex-direction: column;
    align-items: center;
    background: #1e1e1e;
    border-radius: 8px;
    padding: 6px 12px;
    min-width: 52px;
  }

  .card.done .day-badge { background: #1a2e1b; }

  .day-num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 28px;
    color: #e8c05a;
    line-height: 1;
  }

  .card.done .day-num { color: #5aad62; }

  .day-week {
    font-size: 10px;
    color: #666;
    text-transform: uppercase;
    letter-spacing: 1px;
  }

  .card-type {
    font-size: 10px;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 1.5px;
    padding: 4px 10px;
    border-radius: 20px;
    border: 1px solid;
  }

  .type-reels { color: #c97c2a; border-color: #c97c2a; background: rgba(201,124,42,0.08); }
  .type-foto { color: #4a90c4; border-color: #4a90c4; background: rgba(74,144,196,0.08); }
  .type-carrossel { color: #9b6bdb; border-color: #9b6bdb; background: rgba(155,107,219,0.08); }
  .type-stories { color: #d44a6a; border-color: #d44a6a; background: rgba(212,74,106,0.08); }

  .card-theme {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 18px;
    letter-spacing: 1.5px;
    color: #f0ece0;
    margin-bottom: 0.6rem;
    line-height: 1.2;
  }

  .card.done .card-theme { color: #5aad62; }

  .card-copy {
    font-size: 13px;
    color: #777;
    line-height: 1.6;
    margin-bottom: 0.8rem;
    display: -webkit-box;
    -webkit-line-clamp: 3;
    -webkit-box-orient: vertical;
    overflow: hidden;
  }

  .card-caption {
    font-size: 12px;
    color: #555;
    line-height: 1.5;
    font-style: italic;
    margin-bottom: 1rem;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
    overflow: hidden;
  }

  .hashtags {
    font-size: 11px;
    color: #3a7abf;
    line-height: 1.6;
    margin-bottom: 1rem;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
    overflow: hidden;
  }

  .card-image-hint {
    background: #1a1a1a;
    border: 1px dashed #333;
    border-radius: 6px;
    padding: 8px 12px;
    font-size: 11px;
    color: #555;
    margin-bottom: 1rem;
    display: flex;
    align-items: center;
    gap: 6px;
  }

  .card.done .card-image-hint { border-color: #2a4a2b; }

  .img-icon { font-size: 14px; }

  .check-row {
    display: flex;
    align-items: center;
    gap: 10px;
    padding-top: 1rem;
    border-top: 1px solid #1e1e1e;
  }

  .card.done .check-row { border-color: #1a2e1b; }

  .check-label {
    display: flex;
    align-items: center;
    gap: 8px;
    cursor: pointer;
    flex: 1;
  }

  .custom-check {
    width: 20px;
    height: 20px;
    border: 2px solid #333;
    border-radius: 4px;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all 0.2s;
    flex-shrink: 0;
  }

  .card.done .custom-check {
    background: #5aad62;
    border-color: #5aad62;
  }

  .checkmark {
    display: none;
    color: white;
    font-size: 13px;
    font-weight: 700;
  }

  .card.done .checkmark { display: block; }

  .check-text {
    font-size: 13px;
    color: #666;
  }

  .card.done .check-text {
    color: #5aad62;
    font-weight: 500;
  }

  .expand-btn {
    background: transparent;
    border: 1px solid #2a2a2a;
    color: #666;
    padding: 4px 10px;
    border-radius: 4px;
    font-size: 11px;
    cursor: pointer;
    font-family: 'DM Sans', sans-serif;
    transition: all 0.2s;
    white-space: nowrap;
  }

  .expand-btn:hover {
    border-color: #444;
    color: #999;
  }

  .card-extra {
    display: none;
    margin-top: 1rem;
    padding-top: 1rem;
    border-top: 1px solid #1e1e1e;
  }

  .card-extra.open { display: block; }

  .extra-section {
    margin-bottom: 0.8rem;
  }

  .extra-label {
    font-size: 10px;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 1.5px;
    color: #555;
    margin-bottom: 4px;
  }

  .extra-text {
    font-size: 13px;
    color: #888;
    line-height: 1.6;
  }

  .extra-tags {
    font-size: 12px;
    color: #3a7abf;
    line-height: 1.7;
  }

  footer {
    text-align: center;
    padding: 2rem;
    color: #444;
    font-size: 12px;
    border-top: 1px solid #1e1e1e;
    letter-spacing: 1px;
    text-transform: uppercase;
  }
</style>
</head>
<body>

<header>
  <div class="logo">Via <span>Crux</span> Escalada</div>
  <div class="progress-wrap">
    <div class="progress-bar-outer">
      <div class="progress-bar-inner" id="progressBar" style="width:0%"></div>
    </div>
    <div class="progress-text" id="progressText">0 / 31 publicações</div>
  </div>
</header>

<div class="hero">
  <h1>Calendário <em>Editorial</em><br>Maio 2025</h1>
  <p>Via Crux Escalada · Planejamento de Conteúdo</p>
  <div class="stats-row">
    <div class="stat">
      <div class="stat-num" id="statFeito">0</div>
      <div class="stat-label">Feitos</div>
    </div>
    <div class="stat">
      <div class="stat-num" id="statRestantes">31</div>
      <div class="stat-label">Restantes</div>
    </div>
    <div class="stat">
      <div class="stat-num" id="statPercent">0%</div>
      <div class="stat-label">Completo</div>
    </div>
  </div>
</div>

<div class="filter-row">
  <span class="filter-label">Filtrar:</span>
  <button class="filter-btn active" onclick="filterCards('all', this)">Todos</button>
  <button class="filter-btn" onclick="filterCards('pendente', this)">Pendentes</button>
  <button class="filter-btn" onclick="filterCards('feito', this)">Concluídos</button>
  <button class="filter-btn" onclick="filterCards('reels', this)">Reels</button>
  <button class="filter-btn" onclick="filterCards('foto', this)">Foto</button>
  <button class="filter-btn" onclick="filterCards('carrossel', this)">Carrossel</button>
  <button class="filter-btn" onclick="filterCards('stories', this)">Stories</button>
</div>

<div class="grid" id="mainGrid"></div>

<footer>Via Crux Escalada · Calendário Editorial Maio 2025</footer>

<script>
const posts = [
  { dia: 1, semana: "Qui", tipo: "reels", tema: "Bem-vindo a Maio! Abertura de temporada", copy: "Maio chegou e as paredes estão te chamando! Mostre um clipe dinâmico com as melhores rotas do mês, trilha animada e CTA para as aulas.", legenda: "Maio é o mês de subir mais alto! 🧗 As nossas turmas de escalada estão abertas para todos os níveis. Vem descobrir o poder de conquistar cada parede. Link na bio para se inscrever!", image: "Vídeo de abertura: atletas escalando, câmera lenta nas mãos no gripe, trilha motivacional", tags: "#ViacruxEscalada #EscaladaBrasil #Escalada #ClimbingBrasil #Climbing #EscaladaEsportiva #Climb #BoulderBrasil #EscaladaIniciante #MaisAlto" },
  { dia: 2, semana: "Sex", tipo: "foto", tema: "Técnica do dia: Posição dos pés", copy: "A maioria dos iniciantes negligencia os pés. Mostre a diferença entre pisar errado e certo com uma foto didática e legenda que provoque curiosidade.", legenda: "Sabia que 70% da escalada está nos seus pés? 👣 Na Via Crux você aprende a técnica desde o início. Vagas para iniciantes abertas — link na bio!", image: "Close nos pés do escalador no agarramento, iluminação clara, ângulo lateral educativo", tags: "#TecnicaDeEscalada #EscaladaDicas #AprendaEscalada #ViacruxEscalada #FeetFirst #ClimbingTips #EscaladaSP #Bouldering" },
  { dia: 3, semana: "Sáb", tipo: "carrossel", tema: "5 motivos para começar a escalar", copy: "Carrossel com slides visuais: benefícios físicos, mentais, sociais, de autoestima e superação. Último slide com CTA forte.", legenda: "Você ainda não escala? Aqui vão 5 razões pra isso mudar hoje 👉 Deslize e se convença. A primeira aula é você com a parede — e não tem como não se apaixonar.", image: "Slide 1: Capa impactante. Slides 2-6: cada benefício com foto + texto curto. Slide 7: CTA", tags: "#EscaladaParaTodos #BeneficiosDaEscalada #ViacruxEscalada #EscaladaEsportiva #QuerEscalar #ClimbingLife #Fitness #DesafiosPessoais" },
  { dia: 4, semana: "Dom", tipo: "stories", tema: "Quiz: Qual escalador é você?", copy: "Stories interativo com enquetes: 'Prefere boulder ou via esportiva?', 'Chegada na palma ou na ponta dos dedos?', revela o perfil no final.", legenda: "Descubra seu perfil de escalador! Responda o quiz nos stories 🎯 Todo perfil tem uma turma ideal na Via Crux — conta pra gente o resultado!", image: "Stories com fundo texturizado rocha, perguntas em caixas grandes, ícones de escalada", tags: "#QuizEscalada #EscaladaBrasil #ViacruxEscalada #Stories #ClimbingCommunity" },
  { dia: 5, semana: "Seg", tipo: "reels", tema: "Transformação: antes e depois de 3 meses", copy: "Depoimento de aluno com progresso em 3 meses. Mostrar primeiros passos e conquista de rota difícil. Emocionante e autêntico.", legenda: "3 meses atrás ela mal se pendurava na parede. Hoje? Conquistou a rota que parecia impossível. 💪 Essa pode ser sua história. Primeiras aulas na Via Crux são para você.", image: "Vídeo split: início (hesitante, ajuda do instrutor) e evolução (segura, independente)", tags: "#TransformacaoEscalada #EscaladaIniciante #ViacruxEscalada #ProgressoEscalada #ClimbingJourney #Motivacao #EvolucaoNaEscalada" },
  { dia: 6, semana: "Ter", tipo: "foto", tema: "Destaque: Instrutor da semana", copy: "Apresente um instrutor com foto profissional e texto sobre sua trajetória. Humaniza a escola e gera conexão com o público.", legenda: "Conheça quem vai te guiar na parede! Nossos instrutores são apaixonados por escalada e por ensinar. Marque quem você quer treinar junto 👇", image: "Foto do instrutor na parede ou no estúdio, expressão genuína, luz natural", tags: "#InstrutorDeEscalada #ViacruxEscalada #EquipeViacrux #ClimbingCoach #EscaladaComSeguranca #TreinoDeEscalada" },
  { dia: 7, semana: "Qua", tipo: "carrossel", tema: "Guia do Equipamento Básico", copy: "Carrossel educativo: sapatilha, baudrier, corda, magnésio, capacete. O que é cada um, para que serve, quando usar.", legenda: "Perdido com os equipamentos de escalada? 🪢 Esse guia é pra você! Na Via Crux os equipamentos são fornecidos nas aulas — você só precisa aparecer.", image: "Foto de cada equipamento com fundo neutro, estilo editorial clean", tags: "#EquipamentoEscalada #GuiaEscalada #ViacruxEscalada #EscaladaSegura #ClimbingGear #SapatilhaEscalada #BaudriEscalada" },
  { dia: 8, semana: "Qui", tipo: "reels", tema: "Dia de treino: de dentro da escola", copy: "Bastidores do treino: câmera acompanha alunos e instrutores. Energia, garra, superação. Mostra o ambiente real da escola.", legenda: "É assim que acontece a mágica na Via Crux! ✨ Cada treino é um desafio novo. Turmas abertas para todos os níveis — venha viver isso.", image: "Vídeo dinâmico de treino real, vários ângulos, música enérgica, cortes rápidos", tags: "#TreinoEscalada #ViacruxEscalada #DentroDaEscola #ClimbingTraining #AulasDeEscalada #EscaladaEsportiva" },
  { dia: 9, semana: "Sex", tipo: "foto", tema: "Frase motivacional de escalada", copy: "Imagem poderosa de escalador no topo com frase sobre superação e conquista. Gera compartilhamento orgânico.", legenda: "'A parede não desce até você. Você que sobe até ela.' — Essa é a filosofia que vivemos na Via Crux. Marca quem precisa ouvir isso 🏔", image: "Escalador no topo de rota, vista de baixo para cima, céu ou parede ao fundo, frase sobreposta", tags: "#FraseEscalada #Motivacao #ViacruxEscalada #ClimbingMotivation #SuperacaoPessoal #EscaladaInspira #Conquista" },
  { dia: 10, semana: "Sáb", tipo: "carrossel", tema: "Erros comuns de iniciantes (e como evitar)", copy: "Carrossel educativo e divertido: 5 erros clássicos que todo iniciante comete, com humor e orientação. Altamente compartilhável.", legenda: "Se identificou com algum desses erros? 😅 Não se preocupa — na Via Crux a gente corrige tudo isso! Aulas personalizadas para iniciantes.", image: "Ilustrações ou fotos estilizadas de cada erro, visual divertido e levemente humorístico", tags: "#ErrosDeEscalada #ViacruxEscalada #DicasEscalada #AulasDeEscalada #EscaladaIniciante #AprendaEscalada #ClimbingTips" },
  { dia: 11, semana: "Dom", tipo: "stories", tema: "Enquete: Boulder ou Via Esportiva?", copy: "Stories direto com enquete, resultado nos próximos stories. Gera engajamento e coleta dados do público.", legenda: "A discussão eterna do escalador! 🤔 Vote e conta pra gente nos comentários qual você prefere e por quê.", image: "Background com foto das duas modalidades lado a lado, enquete centralizada", tags: "#BouldervsVia #EscaladaBrasil #ViacruxEscalada #BoulderBrasil #ViaEsportiva" },
  { dia: 12, semana: "Seg", tipo: "reels", tema: "Tutorial: primeiro nó para escalada", copy: "Tutorial rápido e didático do nó oito. Linguagem acessível, passo a passo visual. Extremamente útil para iniciantes.", legenda: "O nó que todo escalador precisa saber! 🪢 Em 60 segundos você aprende. Na Via Crux ensinamos tudo isso nas aulas — técnica + segurança desde o primeiro dia.", image: "Mãos em close aprendendo o nó, fundo neutro, texto sobreposto em cada passo", tags: "#NoOito #TecnicaEscalada #EscaladaSegura #ViacruxEscalada #ClimbingKnots #AprenderEscalada #TutorialEscalada" },
  { dia: 13, semana: "Ter", tipo: "foto", tema: "Aluno em destaque: conquista da semana", copy: "Feature de aluno real, com permissão, compartilhando conquista pessoal. Autentico, inspirador, prova social.", legenda: "Toda semana alguém na Via Crux conquista algo que parecia impossível 🙌 Essa semana foi a vez de [nome]! Qual vai ser a sua conquista?", image: "Foto do aluno na parede ou comemorando, expressão de alegria e orgulho", tags: "#AlunodaSemana #ViacruxEscalada #ProvasSocial #ConquistaEscalada #EscaladaBrasil #ComunidadeViacrux" },
  { dia: 14, semana: "Qua", tipo: "carrossel", tema: "Escalada para crianças: benefícios", copy: "Carrossel voltado para pais: desenvolvimento motor, confiança, coordenação, concentração. CTA para turmas infantis.", legenda: "Escalada não é só para adultos! 🧒 Crianças que escalam desenvolvem equilíbrio, confiança e foco. A Via Crux tem turmas especiais para os pequenos escaladores!", image: "Fotos de crianças escalando com sorrisos, ambiente seguro e colorido", tags: "#EscaladaInfantil #CriancasEscalando #ViacruxEscalada #DesenvolvimentoInfantil #AtividadeParaCriancas #EscaladaFamilia" },
  { dia: 15, semana: "Qui", tipo: "reels", tema: "15 de Maio: meio do mês, que tal começar?", copy: "Reels motivacional com contagem: 'Faltam só 16 dias pra você começar algo que vai mudar sua vida.' Urgência e FOMO.", legenda: "Você ainda está pensando em começar? Meio do mês é o momento perfeito! ⏰ As vagas estão quase esgotadas — clica no link e garante sua aula experimental.", image: "Vídeo com contador, imagens de escaladores satisfeitos, ritmo acelerado", tags: "#VamosComecar #ViacruxEscalada #AulaExperimental #EscaladaAgora #JaDecidiu #ClimbingLife #MudancaDeVida" },
  { dia: 16, semana: "Sex", tipo: "foto", tema: "Bastidores: a parede de boulder da escola", copy: "Apresente a estrutura física da escola com foto bonita da parede, destaque para qualidade e variedade de rotas.", legenda: "Já conhece a nossa parede? 🪨 Rotas para todos os níveis, ambientação profissional e instrutores especializados. Venha fazer uma visita — agendamento pelo link na bio.", image: "Foto angular da parede de boulder, iluminação dramática, agarramentos coloridos em evidência", tags: "#ParedeBoulder #ViacruxEscalada #EstruturadeEscalada #EscolaDeEscalada #BoulderSP #GymClimbing #IndoorClimbing" },
  { dia: 17, semana: "Sáb", tipo: "carrossel", tema: "Treino funcional + escalada: a combinação perfeita", copy: "Carrossel mostrando exercícios complementares à escalada: prancha, tração, equilíbrio. Posiciona a escola como especialista.", legenda: "Escalada é o treino funcional mais completo que existe! 💪 Corpo inteiro, mente focada e zero tédio. Nossas aulas misturam técnica e condicionamento.", image: "Fotos de exercícios funcionais relacionados à escalada, visual fitness e dinâmico", tags: "#TreinoFuncional #EscaladaFitness #ViacruxEscalada #CorpoInteiro #Condicionamento #ClimbingWorkout #EscaladaEsportiva" },
  { dia: 18, semana: "Dom", tipo: "stories", tema: "Conta rápida: quanto tempo você tem por semana?", copy: "Stories com enquete de tempo disponível. Responda nos DMs com sugestão de modalidade e frequência ideal.", legenda: "Quanto tempo você tem? Com 2h por semana já dá pra começar! 📅 A Via Crux se adapta à sua rotina.", image: "Stories clean com pergunta central e opções de resposta (1x, 2x, 3x+ por semana)", tags: "#TempoParaEscalada #ViacruxEscalada #RotinaDeTreino #EscaladaFlexivel" },
  { dia: 19, semana: "Seg", tipo: "reels", tema: "Reels: a sensação de chegar no topo", copy: "Vídeo emocional capturando o momento de chegada no topo de uma rota difícil. Foco na expressão de conquista.", legenda: "Esse momento... não tem como descrever. 🥹 Mas a gente garante que você vai querer sentir. Agende sua aula experimental e viva isso na Via Crux!", image: "Close na expressão do escalador chegando no topo, respiração pesada, sorriso de conquista", tags: "#TopoAlcancado #ViacruxEscalada #SensacaoDeConquista #EscaladaEmotion #ClimbingFeel #MomentoPuro #AulasDeEscalada" },
  { dia: 20, semana: "Ter", tipo: "foto", tema: "Comparação: escalada indoor vs outdoor", copy: "Foto díptico comparando os dois ambientes. Texto sobre como a escola prepara para a escalada ao ar livre.", legenda: "Começa dentro, conquista fora! 🌄 Na Via Crux você aprende as bases que vai usar nas grandes paredes lá fora. Donde começar? Aqui.", image: "Montagem: parede indoor colorida vs parede de rocha natural ao ar livre", tags: "#IndoorVsOutdoor #EscaladaIndoor #EscaladaOutdoor #ViacruxEscalada #PreparacaoEscalada #ClimbingEvolution" },
  { dia: 21, semana: "Qua", tipo: "carrossel", tema: "Como funciona a aula experimental", copy: "Carrossel passo a passo da jornada do aluno novo: chegada, apresentação, aquecimento, aula, feedback. Quebra objeções.", legenda: "Ainda com medo de não conseguir? 🫂 Olha como é simples começar na Via Crux! Sem experiência necessária, sem julgamento — só muita diversão.", image: "Sequência de fotos real de uma aula experimental, cada slide = uma etapa", tags: "#AulaExperimental #ViacruxEscalada #PrimeiraAula #SemExperiencia #EscaladaParaTodos #ComoFunciona" },
  { dia: 22, semana: "Qui", tipo: "reels", tema: "Reels motivacional: 'Você é capaz'", copy: "Montagem de escaladores de todos os perfis (peso, idade, gênero) conquistando rotas. Mensagem de inclusão.", legenda: "A escalada não escolhe corpo, não escolhe idade, não escolhe histórico. Ela escolhe quem tem coragem de tentar. E você tem? 💛 Via Crux te espera.", image: "Montagem inclusiva de diversos escaladores, música inspiracional, cortes no ritmo", tags: "#EscaladaInclusive #ParaTodos #ViacruxEscalada #EscaladaBrasil #DiversidadeEscalada #CorpoQueSobe #ClimbingForAll" },
  { dia: 23, semana: "Sex", tipo: "foto", tema: "Produto: apresente os planos da escola", copy: "Post visual e claro com os planos disponíveis, preços ou benefícios. Objetivo direto: conversão.", legenda: "Escolha seu plano e comece a escalar! 🧗 Mensalidade, aula avulsa ou pacote — a Via Crux tem a opção certa pra você. Detalhes na bio!", image: "Layout gráfico limpo com os planos, cores da marca, visual premium mas acessível", tags: "#PlanoEscalada #ViacruxEscalada #MensalidadeEscalada #InvestimentoNaVida #EscaladaSP #AulasDeEscalada" },
  { dia: 24, semana: "Sáb", tipo: "carrossel", tema: "Escalada e saúde mental: a ciência explica", copy: "Carrossel sobre os benefícios psicológicos da escalada: foco, gestão de ansiedade, autoestima. Com dados e referências.", legenda: "A escalada é meditação em movimento. 🧠 Ciência confirma os benefícios mentais de subir paredes. Que tal experimentar o melhor remédio sem efeito colateral?", image: "Visual médico-científico mas acessível, ícones de cérebro, gráficos simples, fotos de escaladores zen", tags: "#SaudeMental #EscaladaTerapeutica #ViacruxEscalada #BemEstar #AnsiedadeZero #ClimbingTherapy #MindfulClimbing" },
  { dia: 25, semana: "Dom", tipo: "stories", tema: "Domingo de motivação: semana nova chegando", copy: "Stories motivacional com frase + caixa de perguntas: 'Qual é o seu desafio dessa semana?'", legenda: "Domingo é dia de carregar as energias para a semana! ⚡ Qual parece impossível que você quer conquistar essa semana?", image: "Stories com fundo de pôr do sol ou parede de escalada, tipografia grande e impactante", tags: "#DomingoDomotivacao #ViacruxEscalada #SemanaNova #Desafio #EscaladaMotivation" },
  { dia: 26, semana: "Seg", tipo: "reels", tipo: "reels", tema: "Técnica avançada: movimentação lateral", copy: "Tutorial de movimentação lateral na parede para escaladores intermediários. Valoriza alunos que já treinam.", legenda: "Pra quem já está escalando: dominar o movimento lateral é o que separa o intermediário do avançado. 🎯 Nossos instrutores te ensinam na prática.", image: "Vídeo de lado mostrando o movimento lateral, marcação visual dos pés e mãos", tags: "#TecnicaAvancada #EscaladaIntermediaria #ViacruxEscalada #MovimentoLateral #ClimbingSkills #AprimorarEscalada" },
  { dia: 27, semana: "Ter", tipo: "foto", tema: "Citação de aluno: depoimento real", copy: "Post com foto + depoimento real de aluno (com permissão). Prova social poderosa para conversão.", legenda: "Palavras de quem vive a Via Crux! 💬 Nada melhor do que ouvir de quem já deu o primeiro passo. Você é o próximo?", image: "Foto do aluno com depoimento em overlay, estilo editorial, cores quentes", tags: "#Depoimento #ViacruxEscalada #ProvasSocial #AlunoViacrux #ResultadosReais #EscaladaTransforma" },
  { dia: 28, semana: "Qua", tipo: "carrossel", tema: "Programação de Junho: o que vem por aí", copy: "Prévia do mês seguinte: novos horários, eventos, workshops. Gera expectativa e mantém o público engajado.", legenda: "Junho vem com novidades na Via Crux! 🗓 Deslize para ver o que está chegando e garanta sua vaga com antecedência. Link na bio!", image: "Slides com visual de calendário, ícones de eventos, cores vibrantes e tipografia clara", tags: "#JunhoViacrux #ProgramacaoEscalada #ViacruxEscalada #Novidades #EventosEscalada #Workshop" },
  { dia: 29, semana: "Qui", tipo: "reels", tema: "Reels: superando o medo de altura", copy: "Conteúdo empático para quem tem medo de altura. Mostrar progressão real de aluno com esse desafio.", legenda: "Medo de altura? Você não está sozinho. 🫶 A escalada, paradoxalmente, é uma das melhores formas de trabalhar esse medo com segurança e confiança.", image: "Vídeo progressivo: pé do chão → meio da parede → topo. Narração do aluno contando a experiência", tags: "#MedoDeAltura #ViacruxEscalada #SuperarMedos #EscaladaTerapeutica #ClimbingFear #Coragem #PrimeirosPasso" },
  { dia: 30, semana: "Sex", tipo: "foto", tema: "Encerramento de Maio: celebração do mês", copy: "Post de celebração do mês: conquistas coletivas dos alunos, highlights, agradecimento à comunidade.", legenda: "Maio foi INCRÍVEL na Via Crux! 🎉 Quantas primeiras vezes, quantas conquistas, quantas paredes superadas. Obrigado a cada um de vocês. Junho ainda vem mais forte!", image: "Collage ou foto de grupo dos alunos e instrutores, clima de celebração", tags: "#Maio2025 #ViacruxEscalada #FimDoMes #ComunidadeEscalada #ObrigadoAlunos #JunhoVemAi #EscaladaBrasil" },
  { dia: 31, semana: "Sáb", tipo: "carrossel", tema: "Reflexão: o que a escalada te ensinou?", copy: "Carrossel filosófico sobre as lições que a escalada transmite para a vida: paciência, persistência, confiança, humildade.", legenda: "A parede ensina o que a sala de aula não consegue. 🪨 Quais foram as maiores lições que a escalada te deu? Conta nos comentários!", image: "Slides minimalistas com frases e fotografias inspiradoras, paleta escura e sofisticada", tags: "#LicoesDeEscalada #EscaladaDeVida #ViacruxEscalada #FilosofiaEscalada #ClimbingLife #Persistencia #Conquista" }
];

const weekColors = { "Seg": "#4a90c4", "Ter": "#9b6bdb", "Qua": "#5aad62", "Qui": "#e8c05a", "Sex": "#d44a6a", "Sáb": "#c97c2a", "Dom": "#e05a5a" };

function buildCards() {
  const grid = document.getElementById('mainGrid');
  posts.forEach((p, i) => {
    const checked = localStorage.getItem('viacrux_' + p.dia) === '1';
    const div = document.createElement('div');
    div.className = 'card' + (checked ? ' done' : '');
    div.dataset.tipo = p.tipo;
    div.dataset.feito = checked ? '1' : '0';
    div.dataset.index = i;

    div.innerHTML = `
      <div class="card-top">
        <div class="day-badge">
          <div class="day-num">${p.dia}</div>
          <div class="day-week" style="color:${weekColors[p.semana]||'#888'}">${p.semana}</div>
        </div>
        <div class="card-type type-${p.tipo}">${p.tipo.toUpperCase()}</div>
      </div>
      <div class="card-theme">${p.tema}</div>
      <div class="card-copy">${p.copy}</div>
      <div class="card-image-hint"><span class="img-icon">🖼</span><span>${p.image}</span></div>
      <div class="check-row">
        <label class="check-label" onclick="toggleDone(${i}, event)">
          <div class="custom-check"><span class="checkmark">✓</span></div>
          <span class="check-text">${checked ? 'Publicado!' : 'Marcar como feito'}</span>
        </label>
        <button class="expand-btn" onclick="toggleExtra(${i}, event)">Ver mais ↓</button>
      </div>
      <div class="card-extra" id="extra-${i}">
        <div class="extra-section">
          <div class="extra-label">Legenda completa</div>
          <div class="extra-text">${p.legenda}</div>
        </div>
        <div class="extra-section">
          <div class="extra-label">Hashtags</div>
          <div class="extra-tags">${p.tags}</div>
        </div>
      </div>
    `;
    grid.appendChild(div);
  });
  updateStats();
}

function toggleDone(index, e) {
  e.stopPropagation();
  const p = posts[index];
  const card = document.querySelector(`[data-index="${index}"]`);
  const isDone = card.dataset.feito === '1';
  const newState = !isDone;
  card.dataset.feito = newState ? '1' : '0';
  card.className = 'card' + (newState ? ' done' : '');
  card.querySelector('.check-text').textContent = newState ? 'Publicado!' : 'Marcar como feito';
  localStorage.setItem('viacrux_' + p.dia, newState ? '1' : '0');
  updateStats();
}

function toggleExtra(index, e) {
  e.stopPropagation();
  const extra = document.getElementById('extra-' + index);
  const btn = e.target;
  if (extra.classList.contains('open')) {
    extra.classList.remove('open');
    btn.textContent = 'Ver mais ↓';
  } else {
    extra.classList.add('open');
    btn.textContent = 'Fechar ↑';
  }
}

function updateStats() {
  const cards = document.querySelectorAll('.card');
  let done = 0;
  cards.forEach(c => { if (c.dataset.feito === '1') done++; });
  const total = posts.length;
  const pct = Math.round((done / total) * 100);
  document.getElementById('statFeito').textContent = done;
  document.getElementById('statRestantes').textContent = total - done;
  document.getElementById('statPercent').textContent = pct + '%';
  document.getElementById('progressBar').style.width = pct + '%';
  document.getElementById('progressText').textContent = done + ' / ' + total + ' publicações';
}

function filterCards(type, btn) {
  document.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  document.querySelectorAll('.card').forEach(c => {
    let show = false;
    if (type === 'all') show = true;
    else if (type === 'pendente') show = c.dataset.feito === '0';
    else if (type === 'feito') show = c.dataset.feito === '1';
    else show = c.dataset.tipo === type;
    c.style.display = show ? '' : 'none';
  });
}

buildCards();
</script>
</body>
</html>
