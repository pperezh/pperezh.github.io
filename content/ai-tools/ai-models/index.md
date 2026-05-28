---
title: "Beyond the Default AI Model: A Field Guide to the New AI Landscape"
date: 2026-05-27
description: "An interactive field guide to the modern AI landscape, outlining why relying on a single model is a workflow limitation and mapping out key labs, models, and interfaces."
tags: ["AI", "models", "workflow"]
---

AI models are evolving at a pace that is genuinely hard to keep up with. Every few weeks, a new model tops a benchmark, a new interface ships, and the previous "best option" quietly steps aside. More importantly, different models are now excelling at very different tasks, writing, coding, math, image generation, cost efficiency, which means that relying on a single model is increasingly a limitation, not a workflow.

To navigate this effectively, there are three things worth keeping distinct: the parent company, the model itself, and the interface you use to interact with it. These are three separate things that receive different names and are often conflated, which creates unnecessary confusion. A company like Anthropic builds models like Sonnet and Opus, which you can access through [claude.ai](https://claude.ai), the desktop app, or Claude Code in the terminal. Same logic applies across the board. Getting this picture clear is the first step toward using AI deliberately rather than by habit.

One trend worth paying attention to: over the last few months, engineers and entrepreneurs in the US have been quietly shifting toward leaner, more cost-efficient models (many of them Chinese) rather than defaulting to the flagship US options. This is recent, it is accelerating, and it changes the calculus of what you should have access to.

If you want a first approach to non-traditional models, I would suggest starting with OpenCode (I'm not sponsored by them or anything) an agent that runs in the terminal with a clean TUI, but also has desktop and web versions available. It connects to a wide range of models from a single interface, which I think is currently the most practical way to consolidate your access and start experimenting.

The table below is my attempt to give you a clear snapshot of the current AI landscape: who builds what, what each model is best known for, and where you can actually use it.

I am genuinely curious what combinations have worked for you. [patricio@pperezh.com](mailto:patricio@pperezh.com).

---

<!-- Scoped styling for the live web page inside the Hugo Blowfish theme -->
<style>
  .ai-models-wrapper {
    --border: #e5e7eb;
    --border-light: #f3f4f6;
    --accent: #2563eb;
    --gold: #d97706;
    --text-primary: #1f2937;
    --text-secondary: #4b5563;
    --text-muted: #9ca3af;
    --anthropic: #d97e6a;
    --openai: #10b981;
    --google: #3b82f6;
    --xai: #8b5cf6;
    --deepseek: #06b6d4;
    --zai: #f59e0b;
    --baidu: #ec4899;

    color: var(--text-primary);
    padding: 0;
    margin: 2rem 0;
    max-width: 100%;
    overflow: hidden;
  }

  .dark .ai-models-wrapper {
    --border: #374151;
    --border-light: #1f2937;
    --accent: #60a5fa;
    --gold: #f59e0b;
    --text-primary: #f3f4f6;
    --text-secondary: #9ca3af;
    --text-muted: #6b7280;
  }

  .ai-models-wrapper * { box-sizing: border-box; margin: 0; padding: 0; }

  /* Reset default Blowfish/Tailwind theme table backgrounds and borders */
  .ai-models-wrapper table,
  .ai-models-wrapper thead,
  .ai-models-wrapper tbody,
  .ai-models-wrapper tr,
  .ai-models-wrapper th,
  .ai-models-wrapper td {
    background: transparent !important;
    background-color: transparent !important;
    border: none !important;
    box-shadow: none !important;
  }

  .ai-models-wrapper header { margin-bottom: 2rem; }

  .ai-models-wrapper .eyebrow {
    font-size: 11px;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--accent) !important;
    margin-bottom: 10px;
    display: flex;
    align-items: center;
    gap: 8px;
    font-weight: 600;
  }
  .ai-models-wrapper .eyebrow::before { content: ''; display: inline-block; width: 20px; height: 1px; background: var(--accent); }

  .ai-models-wrapper h1.table-title {
    font-size: clamp(24px, 4vw, 32px);
    font-weight: 700;
    line-height: 1.2;
    margin-bottom: 8px;
    color: var(--text-primary) !important;
    border: none !important;
    padding: 0 !important;
    background: transparent !important;
  }
  .ai-models-wrapper h1.table-title em { font-style: italic; color: var(--gold) !important; }

  .ai-models-wrapper .subtitle { font-size: 14px; color: var(--text-secondary) !important; font-weight: 400; }

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
    font-size: 11px;
    color: var(--text-muted) !important;
    background: transparent !important;
    border: 1px solid var(--border) !important;
    border-radius: 4px;
    padding: 5px 10px;
  }

  .ai-models-wrapper .download-btn {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-size: 11px;
    color: var(--accent) !important;
    background: rgba(37, 99, 235, 0.08) !important;
    border: 1px solid rgba(37, 99, 235, 0.2) !important;
    border-radius: 4px;
    padding: 5px 12px;
    cursor: pointer;
    transition: background 0.2s, border-color 0.2s;
    user-select: none;
    font-weight: 500;
  }
  .ai-models-wrapper .download-btn:hover { background: rgba(37, 99, 235, 0.15) !important; border-color: rgba(37, 99, 235, 0.4) !important; }

  .dark .ai-models-wrapper .download-btn {
    background: rgba(96, 165, 250, 0.08) !important;
    border: 1px solid rgba(96, 165, 250, 0.2) !important;
  }
  .dark .ai-models-wrapper .download-btn:hover { background: rgba(96, 165, 250, 0.15) !important; border-color: rgba(96, 165, 250, 0.4) !important; }

  .ai-models-wrapper .table-wrap {
    border: 1px solid var(--border) !important;
    border-radius: 8px;
    overflow: hidden;
    background: transparent !important;
    margin-top: 24px;
  }

  .ai-models-wrapper table { width: 100%; border-collapse: collapse; table-layout: fixed; }

  .ai-models-wrapper col.col-company { width: 13%; }
  .ai-models-wrapper col.col-models  { width: 19%; }
  .ai-models-wrapper col.col-best    { width: 16%; }
  .ai-models-wrapper col.col-iface   { width: 23%; }
  .ai-models-wrapper col.col-excels  { width: 29%; }

  .ai-models-wrapper thead tr { border-bottom: 1px solid var(--border) !important; }
  .ai-models-wrapper thead th {
    font-size: 10px;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: var(--text-muted) !important;
    padding: 14px 16px;
    text-align: left;
    font-weight: 600;
  }

  .ai-models-wrapper tbody tr { border-bottom: 1px solid var(--border) !important; }
  .ai-models-wrapper tbody tr:last-child { border-bottom: none !important; }

  .ai-models-wrapper tbody tr:hover td { background: rgba(0, 0, 0, 0.015) !important; }
  .dark .ai-models-wrapper tbody tr:hover td { background: rgba(255, 255, 255, 0.015) !important; }

  .ai-models-wrapper td { padding: 0; vertical-align: top; }

  .ai-models-wrapper .cell { padding: 12px 14px; min-height: 50px; }

  .ai-models-wrapper .company-cell { display: flex; flex-direction: row; align-items: center; gap: 7px; height: 100%; }
  .ai-models-wrapper .company-dot { width: 7px; height: 7px; border-radius: 50%; flex-shrink: 0; }
  .ai-models-wrapper .company-name { font-weight: 600; font-size: 13px; color: var(--text-primary) !important; outline: none; white-space: nowrap; }
  .ai-models-wrapper .company-name:focus { text-decoration: underline; text-decoration-style: dotted; }

  .ai-models-wrapper .models-list { display: flex; flex-direction: column; gap: 3px; }
  .ai-models-wrapper .model-tag {
    font-size: 11px;
    color: var(--text-secondary) !important;
    background: rgba(0,0,0,0.03) !important;
    border: 1px solid var(--border-light) !important;
    border-radius: 4px;
    padding: 2px 7px;
    display: inline-block;
    width: fit-content;
    outline: none;
    cursor: text;
    transition: border-color 0.2s, color 0.2s;
  }
  .dark .ai-models-wrapper .model-tag { background: rgba(255,255,255,0.04) !important; }
  .ai-models-wrapper .model-tag:focus { border-color: var(--accent) !important; color: var(--text-primary) !important; }

  .ai-models-wrapper .best-name {
    font-size: 13px;
    font-weight: 600;
    color: var(--gold) !important;
    outline: none;
    cursor: text;
  }

  .ai-models-wrapper .iface-list { display: flex; flex-direction: column; gap: 4px; }
  .ai-models-wrapper .iface-row { display: flex; align-items: center; gap: 6px; }
  .ai-models-wrapper .iface-badge {
    font-size: 9px;
    padding: 1px 5px;
    border-radius: 3px;
    font-weight: 600;
    flex-shrink: 0;
    text-transform: uppercase;
    letter-spacing: 0.04em;
    min-width: 42px;
    text-align: center;
  }
  .ai-models-wrapper .badge-web  { background: rgba(37, 99, 235, 0.08) !important; color: #2563eb !important; }
  .ai-models-wrapper .badge-desk { background: rgba(16, 185, 129, 0.08) !important; color: #10b981 !important; }
  .ai-models-wrapper .badge-ide  { background: rgba(217, 119, 6, 0.08) !important; color: #d97706 !important; }
  .ai-models-wrapper .badge-cli  { background: rgba(139, 92, 246, 0.08) !important; color: #8b5cf6 !important; }

  .dark .ai-models-wrapper .badge-web  { background: rgba(96, 165, 250, 0.15) !important; color: #90cdf4 !important; }
  .dark .ai-models-wrapper .badge-desk { background: rgba(52, 211, 153, 0.15) !important; color: #81e6d9 !important; }
  .dark .ai-models-wrapper .badge-ide  { background: rgba(251, 191, 36, 0.15) !important; color: #fbd38d !important; }
  .dark .ai-models-wrapper .badge-cli  { background: rgba(196, 160, 247, 0.15) !important; color: #d6bcfa !important; }

  .ai-models-wrapper .iface-detail {
    font-size: 11px;
    color: var(--text-secondary) !important;
    outline: none;
    cursor: text;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
  }
  .ai-models-wrapper .iface-detail:focus { color: var(--text-primary) !important; white-space: normal; }

  .ai-models-wrapper .excels-text { font-size: 13px; color: var(--text-secondary) !important; line-height: 1.5; outline: none; cursor: text; }
  .ai-models-wrapper .excels-text:focus { color: var(--text-primary) !important; }

  .ai-models-wrapper .note {
    display: block;
    margin-top: 5px;
    font-size: 11px;
    color: var(--text-muted) !important;
    border-left: 2px solid var(--border) !important;
    padding-left: 7px;
    outline: none;
    cursor: text;
  }
  .ai-models-wrapper .note:focus { color: var(--text-secondary) !important; border-left-color: var(--accent) !important; }

  .ai-models-wrapper .asterisk { color: var(--baidu) !important; font-size: 14px; font-weight: bold; margin-left: 2px; }

  .ai-models-wrapper .asterisk-note {
    margin-top: 14px;
    font-size: 11px;
    color: var(--text-muted) !important;
  }
  .ai-models-wrapper .asterisk-note span { color: var(--baidu) !important; }

  .ai-models-wrapper tr[data-company="anthropic"] td:first-child { box-shadow: inset 3px 0 0 var(--anthropic) !important; }
  .ai-models-wrapper tr[data-company="openai"]    td:first-child { box-shadow: inset 3px 0 0 var(--openai) !important; }
  .ai-models-wrapper tr[data-company="google"]    td:first-child { box-shadow: inset 3px 0 0 var(--google) !important; }
  .ai-models-wrapper tr[data-company="xai"]       td:first-child { box-shadow: inset 3px 0 0 var(--xai) !important; }
  .ai-models-wrapper tr[data-company="deepseek"]  td:first-child { box-shadow: inset 3px 0 0 var(--deepseek) !important; }
  .ai-models-wrapper tr[data-company="zai"]       td:first-child { box-shadow: inset 3px 0 0 var(--zai) !important; }
  .ai-models-wrapper tr[data-company="baidu"]     td:first-child { box-shadow: inset 3px 0 0 var(--baidu) !important; }

  .ai-models-wrapper .dot-anthropic { background: var(--anthropic); }
  .ai-models-wrapper .dot-openai    { background: var(--openai); }
  .ai-models-wrapper .dot-google    { background: var(--google); }
  .ai-models-wrapper .dot-xai       { background: var(--xai); }
  .ai-models-wrapper .dot-deepseek  { background: var(--deepseek); }
  .ai-models-wrapper .dot-zai       { background: var(--zai); }
  .ai-models-wrapper .dot-baidu     { background: var(--baidu); }

  @media (max-width: 768px) {
    .ai-models-wrapper .table-wrap { overflow-x: auto; }
    .ai-models-wrapper table { min-width: 720px; }
  }
</style>

<!-- Outer wrapper representing the dark-themed block widget -->
<div class="ai-models-wrapper">
<!-- The inner page contents which gets cloned and exported on Download -->
<div id="ai-models-page" class="ai-models-page">
<header>
<div class="eyebrow">AI Landscape</div>
<h1 class="table-title">The Models Worth Knowing<br><em>May 2026</em></h1>
<p class="subtitle">A field guide to who's building what — and where each lab truly shines.</p>
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
<th>Company</th>
<th>Models</th>
<th>Best Name</th>
<th>Interface</th>
<th>Excels At</th>
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
<div class="iface-row"><span class="iface-badge badge-desk">Desktop</span><span class="iface-detail">Claude Desktop</span></div>
<div class="iface-row"><span class="iface-badge badge-cli">CLI</span><span class="iface-detail">Claude Code</span></div>
</div>
</div></td>
<td><div class="cell">
<span class="excels-text">Writing, coding<br><span style="color: rgb(122, 130, 153); font-family: 'DM Mono', monospace; font-size: 11px;">⭐ The one I use for writing tasks</span></span>
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
<div class="iface-row"><span class="iface-badge badge-desk">Desktop</span><span class="iface-detail">Codex IDE</span></div>
<div class="iface-row"><span class="iface-badge badge-cli">CLI</span><span class="iface-detail">OpenAI CLI</span></div>
</div>
</div></td>
<td><div class="cell">
<span class="excels-text">Math, physics, images</span>
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
<div class="iface-row"><span class="iface-badge badge-desk">Desktop</span><span class="iface-detail">Antigravity 2.0</span></div>
<div class="iface-row"><span class="iface-badge badge-ide">IDE</span><span class="iface-detail">Antigravity IDE</span></div>
<div class="iface-row"><span class="iface-badge badge-cli">CLI</span><span class="iface-detail">Antigravity CLI</span></div>
</div>
</div></td>
<td><div class="cell">
<span class="excels-text">Images, multimodal, science</span>
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
<div class="iface-row"><span class="iface-badge badge-desk">Desktop</span><span class="iface-detail">X Desktop App</span></div>
<div class="iface-row"><span class="iface-badge badge-cli">CLI</span><span class="iface-detail">xAI API</span></div>
</div>
</div></td>
<td><div class="cell">
<span class="excels-text">Real-time news, long context</span>
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
<div class="iface-row"><span class="iface-badge badge-desk">Desktop</span><span class="iface-detail">DeepSeek App</span></div>
<div class="iface-row"><span class="iface-badge badge-cli">CLI</span><span class="iface-detail">DeepSeek API</span></div>
</div>
</div></td>
<td><div class="cell">
<span class="excels-text">Cost-efficient</span>
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
<div class="iface-row"><span class="iface-badge badge-desk">Desktop</span><span class="iface-detail">—</span></div>
<div class="iface-row"><span class="iface-badge badge-cli">CLI</span><span class="iface-detail">Z.AI API</span></div>
</div>
</div></td>
<td><div class="cell">
<span class="excels-text">Cost-efficient</span>
<span class="note">⭐ The one I use for cheap tasks</span>
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
<div class="iface-row"><span class="iface-badge badge-desk">Desktop</span><span class="iface-detail">—</span></div>
<div class="iface-row"><span class="iface-badge badge-cli">CLI</span><span class="iface-detail">Baidu Qianfan API</span></div>
</div>
</div></td>
<td><div class="cell">
<span class="excels-text">Cost-efficient</span>
</div></td>
</tr>
</tbody>
</table>
</div>

<p class="asterisk-note"><span>*</span> Recent release — already the best Chinese model on global leaderboards.</p>
</div>
</div>
