---
title: "Citations and references in AI-assisted academic writing"
date: 2026-05-13
description: "A ranked comparison of MCP server tools for citation lookup, topic expansion, and literature review workflows. Covers Scite, Semantic Scholar, OpenAlex, PubMed, Zotero, and more."
tags: ["AI", "MCP", "literature", "tools"]
---

AI can be an excellent tool to help scientists develop ideas, write papers, and refine their output. My impression is that resistance to adoption comes from a real limitation: research requires more than text editing. It requires connecting to the sources of knowledge.
Since Anthropic popularized MCP servers, that connection has become practical. MCP (Model Context Protocol) is an open standard that lets AI models communicate directly with external tools and data sources. For scientists, this means your AI assistant can search the literature, retrieve papers, and rank them by citation impact, all within the same conversation.
The best source for this is Scite, a paid service that not only counts citations but tells you whether a paper was supported or contradicted by subsequent work. Here I present the best free and low-cost alternatives, what each one is good for, and how to combine them depending on your workflow.
The ranking below compares seven available MCP servers across citation quality, coverage, and workflow fit, with notes on what to pair with what.
I have tried some of them and find them useful for different purposes.I'd genuinely like to hear what has worked for you.[patricio@pperezh.com](mailto:patricio@pperezh.com).

<style>
.tt { width: 100%; border-collapse: collapse; font-size: 13px; table-layout: fixed; }
.tt th { font-size: 11px; font-weight: 500; color: #6b7280; text-align: left; padding: 6px 8px; border-bottom: 0.5px solid #e5e7eb; }
.tt td { padding: 8px; border-bottom: 0.5px solid #e5e7eb; vertical-align: top; }
.tt tr:last-child td { border-bottom: none; }
.tt tr.data-row:hover td { background: #f9fafb; }
.rk { font-size: 15px; font-weight: 500; width: 24px; text-align: center; }
.nm { font-weight: 500; font-size: 13px; }
.nm a { color: inherit; text-decoration: underline; text-underline-offset: 2px; }
.sb { font-size: 11px; color: #6b7280; margin-top: 2px; }
.badge { display: inline-block; font-size: 11px; padding: 2px 6px; border-radius: 4px; margin: 1px 1px 1px 0; white-space: nowrap; }
.bg { background: #EAF3DE; color: #3B6D11; }
.ba { background: #FAEEDA; color: #854F0B; }
.br { background: #FCEBEB; color: #A32D2D; }
.bb { background: #E6F1FB; color: #185FA5; }
.bgy { background: #F1EFE8; color: #5F5E5A; }
.bp { background: #EEEDFE; color: #3C3489; }
.bar-wrap { display: flex; align-items: center; gap: 6px; }
.bar-bg { flex: 1; height: 5px; background: #e5e7eb; border-radius: 3px; min-width: 40px; }
.bar-fill { height: 5px; border-radius: 3px; }
.bar-teal { background: #1D9E75; }
.bar-amber { background: #BA7517; }
.sc { font-size: 12px; color: #6b7280; min-width: 28px; }
.sl { font-size: 11px; font-weight: 500; color: #6b7280; padding: 10px 8px 4px; letter-spacing: 0.04em; text-transform: uppercase; }
.paid-row td { opacity: 0.85; }
.out-row td { opacity: 0.7; }
.dark .tt th { color: #9ca3af; border-bottom-color: #374151; }
.dark .tt td { border-bottom-color: #374151; }
.dark .tt tr.data-row:hover td { background: #1f2937; }
.dark .sb { color: #9ca3af; }
.dark .sc { color: #9ca3af; }
.dark .sl { color: #9ca3af; }
.dark .bar-bg { background: #374151; }
.dark .bg { background: #27500A; color: #C0DD97; }
.dark .ba { background: #633806; color: #FAC775; }
.dark .br { background: #791F1F; color: #F7C1C1; }
.dark .bb { background: #0C447C; color: #B5D4F4; }
.dark .bgy { background: #444441; color: #D3D1C7; }
.dark .bp { background: #3C3489; color: #CECBF6; }
</style>
<div style="padding: 0.75rem 0 1rem; overflow-x: auto;">
<table class="tt">
<colgroup>
<col style="width: 28px">
<col style="width: 140px">
<col style="width: 160px">
<col>
<col style="width: 72px">
</colgroup>
<thead>
<tr><th>#</th><th>Tool</th><th>MCP status</th><th>Key strengths</th><th>Score</th></tr>
</thead>
<tbody>
<tr><td colspan="5" class="sl">✦ Paid / freemium ✦</td></tr>
<tr class="data-row paid-row">
<td class="rk">1</td>
<td><div class="nm"><a href="https://scite.ai" target="_blank" rel="noopener">Scite.ai</a></div><div class="sb">1.2B+ citation statements</div></td>
<td><span class="badge bg">✓ MCP connected</span> <span class="badge ba">paid tier</span><div class="sb">Already in your connectors</div></td>
<td><span class="badge bb">supporting vs contrasting</span> <span class="badge bb">retraction flags</span> <span class="badge bb">citation context</span><div class="sb">The gold standard. Unique citation quality scoring that no free tool matches. Cost is the only barrier.</div></td>
<td><div class="bar-wrap"><div class="bar-bg"><div class="bar-fill bar-teal" style="width:100%"></div></div><span class="sc">10/10</span></div></td>
</tr>
<tr><td colspan="5" class="sl">✦ Free tier: best alternatives ✦</td></tr>
<tr class="data-row">
<td class="rk">2</td>
<td><div class="nm"><a href="https://www.semanticscholar.org" target="_blank" rel="noopener">Semantic Scholar</a></div><div class="sb">200M+ papers</div></td>
<td><span class="badge bg">✓ MCP available</span> <span class="badge bgy">self-hosted</span><div class="sb">semantic-scholar-fastmcp via Smithery/GitHub</div></td>
<td><span class="badge bb">sort by citations</span> <span class="badge bb">influential citations</span> <span class="badge bb">TLDR summaries</span> <span class="badge bb">paper recommendations</span><div class="sb">Closest free Scite substitute. Free API key optional but raises rate limits.</div></td>
<td><div class="bar-wrap"><div class="bar-bg"><div class="bar-fill bar-teal" style="width:90%"></div></div><span class="sc">9/10</span></div></td>
</tr>
<tr class="data-row">
<td class="rk">3</td>
<td><div class="nm"><a href="https://openalex.org" target="_blank" rel="noopener">OpenAlex</a></div><div class="sb">250M+ works</div></td>
<td><span class="badge bg">✓ MCP available</span> <span class="badge bgy">self-hosted</span><div class="sb">openalex-research-mcp on GitHub — no API key needed</div></td>
<td><span class="badge bb">citation counts</span> <span class="badge bb">related works</span> <span class="badge bb">topic trends</span> <span class="badge bb">100K calls/day free</span><div class="sb">Best for citation graph expansion. No citation context (supporting/contrasting) but massive free coverage.</div></td>
<td><div class="bar-wrap"><div class="bar-bg"><div class="bar-fill bar-teal" style="width:85%"></div></div><span class="sc">8.5/10</span></div></td>
</tr>
<tr class="data-row">
<td class="rk">4</td>
<td><div class="nm"><a href="https://pubmed.ncbi.nlm.nih.gov" target="_blank" rel="noopener">PubMed</a></div><div class="sb">36M+ biomedical</div></td>
<td><span class="badge bg">✓ MCP connected</span> <span class="badge bp">already yours</span><div class="sb">Live in your Claude connectors</div></td>
<td><span class="badge bb">MeSH precision</span> <span class="badge bb">plant biology coverage</span> <span class="badge ba">no citation counts</span><div class="sb">Best discipline precision for life sciences. Pair with Semantic Scholar or OpenAlex for impact ranking.</div></td>
<td><div class="bar-wrap"><div class="bar-bg"><div class="bar-fill bar-teal" style="width:70%"></div></div><span class="sc">7/10</span></div></td>
</tr>
<tr><td colspan="5" class="sl">✦ Free tier: useful for specific steps ✦</td></tr>
<tr class="data-row">
<td class="rk">5</td>
<td><div class="nm"><a href="https://github.com/54yyyu/zotero-mcp" target="_blank" rel="noopener">Zotero MCP</a></div><div class="sb">Your personal library</div></td>
<td><span class="badge bg">✓ MCP available</span> <span class="badge bgy">self-hosted</span><div class="sb">zotero-mcp (54yyyu) via PyPI/GitHub</div></td>
<td><span class="badge bb">manage saved refs</span> <span class="badge bb">PDF annotations</span> <span class="badge bb">BibTeX export</span> <span class="badge bb">retraction alerts</span><div class="sb">Not for discovery — for organising what you already have.</div></td>
<td><div class="bar-wrap"><div class="bar-bg"><div class="bar-fill bar-teal" style="width:65%"></div></div><span class="sc">6.5/10</span></div></td>
</tr>
<tr class="data-row">
<td class="rk">6</td>
<td><div class="nm"><a href="https://github.com/openags/paper-search-mcp" target="_blank" rel="noopener">Paper-Search MCP</a></div><div class="sb">20+ source aggregator</div></td>
<td><span class="badge bg">✓ MCP available</span> <span class="badge bgy">self-hosted</span><div class="sb">openags/paper-search-mcp on GitHub</div></td>
<td><span class="badge bb">bioRxiv preprints</span> <span class="badge bb">broad source coverage</span> <span class="badge ba">no citation ranking</span><div class="sb">Good for catching very recent plant biology preprints. Breadth over depth.</div></td>
<td><div class="bar-wrap"><div class="bar-bg"><div class="bar-fill bar-teal" style="width:60%"></div></div><span class="sc">6/10</span></div></td>
</tr>
<tr class="data-row">
<td class="rk">7</td>
<td><div class="nm"><a href="https://github.com/ndchikin/reference-mcp" target="_blank" rel="noopener">CiteAssist MCP</a></div><div class="sb">CiteAs + Google Scholar</div></td>
<td><span class="badge bg">✓ MCP available</span> <span class="badge bgy">self-hosted</span><div class="sb">@ndchikin/reference-mcp via Smithery/uvx</div></td>
<td><span class="badge bb">BibTeX retrieval</span> <span class="badge ba">formatting only</span><div class="sb">Narrow use case — formats citations you already know. Not for discovery or ranking.</div></td>
<td><div class="bar-wrap"><div class="bar-bg"><div class="bar-fill bar-amber" style="width:45%"></div></div><span class="sc">4.5/10</span></div></td>
</tr>
<tr><td colspan="5" class="sl">✦ Excluded ✦</td></tr>
<tr class="out-row">
<td class="rk" style="color:#9ca3af">✗</td>
<td><div class="nm" style="color:#9ca3af">arXiv MCP</div></td>
<td><span class="badge bgy">available</span></td>
<td><span style="font-size:11px; font-style:italic; color:#9ca3af">Wrong discipline — physics/CS/math. bioRxiv (inside Paper-Search MCP) is the plant biology preprint server.</span></td>
<td><span style="font-size:11px; color:#9ca3af">excluded</span></td>
</tr>
<tr class="out-row">
<td class="rk" style="color:#9ca3af">✗</td>
<td><div class="nm" style="color:#9ca3af">CiteCheck MCP</div></td>
<td><span class="badge ba">prototype</span></td>
<td><span style="font-size:11px; font-style:italic; color:#9ca3af">arXiv preprint only — no deployable server confirmed as of May 2026.</span></td>
<td><span style="font-size:11px; color:#9ca3af">excluded</span></td>
</tr>
<tr class="out-row">
<td class="rk" style="color:#9ca3af">✗</td>
<td><div class="nm" style="color:#9ca3af">Citation Finder AI</div></td>
<td><span class="badge br">unverified</span></td>
<td><span style="font-size:11px; font-style:italic; color:#9ca3af">PulseMCP listing only — no GitHub source, docs, or maintenance record found.</span></td>
<td><span style="font-size:11px; color:#9ca3af">excluded</span></td>
</tr>
</tbody>
</table>
</div>
