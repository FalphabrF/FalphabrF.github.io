<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Qual Dev Python você seria? • Pyto Academy</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;700;800&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --p1: #1a0533;
    --p2: #2d0a5e;
    --p3: #4a1a8c;
    --p4: #6b35c4;
    --p5: #9b6de8;
    --p6: #c4a8f5;
    --p7: #ede4ff;
    --accent: #b84dff;
    --gold: #f5c842;
    --white: #faf8ff;
    --glass: rgba(107,53,196,0.15);
    --glass2: rgba(255,255,255,0.06);
  }
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--p1);
    color: var(--white);
    min-height: 100vh;
    overflow-x: hidden;
    position: relative;
  }

  /* Background animado */
  body::before {
    content: '';
    position: fixed; inset: 0;
    background:
      radial-gradient(ellipse 60% 50% at 20% 20%, rgba(107,53,196,0.4) 0%, transparent 60%),
      radial-gradient(ellipse 50% 40% at 80% 80%, rgba(184,77,255,0.25) 0%, transparent 55%),
      radial-gradient(ellipse 40% 60% at 50% 50%, rgba(45,10,94,0.6) 0%, transparent 70%);
    pointer-events: none; z-index: 0;
    animation: bgPulse 8s ease-in-out infinite alternate;
  }
  @keyframes bgPulse {
    from { opacity: 0.8; }
    to   { opacity: 1; }
  }

  /* Partículas */
  .particles {
    position: fixed; inset: 0; pointer-events: none; z-index: 0; overflow: hidden;
  }
  .particle {
    position: absolute; border-radius: 50%;
    background: var(--accent); opacity: 0;
    animation: float linear infinite;
  }
  @keyframes float {
    0%   { transform: translateY(110vh) scale(0); opacity: 0; }
    10%  { opacity: 0.4; }
    90%  { opacity: 0.15; }
    100% { transform: translateY(-10vh) scale(1); opacity: 0; }
  }

  .container {
    position: relative; z-index: 1;
    max-width: 680px; margin: 0 auto;
    padding: 40px 24px 80px;
  }

  /* Header */
  .logo {
    display: flex; align-items: center; gap: 10px;
    margin-bottom: 40px; justify-content: center;
  }
  .mascot {
    font-size: 32px;
    filter: drop-shadow(0 0 12px var(--accent));
    animation: wiggle 3s ease-in-out infinite;
  }
  @keyframes wiggle {
    0%,100% { transform: rotate(-5deg); }
    50%     { transform: rotate(5deg); }
  }
  .logo-text {
    font-family: 'Syne', sans-serif;
    font-size: 18px; font-weight: 800;
    letter-spacing: 0.04em;
    color: var(--p6);
  }

  /* Card principal */
  .card {
    background: var(--glass2);
    border: 1px solid rgba(155,109,232,0.2);
    border-radius: 24px;
    padding: 40px 36px;
    backdrop-filter: blur(20px);
    box-shadow: 0 0 60px rgba(107,53,196,0.2), inset 0 1px 0 rgba(255,255,255,0.08);
  }

  /* Tela de intro */
  #screen-intro { display: block; }
  .intro-badge {
    display: inline-block;
    font-size: 11px; font-weight: 500; letter-spacing: 0.1em; text-transform: uppercase;
    background: rgba(184,77,255,0.15);
    border: 1px solid rgba(184,77,255,0.3);
    color: var(--p6);
    padding: 6px 16px; border-radius: 100px;
    margin-bottom: 20px;
  }
  .intro-title {
    font-family: 'Syne', sans-serif;
    font-size: clamp(26px, 5vw, 40px);
    font-weight: 800; line-height: 1.1;
    margin-bottom: 16px;
  }
  .intro-title span { color: var(--accent); }
  .intro-desc {
    font-size: 15px; color: var(--p6); line-height: 1.7;
    margin-bottom: 32px;
  }
  .intro-bullets {
    display: flex; flex-direction: column; gap: 10px;
    margin-bottom: 36px;
  }
  .bullet {
    display: flex; align-items: center; gap: 12px;
    font-size: 14px; color: var(--p7);
  }
  .bullet-icon {
    width: 28px; height: 28px; border-radius: 8px; flex-shrink: 0;
    background: rgba(184,77,255,0.2);
    border: 1px solid rgba(184,77,255,0.3);
    display: flex; align-items: center; justify-content: center;
    font-size: 13px;
  }

  /* Botão principal */
  .btn-primary {
    width: 100%; padding: 18px;
    background: linear-gradient(135deg, var(--p4), var(--accent));
    border: none; border-radius: 14px;
    font-family: 'Syne', sans-serif;
    font-size: 16px; font-weight: 700;
    color: #fff; cursor: pointer;
    position: relative; overflow: hidden;
    transition: transform 0.15s, box-shadow 0.15s;
    box-shadow: 0 8px 32px rgba(184,77,255,0.35);
    letter-spacing: 0.02em;
  }
  .btn-primary::before {
    content: '';
    position: absolute; inset: 0;
    background: linear-gradient(135deg, transparent 40%, rgba(255,255,255,0.15));
  }
  .btn-primary:hover { transform: translateY(-2px); box-shadow: 0 12px 40px rgba(184,77,255,0.45); }
  .btn-primary:active { transform: translateY(0); }

  /* Progress bar */
  .progress-wrap { margin-bottom: 28px; }
  .progress-label {
    display: flex; justify-content: space-between; align-items: center;
    font-size: 12px; color: var(--p5); margin-bottom: 8px;
  }
  .progress-bar {
    height: 4px; background: rgba(155,109,232,0.2); border-radius: 2px; overflow: hidden;
  }
  .progress-fill {
    height: 100%; background: linear-gradient(90deg, var(--p4), var(--accent));
    border-radius: 2px; transition: width 0.5s cubic-bezier(.4,0,.2,1);
  }

  /* Quiz screen */
  #screen-quiz { display: none; }
  .q-number {
    font-size: 11px; font-weight: 500; letter-spacing: 0.12em; text-transform: uppercase;
    color: var(--p5); margin-bottom: 10px;
  }
  .q-text {
    font-family: 'Syne', sans-serif;
    font-size: clamp(18px, 3vw, 24px);
    font-weight: 700; line-height: 1.3;
    margin-bottom: 28px;
  }
  .options { display: flex; flex-direction: column; gap: 10px; }
  .option {
    padding: 16px 20px;
    background: var(--glass2);
    border: 1px solid rgba(155,109,232,0.2);
    border-radius: 14px;
    cursor: pointer; display: flex; align-items: flex-start; gap: 14px;
    transition: all 0.2s;
    font-size: 14px; line-height: 1.5; color: var(--p7);
  }
  .option:hover {
    background: rgba(107,53,196,0.25);
    border-color: rgba(155,109,232,0.5);
    transform: translateX(4px);
  }
  .option.selected {
    background: rgba(107,53,196,0.35);
    border-color: var(--p5);
    color: #fff;
  }
  .option-letter {
    width: 26px; height: 26px; border-radius: 8px; flex-shrink: 0;
    background: rgba(155,109,232,0.2); border: 1px solid rgba(155,109,232,0.3);
    display: flex; align-items: center; justify-content: center;
    font-family: 'Syne', sans-serif; font-size: 12px; font-weight: 700;
    color: var(--p5); transition: all 0.2s;
  }
  .option.selected .option-letter { background: var(--p4); border-color: var(--p5); color: #fff; }

  .btn-next {
    width: 100%; margin-top: 20px; padding: 16px;
    background: linear-gradient(135deg, var(--p4), var(--accent));
    border: none; border-radius: 14px;
    font-family: 'Syne', sans-serif; font-size: 15px; font-weight: 700;
    color: #fff; cursor: pointer;
    box-shadow: 0 6px 24px rgba(184,77,255,0.3);
    transition: all 0.2s; opacity: 0.4; pointer-events: none;
    letter-spacing: 0.02em;
  }
  .btn-next.active { opacity: 1; pointer-events: all; }
  .btn-next.active:hover { transform: translateY(-2px); box-shadow: 0 10px 32px rgba(184,77,255,0.4); }

  /* Resultado */
  #screen-result { display: none; }
  .result-header { text-align: center; margin-bottom: 28px; }
  .result-emoji {
    font-size: 56px; display: block; margin-bottom: 12px;
    filter: drop-shadow(0 0 20px var(--accent));
    animation: popIn 0.5s cubic-bezier(.17,.67,.35,1.4);
  }
  @keyframes popIn {
    from { transform: scale(0) rotate(-20deg); opacity: 0; }
    to   { transform: scale(1) rotate(0deg);   opacity: 1; }
  }
  .result-type {
    font-size: 11px; letter-spacing: 0.12em; text-transform: uppercase;
    color: var(--accent); margin-bottom: 8px; font-weight: 500;
  }
  .result-name {
    font-family: 'Syne', sans-serif;
    font-size: clamp(24px, 4vw, 32px); font-weight: 800; line-height: 1.2;
    margin-bottom: 14px;
  }
  .result-desc { font-size: 14px; color: var(--p6); line-height: 1.7; margin-bottom: 24px; }

  .result-skills {
    display: flex; flex-wrap: wrap; gap: 8px; justify-content: center;
    margin-bottom: 28px;
  }
  .skill-tag {
    font-size: 12px; padding: 5px 14px; border-radius: 100px;
    background: rgba(184,77,255,0.15); border: 1px solid rgba(184,77,255,0.3);
    color: var(--p6);
  }

  .result-box {
    background: rgba(184,77,255,0.08);
    border: 1px solid rgba(184,77,255,0.25);
    border-radius: 16px; padding: 20px 24px; margin-bottom: 24px;
  }
  .result-box-title {
    font-family: 'Syne', sans-serif; font-size: 13px; font-weight: 700;
    color: var(--p6); margin-bottom: 10px; letter-spacing: 0.04em;
  }
  .result-box p { font-size: 14px; color: var(--p7); line-height: 1.65; }

  .btn-cta {
    width: 100%; padding: 20px;
    background: linear-gradient(135deg, var(--p4), var(--accent));
    border: none; border-radius: 16px;
    font-family: 'Syne', sans-serif; font-size: 17px; font-weight: 800;
    color: #fff; cursor: pointer; text-decoration: none; display: block;
    text-align: center;
    box-shadow: 0 8px 40px rgba(184,77,255,0.4);
    transition: all 0.2s; position: relative; overflow: hidden;
    letter-spacing: 0.02em;
  }
  .btn-cta::before {
    content: ''; position: absolute; inset: 0;
    background: linear-gradient(135deg, transparent 40%, rgba(255,255,255,0.12));
  }
  .btn-cta:hover { transform: translateY(-3px); box-shadow: 0 14px 48px rgba(184,77,255,0.5); }
  .btn-cta-sub { font-size: 11px; font-weight: 400; opacity: 0.8; margin-top: 3px; display: block; }

  .social-proof {
    text-align: center; margin-top: 16px;
    font-size: 12px; color: var(--p5);
    display: flex; align-items: center; justify-content: center; gap: 6px;
  }

  /* Transições */
  .screen { transition: opacity 0.3s, transform 0.3s; }
  .screen.fade-out { opacity: 0; transform: translateY(10px); }

  @media (max-width: 480px) {
    .card { padding: 28px 20px; }
    .container { padding: 24px 16px 60px; }
  }
</style>
</head>
<body>

<div class="particles" id="particles"></div>

<div class="container">

  <div class="logo">
    <span class="mascot">🐙</span>
    <span class="logo-text">PYTO ACADEMY</span>
  </div>

  <!-- INTRO -->
  <div class="card screen" id="screen-intro">
    <div class="intro-badge">✦ Teste gratuito • 2 minutos</div>
    <h1 class="intro-title">
      Qual Dev Python<br>
      <span>você seria?</span>
    </h1>
    <p class="intro-desc">
      Responda 5 perguntas e descubra seu perfil — e qual caminho vai te levar mais longe em Python.
    </p>
    <div class="intro-bullets">
      <div class="bullet">
        <span class="bullet-icon">⚡</span>
        <span>100% gratuito, sem cadastro</span>
      </div>
      <div class="bullet">
        <span class="bullet-icon">🎯</span>
        <span>Resultado personalizado com seu perfil exato</span>
      </div>
      <div class="bullet">
        <span class="bullet-icon">🚀</span>
        <span>Plano de estudos recomendado no final</span>
      </div>
    </div>
    <button class="btn-primary" onclick="startQuiz()">
      Descobrir meu perfil →
    </button>
  </div>

  <!-- QUIZ -->
  <div class="card screen" id="screen-quiz">
    <div class="progress-wrap">
      <div class="progress-label">
        <span id="q-label">Pergunta 1 de 5</span>
        <span id="q-pct">0%</span>
      </div>
      <div class="progress-bar"><div class="progress-fill" id="progress-fill" style="width:0%"></div></div>
    </div>
    <div class="q-number" id="q-number">PERGUNTA 01</div>
    <div class="q-text" id="q-text"></div>
    <div class="options" id="options"></div>
    <button class="btn-next" id="btn-next" onclick="nextQuestion()">Próxima →</button>
  </div>

  <!-- RESULTADO -->
  <div class="card screen" id="screen-result">
    <div class="result-header">
      <span class="result-emoji" id="r-emoji"></span>
      <div class="result-type">Seu perfil Python é</div>
      <div class="result-name" id="r-name"></div>
      <p class="result-desc" id="r-desc"></p>
      <div class="result-skills" id="r-skills"></div>
    </div>
    <div class="result-box">
      <div class="result-box-title">🗺️ SEU PRÓXIMO PASSO</div>
      <p id="r-next"></p>
    </div>
    <a href="https://kiwify.com.br/SEU-LINK-AQUI" class="btn-cta" id="btn-cta" target="_blank">
      Ver meu plano completo →
      <span class="btn-cta-sub">Acesso imediato • Material do Pyto Academy</span>
    </a>
    <div class="social-proof">
      🔒 Garantia de 7 dias • Satisfação garantida
    </div>
  </div>

</div>

<script>
const questions = [
  {
    text: "Você tem um problema pra resolver. Qual é seu primeiro instinto?",
    options: [
      { text: "Automatizar tudo — se repete, a máquina faz", profile: "automator" },
      { text: "Analisar os dados por trás do problema", profile: "analyst" },
      { text: "Construir algo que outras pessoas possam usar", profile: "builder" },
      { text: "Entender o sistema inteiro antes de agir", profile: "architect" }
    ]
  },
  {
    text: "Qual dessas situações te deixa mais animado(a)?",
    options: [
      { text: "Criar um bot que faz algo chato por você 24h", profile: "automator" },
      { text: "Descobrir um padrão escondido num monte de dados", profile: "analyst" },
      { text: "Ver alguém usando algo que você criou", profile: "builder" },
      { text: "Fazer um código que ninguém mais conseguiria escrever", profile: "architect" }
    ]
  },
  {
    text: "Seu fim de semana livre. O que você faria com Python?",
    options: [
      { text: "Script que organiza meus arquivos automaticamente", profile: "automator" },
      { text: "Analisar dados de algo que tenho curiosidade", profile: "analyst" },
      { text: "Começar um projeto de app ou site novo", profile: "builder" },
      { text: "Estudar como funciona por dentro — algoritmos, estruturas", profile: "architect" }
    ]
  },
  {
    text: "Como você prefere aprender algo novo?",
    options: [
      { text: "Fazendo — erro, ajusto, funciona", profile: "automator" },
      { text: "Estudando exemplos reais com dados concretos", profile: "analyst" },
      { text: "Construindo um projeto do zero pra aprender", profile: "builder" },
      { text: "Entendendo a teoria antes de codar qualquer coisa", profile: "architect" }
    ]
  },
  {
    text: "Qual dessas frases mais combina com você?",
    options: [
      { text: "\"Tempo é dinheiro. Automatizar é obrigação.\"", profile: "automator" },
      { text: "\"Os dados nunca mentem — as pessoas é que interpretam errado.\"", profile: "analyst" },
      { text: "\"Uma boa ideia só vale se chegar nas pessoas.\"", profile: "builder" },
      { text: "\"Para construir bem, primeiro precisa entender fundo.\"", profile: "architect" }
    ]
  }
];

const results = {
  automator: {
    emoji: "⚡",
    name: "O Automatizador",
    desc: "Você pensa em eficiência acima de tudo. Tarefas repetitivas te irritam, e você tem o instinto certo: se uma máquina pode fazer, uma máquina vai fazer. Seu superpoder é transformar horas de trabalho manual em segundos de código.",
    skills: ["Web Scraping", "Selenium", "Scripts", "APIs", "Bots"],
    next: "Seu caminho ideal começa com automações práticas — scripts que resolvem problemas reais desde o primeiro dia. O Pyto Academy tem um módulo especialmente pensado para o seu perfil: do zero até criar bots e automações que você pode usar ou vender.",
    cta: "Quero começar automatizando →"
  },
  analyst: {
    emoji: "📊",
    name: "O Analista de Dados",
    desc: "Você enxerga padrões onde outros veem só números. Tem curiosidade genuína de entender o que está por trás dos fenômenos — e Python é exatamente a ferramenta que transforma essa curiosidade em insights concretos.",
    skills: ["Pandas", "Matplotlib", "NumPy", "Jupyter", "Machine Learning"],
    next: "Sua jornada começa com análise de dados reais — desde carregar uma planilha até criar visualizações impressionantes. O Pyto Academy te leva do básico do Python direto para o mundo dos dados, com projetos baseados em situações do mundo real.",
    cta: "Quero dominar dados →"
  },
  builder: {
    emoji: "🚀",
    name: "O Construtor",
    desc: "Você pensa em produto. Não quer só fazer código funcionar — quer que as pessoas usem e se beneficiem do que você cria. Esse mindset é raro e valioso: é o que diferencia um dev comum de um criador de soluções.",
    skills: ["Flask", "Django", "APIs REST", "Deploy", "Projetos reais"],
    next: "Seu foco deve ser ir rápido do zero para algo funcionando — APIs, apps, projetos que você pode mostrar. O Pyto Academy tem um trilha focada em construção de projetos reais que você pode adicionar ao portfólio desde as primeiras semanas.",
    cta: "Quero construir projetos reais →"
  },
  architect: {
    emoji: "🧠",
    name: "O Arquiteto",
    desc: "Você precisa entender o fundo das coisas. Antes de usar, quer saber como funciona. Esse rigor te torna o tipo de desenvolvedor que resolve problemas que ninguém mais consegue — porque você entende o que está acontecendo de verdade.",
    skills: ["Algoritmos", "POO", "Design Patterns", "Performance", "CS Fundamentals"],
    next: "Sua base precisa ser sólida antes de tudo. O Pyto Academy tem uma trilha que vai dos fundamentos reais de Python — lógica, estruturas, orientação a objetos — até projetos avançados que testam seu raciocínio de verdade.",
    cta: "Quero aprender da forma certa →"
  }
};

let current = 0;
let answers = [];
let selectedOption = null;

function createParticles() {
  const container = document.getElementById('particles');
  for (let i = 0; i < 18; i++) {
    const p = document.createElement('div');
    p.className = 'particle';
    const size = Math.random() * 4 + 1;
    p.style.cssText = `
      width:${size}px; height:${size}px;
      left:${Math.random()*100}%;
      animation-duration:${8 + Math.random()*12}s;
      animation-delay:${Math.random()*10}s;
      opacity:0;
    `;
    container.appendChild(p);
  }
}

function switchScreen(hideId, showId) {
  const hide = document.getElementById(hideId);
  const show = document.getElementById(showId);
  hide.classList.add('fade-out');
  setTimeout(() => {
    hide.style.display = 'none';
    hide.classList.remove('fade-out');
    show.style.display = 'block';
    show.style.opacity = 0;
    show.style.transform = 'translateY(16px)';
    requestAnimationFrame(() => {
      show.style.transition = 'opacity 0.35s, transform 0.35s';
      show.style.opacity = 1;
      show.style.transform = 'translateY(0)';
    });
  }, 280);
}

function startQuiz() {
  switchScreen('screen-intro', 'screen-quiz');
  renderQuestion();
}

function renderQuestion() {
  const q = questions[current];
  selectedOption = null;
  document.getElementById('q-label').textContent = `Pergunta ${current + 1} de ${questions.length}`;
  document.getElementById('q-pct').textContent = `${Math.round((current / questions.length) * 100)}%`;
  document.getElementById('progress-fill').style.width = `${(current / questions.length) * 100}%`;
  document.getElementById('q-number').textContent = `PERGUNTA ${String(current + 1).padStart(2, '0')}`;
  document.getElementById('q-text').textContent = q.text;
  const letters = ['A', 'B', 'C', 'D'];
  document.getElementById('options').innerHTML = q.options.map((opt, i) => `
    <div class="option" onclick="selectOption(this, '${opt.profile}')">
      <span class="option-letter">${letters[i]}</span>
      <span>${opt.text}</span>
    </div>
  `).join('');
  const btn = document.getElementById('btn-next');
  btn.classList.remove('active');
  btn.textContent = current === questions.length - 1 ? 'Ver meu resultado →' : 'Próxima →';
}

function selectOption(el, profile) {
  document.querySelectorAll('.option').forEach(o => o.classList.remove('selected'));
  el.classList.add('selected');
  selectedOption = profile;
  document.getElementById('btn-next').classList.add('active');
}

function nextQuestion() {
  if (!selectedOption) return;
  answers.push(selectedOption);
  if (current < questions.length - 1) {
    current++;
    // Fade sutil nas opções
    const opts = document.getElementById('options');
    opts.style.opacity = 0;
    opts.style.transition = 'opacity 0.2s';
    setTimeout(() => {
      renderQuestion();
      opts.style.opacity = 1;
    }, 200);
  } else {
    showResult();
  }
}

function showResult() {
  // Conta qual perfil ganhou
  const count = {};
  answers.forEach(a => count[a] = (count[a] || 0) + 1);
  const winner = Object.entries(count).sort((a, b) => b[1] - a[1])[0][0];
  const r = results[winner];

  document.getElementById('r-emoji').textContent = r.emoji;
  document.getElementById('r-name').textContent = r.name;
  document.getElementById('r-desc').textContent = r.desc;
  document.getElementById('r-next').textContent = r.next;
  document.getElementById('r-skills').innerHTML = r.skills.map(s =>
    `<span class="skill-tag">${s}</span>`
  ).join('');

  const ctaBtn = document.getElementById('btn-cta');
  ctaBtn.childNodes[0].textContent = r.cta + ' ';

  // Progresso cheio
  document.getElementById('progress-fill').style.width = '100%';

  switchScreen('screen-quiz', 'screen-result');
}

createParticles();
</script>
</body>
</html>
