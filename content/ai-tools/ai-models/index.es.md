---
title: "Más allá del modelo de IA por defecto: una guía de campo para el nuevo panorama de la IA"
date: 2026-05-27
description: "Una guía de campo interactiva sobre el panorama moderno de la IA, que explica por qué depender de un solo modelo es una limitación de flujo de trabajo y mapea laboratorios clave, modelos e interfaces."
tags: ["IA", "modelos", "flujo-de-trabajo"]
---

Los modelos de IA están evolucionando a un ritmo que es genuinamente difícil de seguir. Cada pocas semanas, un nuevo modelo lidera un benchmark, se lanza una nueva interfaz y la opción que antes era la "mejor" se hace a un lado silenciosamente. Más importante aún, diferentes modelos ahora sobresalen en tareas muy distintas (escritura, programación, matemáticas, generación de imágenes, eficiencia de costos), lo que significa que depender de un solo modelo es cada vez más una limitación y no un flujo de trabajo.

Para navegar esto de manera efectiva, vale la pena mantener claras tres distinciones: la empresa matriz, el modelo en sí y la interfaz que usas para interactuar con él. Son tres cosas separadas que reciben nombres diferentes y que a menudo se confunden, lo que crea una confusión innecesaria. Una empresa como Anthropic construye modelos como Sonnet y Opus, a los que puedes acceder a través de [claude.ai](https://claude.ai), la aplicación de escritorio o Claude Code en la terminal. La misma lógica se aplica en todos los ámbitos. Tener este panorama claro es el primer paso para usar la IA de manera deliberada en lugar de por costumbre.

Una tendencia a la que vale la pena prestar atención: en los últimos meses, los ingenieros y emprendedores en los EE. UU. se han estado inclinando silenciosamente hacia modelos más ligeros y eficientes en costos —muchos de ellos chinos— en lugar de usar por defecto las opciones insignia estadounidenses. Esto es reciente, se está acelerando y cambia el cálculo de a qué deberías tener acceso.

Si quieres un primer acercamiento a los modelos no tradicionales, sugeriría comenzar con OpenCode (no estoy patrocinado por ellos ni nada por el estilo) que es un agente que se ejecuta en la terminal con una TUI (interfaz de usuario de texto) limpia, pero que también tiene versiones web y de escritorio disponibles. Se conecta a una amplia gama de modelos desde una sola interfaz, lo que creo que es actualmente la forma más práctica de consolidar tu acceso y comenzar a experimentar.

La tabla a continuación es mi intento de darte una instantánea clara del panorama actual de la IA: quién construye qué, por qué es más conocido cada modelo y dónde puedes usarlo realmente.

Me causa una curiosidad genuina saber qué combinaciones te han funcionado. [patricio@pperezh.com](mailto:patricio@pperezh.com).

---

<!-- Estilos específicos para la página web en vivo dentro del tema Blowfish de Hugo -->
<style>
  .ai-models-wrapper {
    --bg: #0d0f14;
    --surface: #141720;
    --border: #1e2330;
    --border-light: #252b3a;
    --accent: #5b8ef0;
    --gold: #e2b96a;
    --text-primary: #eef0f5;
    --text-secondary: #7a8299;
    --text-muted: #4a5168;
    --anthropic: #d97e6a;
    --openai: #74c69d;
    --google: #7ab3f5;
    --xai: #b07ef5;
    --deepseek: #5bcfcf;
    --zai: #f5a76b;
    --baidu: #f07090;

    font-family: 'DM Sans', -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
    background: var(--bg);
    color: var(--text-primary);
    padding: 32px 24px;
    border-radius: 12px;
    margin: 32px auto;
    box-shadow: 0 10px 40px rgba(0,0,0,0.5);
    border: 1px solid var(--border);
    max-width: 100%;
    overflow: hidden;
  }

  .ai-models-wrapper * { box-sizing: border-box; margin: 0; padding: 0; }

  .ai-models-wrapper header { margin-bottom: 40px; animation: aiFadeUp 0.6s ease both; }

  .ai-models-wrapper .eyebrow {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 10px;
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .ai-models-wrapper .eyebrow::before { content: ''; display: inline-block; width: 20px; height: 1px; background: var(--accent); }

  .ai-models-wrapper h1.table-title {
    font-family: 'DM Serif Display', Georgia, serif;
    font-size: clamp(24px, 4vw, 36px);
    font-weight: 400;
    line-height: 1.15;
    margin-bottom: 8px;
    color: var(--text-primary);
    border: none;
    padding: 0;
  }
  .ai-models-wrapper h1.table-title em { font-style: italic; color: var(--gold); }

  .ai-models-wrapper .subtitle { font-size: 14px; color: var(--text-secondary); font-weight: 300; }

  .ai-models-wrapper .toolbar {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-top: 16px;
  }

  .ai-models-wrapper .edit-hint {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--text-muted);
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 5px 10px;
  }

  .ai-models-wrapper .download-btn {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--accent);
    background: rgba(91,142,240,0.1);
    border: 1px solid rgba(91,142,240,0.3);
    border-radius: 4px;
    padding: 5px 12px;
    cursor: pointer;
    transition: background 0.2s, border-color 0.2s;
    user-select: none;
  }
  .ai-models-wrapper .download-btn:hover { background: rgba(91,142,240,0.2); border-color: rgba(91,142,240,0.5); }

  .ai-models-wrapper .table-wrap {
    border: 1px solid var(--border);
    border-radius: 12px;
    overflow: hidden;
    background: var(--surface);
    animation: aiFadeUp 0.7s 0.1s ease both;
    box-shadow: 0 0 60px rgba(0,0,0,0.4);
    margin-top: 24px;
  }

  .ai-models-wrapper table { width: 100%; border-collapse: collapse; table-layout: fixed; }

  .ai-models-wrapper col.col-company { width: 13%; }
  .ai-models-wrapper col.col-models  { width: 19%; }
  .ai-models-wrapper col.col-best    { width: 16%; }
  .ai-models-wrapper col.col-iface   { width: 23%; }
  .ai-models-wrapper col.col-excels  { width: 29%; }

  .ai-models-wrapper thead tr { background: var(--bg); border-bottom: 1px solid var(--border-light); }
  .ai-models-wrapper thead th {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: var(--text-muted);
    padding: 14px 16px;
    text-align: left;
    font-weight: 500;
  }

  .ai-models-wrapper tbody tr { border-bottom: 1px solid var(--border); transition: background 0.2s; }
  .ai-models-wrapper tbody tr:last-child { border-bottom: none; }
  .ai-models-wrapper tbody tr:hover { background: rgba(255,255,255,0.025); }

  .ai-models-wrapper td { padding: 0; vertical-align: top; }

  .ai-models-wrapper .cell { padding: 12px 14px; min-height: 50px; }

  .ai-models-wrapper .company-cell { display: flex; flex-direction: row; align-items: center; gap: 7px; height: 100%; }
  .ai-models-wrapper .company-dot { width: 7px; height: 7px; border-radius: 50%; flex-shrink: 0; }
  .ai-models-wrapper .company-name { font-weight: 500; font-size: 13px; color: var(--text-primary); outline: none; white-space: nowrap; }
  .ai-models-wrapper .company-name:focus { text-decoration: underline; text-decoration-style: dotted; }

  .ai-models-wrapper .models-list { display: flex; flex-direction: column; gap: 3px; }
  .ai-models-wrapper .model-tag {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--text-secondary);
    background: rgba(255,255,255,0.04);
    border: 1px solid var(--border-light);
    border-radius: 4px;
    padding: 2px 7px;
    display: inline-block;
    width: fit-content;
    outline: none;
    cursor: text;
    transition: border-color 0.2s, color 0.2s;
  }
  .ai-models-wrapper .model-tag:focus { border-color: var(--accent); color: var(--text-primary); }

  .ai-models-wrapper .best-name {
    font-family: 'DM Serif Display', Georgia, serif;
    font-size: 13px;
    font-style: italic;
    color: var(--gold);
    outline: none;
    cursor: text;
  }

  .ai-models-wrapper .iface-list { display: flex; flex-direction: column; gap: 4px; }
  .ai-models-wrapper .iface-row { display: flex; align-items: center; gap: 6px; }
  .ai-models-wrapper .iface-badge {
    font-family: 'DM Mono', monospace;
    font-size: 9px;
    padding: 1px 5px;
    border-radius: 3px;
    font-weight: 500;
    flex-shrink: 0;
    text-transform: uppercase;
    letter-spacing: 0.04em;
    min-width: 42px;
    text-align: center;
  }
  .ai-models-wrapper .badge-web  { background: rgba(91,142,240,0.15); color: #7aaaf7; }
  .ai-models-wrapper .badge-desk { background: rgba(116,198,157,0.15); color: #74c69d; }
  .ai-models-wrapper .badge-ide  { background: rgba(226,185,106,0.15); color: #e2b96a; }
  .ai-models-wrapper .badge-cli  { background: rgba(176,126,245,0.15); color: #c4a0f7; }

  .ai-models-wrapper .iface-detail {
    font-size: 11px;
    color: var(--text-secondary);
    outline: none;
    cursor: text;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
  }
  .ai-models-wrapper .iface-detail:focus { color: var(--text-primary); white-space: normal; }

  .ai-models-wrapper .excels-text { font-size: 13px; color: var(--text-secondary); line-height: 1.5; outline: none; cursor: text; }
  .ai-models-wrapper .excels-text:focus { color: var(--text-primary); }

  .ai-models-wrapper .note {
    display: block;
    margin-top: 5px;
    font-size: 11px;
    font-family: 'DM Mono', monospace;
    color: var(--text-muted);
    border-left: 2px solid var(--border-light);
    padding-left: 7px;
    outline: none;
    cursor: text;
  }
  .ai-models-wrapper .note:focus { color: var(--text-secondary); border-left-color: var(--accent); }

  .ai-models-wrapper .asterisk { color: var(--baidu); font-size: 14px; font-weight: bold; margin-left: 2px; }

  .ai-models-wrapper .asterisk-note {
    margin-top: 14px;
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--text-muted);
  }
  .ai-models-wrapper .asterisk-note span { color: var(--baidu); }

  .ai-models-wrapper tr[data-company="anthropic"] td:first-child { box-shadow: inset 3px 0 0 var(--anthropic); }
  .ai-models-wrapper tr[data-company="openai"]    td:first-child { box-shadow: inset 3px 0 0 var(--openai); }
  .ai-models-wrapper tr[data-company="google"]    td:first-child { box-shadow: inset 3px 0 0 var(--google); }
  .ai-models-wrapper tr[data-company="xai"]       td:first-child { box-shadow: inset 3px 0 0 var(--xai); }
  .ai-models-wrapper tr[data-company="deepseek"]  td:first-child { box-shadow: inset 3px 0 0 var(--deepseek); }
  .ai-models-wrapper tr[data-company="zai"]       td:first-child { box-shadow: inset 3px 0 0 var(--zai); }
  .ai-models-wrapper tr[data-company="baidu"]     td:first-child { box-shadow: inset 3px 0 0 var(--baidu); }

  .ai-models-wrapper .dot-anthropic { background: var(--anthropic); }
  .ai-models-wrapper .dot-openai    { background: var(--openai); }
  .ai-models-wrapper .dot-google    { background: var(--google); }
  .ai-models-wrapper .dot-xai       { background: var(--xai); }
  .ai-models-wrapper .dot-deepseek  { background: var(--deepseek); }
  .ai-models-wrapper .dot-zai       { background: var(--zai); }
  .ai-models-wrapper .dot-baidu     { background: var(--baidu); }

  @keyframes aiFadeUp {
    from { opacity: 0; transform: translateY(12px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  @media (max-width: 768px) {
    .ai-models-wrapper .table-wrap { overflow-x: auto; }
    .ai-models-wrapper table { min-width: 720px; }
  }
</style>



<!-- Contenedor exterior del widget con temática oscura -->
<div class="ai-models-wrapper">
<!-- Contenido de la página que se clona y exporta al hacer clic en Descargar -->
<div id="ai-models-page" class="ai-models-page">
<header>
<div class="eyebrow">Panorama de la IA</div>
<h1 class="table-title">Los modelos que vale la pena conocer<br><em>Mayo 2026</em></h1>
<p class="subtitle">Una guía de campo sobre quién construye qué y dónde brilla realmente cada laboratorio.</p>
</header>

<div class="table-wrap">
<table>
<colgroup>
<col class="col-company">
<col class="col-models">
<col class="col-best">
<col class="col-iface">
<col class="col-excels">
</colgroup>
<thead>
<tr>
<th>Empresa</th>
<th>Modelos</th>
<th>Mejor versión</th>
<th>Interfaz</th>
<th>Sobresale en</th>
</tr>
</thead>
<tbody>
<!-- ANTHROPIC -->
<tr data-company="anthropic">
<td><div class="cell company-cell">
<div class="company-dot dot-anthropic"></div>
<span class="company-name">Anthropic</span>
</div></td>
<td><div class="cell">
<div class="models-list">
<span class="model-tag">Haiku 4.5</span>
<span class="model-tag">Sonnet 4.6</span>
<span class="model-tag">Opus 4.7</span>
</div>
</div></td>
<td><div class="cell">
<span class="best-name">Claude Opus 4.7</span>
</div></td>
<td><div class="cell">
<div class="iface-list">
<div class="iface-row"><span class="iface-badge badge-web">Web</span><span class="iface-detail">claude.ai</span></div>
<div class="iface-row"><span class="iface-badge badge-desk">Escritorio</span><span class="iface-detail">Claude Desktop</span></div>
<div class="iface-row"><span class="iface-badge badge-cli">Terminal</span><span class="iface-detail">Claude Code</span></div>
</div>
</div></td>
<td><div class="cell">
<span class="excels-text">Escritura, programación<br><span style="color: rgb(122, 130, 153); font-family: 'DM Mono', monospace; font-size: 11px;">⭐ El que uso para tareas de escritura</span></span>
</div></td>
</tr>

<!-- OPENAI -->
<tr data-company="openai">
<td><div class="cell company-cell">
<div class="company-dot dot-openai"></div>
<span class="company-name">OpenAI</span>
</div></td>
<td><div class="cell">
<div class="models-list">
<span class="model-tag">GPT-4o</span>
<span class="model-tag">GPT-5</span>
<span class="model-tag">GPT-5.5</span>
</div>
</div></td>
<td><div class="cell">
<span class="best-name">GPT-5.5</span>
</div></td>
<td><div class="cell">
<div class="iface-list">
<div class="iface-row"><span class="iface-badge badge-web">Web</span><span class="iface-detail">ChatGPT.com</span></div>
<div class="iface-row"><span class="iface-badge badge-desk">Escritorio</span><span class="iface-detail">Codex IDE</span></div>
<div class="iface-row"><span class="iface-badge badge-cli">Terminal</span><span class="iface-detail">OpenAI CLI</span></div>
</div>
</div></td>
<td><div class="cell">
<span class="excels-text">Matemáticas, física, imágenes</span>
</div></td>
</tr>

<!-- GOOGLE -->
<tr data-company="google">
<td><div class="cell company-cell">
<div class="company-dot dot-google"></div>
<span class="company-name">Google</span>
</div></td>
<td><div class="cell">
<div class="models-list">
<span class="model-tag">Gemini Flash</span>
<span class="model-tag">Gemini Pro</span>
<span class="model-tag">Gemini 3.1 Pro</span>
</div>
</div></td>
<td><div class="cell">
<span class="best-name">Gemini 3.1 Pro</span>
</div></td>
<td><div class="cell">
<div class="iface-list">
<div class="iface-row"><span class="iface-badge badge-web">Web</span><span class="iface-detail">gemini.google.com</span></div>
<div class="iface-row"><span class="iface-badge badge-desk">Escritorio</span><span class="iface-detail">Antigravity 2.0</span></div>
<div class="iface-row"><span class="iface-badge badge-ide">IDE</span><span class="iface-detail">Antigravity IDE</span></div>
<div class="iface-row"><span class="iface-badge badge-cli">Terminal</span><span class="iface-detail">Antigravity CLI</span></div>
</div>
</div></td>
<td><div class="cell">
<span class="excels-text">Imágenes, multimodal, ciencia</span>
</div></td>
</tr>

<!-- XAI -->
<tr data-company="xai">
<td><div class="cell company-cell">
<div class="company-dot dot-xai"></div>
<span class="company-name">xAI</span>
</div></td>
<td><div class="cell">
<div class="models-list">
<span class="model-tag">Grok 4</span>
<span class="model-tag">Grok 4 Fast</span>
</div>
</div></td>
<td><div class="cell">
<span class="best-name">Grok 4</span>
</div></td>
<td><div class="cell">
<div class="iface-list">
<div class="iface-row"><span class="iface-badge badge-web">Web</span><span class="iface-detail">x.ai/grok</span></div>
<div class="iface-row"><span class="iface-badge badge-desk">Escritorio</span><span class="iface-detail">X Desktop App</span></div>
<div class="iface-row"><span class="iface-badge badge-cli">Terminal</span><span class="iface-detail">xAI API</span></div>
</div>
</div></td>
<td><div class="cell">
<span class="excels-text">Noticias en tiempo real, contexto largo</span>
</div></td>
</tr>

<!-- DEEPSEEK -->
<tr data-company="deepseek">
<td><div class="cell company-cell">
<div class="company-dot dot-deepseek"></div>
<span class="company-name">DeepSeek</span>
</div></td>
<td><div class="cell">
<div class="models-list">
<span class="model-tag">V4 Flash</span>
<span class="model-tag">V4 Pro</span>
<span class="model-tag">R1</span>
</div>
</div></td>
<td><div class="cell">
<span class="best-name">DeepSeek V4 Pro</span>
</div></td>
<td><div class="cell">
<div class="iface-list">
<div class="iface-row"><span class="iface-badge badge-web">Web</span><span class="iface-detail">chat.deepseek.com</span></div>
<div class="iface-row"><span class="iface-badge badge-desk">Escritorio</span><span class="iface-detail">DeepSeek App</span></div>
<div class="iface-row"><span class="iface-badge badge-cli">Terminal</span><span class="iface-detail">DeepSeek API</span></div>
</div>
</div></td>
<td><div class="cell">
<span class="excels-text">Eficiente en costos</span>
</div></td>
</tr>

<!-- ZHIPU -->
<tr data-company="zai">
<td><div class="cell company-cell">
<div class="company-dot dot-zai"></div>
<span class="company-name">z.AI</span>
</div></td>
<td><div class="cell">
<div class="models-list">
<span class="model-tag">GLM-4.6</span>
<span class="model-tag">GLM-5</span>
<span class="model-tag">GLM-5.1</span>
</div>
</div></td>
<td><div class="cell">
<span class="best-name">GLM-5.1</span>
</div></td>
<td><div class="cell">
<div class="iface-list">
<div class="iface-row"><span class="iface-badge badge-web">Web</span><span class="iface-detail">chatglm.cn</span></div>
<div class="iface-row"><span class="iface-badge badge-desk">Escritorio</span><span class="iface-detail">—</span></div>
<div class="iface-row"><span class="iface-badge badge-cli">Terminal</span><span class="iface-detail">Z.AI API</span></div>
</div>
</div></td>
<td><div class="cell">
<span class="excels-text">Eficiente en costos</span>
<span class="note">⭐ El que uso para tareas baratas</span>
</div></td>
</tr>

<!-- BAIDU -->
<tr data-company="baidu">
<td><div class="cell company-cell">
<div class="company-dot dot-baidu"></div>
<span class="company-name">Baidu</span>
</div></td>
<td><div class="cell">
<div class="models-list">
<span class="model-tag">ERNIE 5.0</span>
<span class="model-tag">ERNIE 5.1</span>
</div>
</div></td>
<td><div class="cell">
<span class="best-name">ERNIE 5.1<span class="asterisk">*</span></span>
</div></td>
<td><div class="cell">
<div class="iface-list">
<div class="iface-row"><span class="iface-badge badge-web">Web</span><span class="iface-detail">ernie.baidu.com</span></div>
<div class="iface-row"><span class="iface-badge badge-desk">Escritorio</span><span class="iface-detail">—</span></div>
<div class="iface-row"><span class="iface-badge badge-cli">Terminal</span><span class="iface-detail">Baidu Qianfan API</span></div>
</div>
</div></td>
<td><div class="cell">
<span class="excels-text">Eficiente en costos</span>
</div></td>
</tr>
</tbody>
</table>
</div>

<p class="asterisk-note"><span>*</span> Lanzamiento reciente — ya es el mejor modelo chino en las tablas de clasificación globales.</p>
</div>
</div>


