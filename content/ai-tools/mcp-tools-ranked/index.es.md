---
title: "Escribiendo texto academico assistido por IA: qué herramientas MCP debo usar?"
date: 2026-05-13
description: "Comparación jerarquizada de servidores MCP para búsqueda de citas, expansión temática y revisión bibliográfica. Incluye Scite, Semantic Scholar, OpenAlex, PubMed, Zotero y más."
tags: ["IA", "MCP", "literatura", "herramientas"]
---

La IA es una excelente herramienta para ayudar a los científicos a desarrollar ideas, escribir artículos y refinar sus resultados. Tengo la impresión de que parte de la resistencia a su adopción proviene de una limitación real: la investigación requiere algo más que edición de texto. Requiere conectarse a las fuentes del conocimiento.
Desde que Anthropic popularizó los servidores MCP, esa conexión se ha vuelto práctica. MCP (Model Context Protocol) es un estándar abierto que permite a los modelos de IA comunicarse directamente con herramientas externas y fuentes de datos. Para los científicos, esto significa que el asistente de IA puede buscar en la literatura, recuperar artículos y clasificarlos por impacto de citaciones, todo dentro de la misma conversación.
La mejor fuente para esto es Scite, un servicio de pago que no solo contabiliza las citas, sino que indica si un artículo fue respaldado o contradicho por trabajos posteriores. Aquí presento las mejores alternativas gratuitas y de bajo costo, para qué sirve cada una y cómo combinarlas según tu flujo de trabajo.
El ranking a continuación compara siete servidores MCP disponibles en términos de calidad de citaciones, cobertura y adecuación al flujo de trabajo, con notas sobre qué combinar con qué.
He probado algunas y encuentro que cada uno es útil para distintos propósitos. Me interesa genuinamente saber qué ha funcionado para ti. [patricio@pperezh.com](mailto:patricio@pperezh.com).

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
<tr><th>#</th><th>Herramienta</th><th>Estado MCP</th><th>Fortalezas principales</th><th>Puntaje</th></tr>
</thead>
<tbody>
<tr><td colspan="5" class="sl">✦ Pago / freemium ✦</td></tr>
<tr class="data-row paid-row">
<td class="rk">1</td>
<td><div class="nm"><a href="https://scite.ai" target="_blank" rel="noopener">Scite.ai</a></div><div class="sb">1.200M+ declaraciones de citas</div></td>
<td><span class="badge bg">✓ MCP conectado</span> <span class="badge ba">plan pago</span><div class="sb">Ya en tus conectores</div></td>
<td><span class="badge bb">citas de apoyo vs contrarias</span> <span class="badge bb">alertas de retractación</span> <span class="badge bb">contexto de cita</span><div class="sb">El estándar de oro. Puntuación de calidad de citas única que ninguna herramienta gratuita iguala. El costo es la única barrera.</div></td>
<td><div class="bar-wrap"><div class="bar-bg"><div class="bar-fill bar-teal" style="width:100%"></div></div><span class="sc">10/10</span></div></td>
</tr>
<tr><td colspan="5" class="sl">✦ Nivel gratuito: mejores alternativas ✦</td></tr>
<tr class="data-row">
<td class="rk">2</td>
<td><div class="nm"><a href="https://www.semanticscholar.org" target="_blank" rel="noopener">Semantic Scholar</a></div><div class="sb">200M+ artículos</div></td>
<td><span class="badge bg">✓ MCP disponible</span> <span class="badge bgy">autoalojado</span><div class="sb">semantic-scholar-fastmcp vía Smithery/GitHub</div></td>
<td><span class="badge bb">ordenar por citas</span> <span class="badge bb">citas influyentes</span> <span class="badge bb">resúmenes TLDR</span> <span class="badge bb">recomendaciones de artículos</span><div class="sb">El sustituto gratuito más cercano a Scite. Clave API gratuita opcional pero eleva los límites de uso.</div></td>
<td><div class="bar-wrap"><div class="bar-bg"><div class="bar-fill bar-teal" style="width:90%"></div></div><span class="sc">9/10</span></div></td>
</tr>
<tr class="data-row">
<td class="rk">3</td>
<td><div class="nm"><a href="https://openalex.org" target="_blank" rel="noopener">OpenAlex</a></div><div class="sb">250M+ trabajos</div></td>
<td><span class="badge bg">✓ MCP disponible</span> <span class="badge bgy">autoalojado</span><div class="sb">openalex-research-mcp en GitHub — sin clave API</div></td>
<td><span class="badge bb">conteos de citas</span> <span class="badge bb">trabajos relacionados</span> <span class="badge bb">tendencias temáticas</span> <span class="badge bb">100K llamadas/día gratis</span><div class="sb">El mejor para expansión de grafos de citas. Sin contexto de apoyo/contrario, pero cobertura masiva y gratuita.</div></td>
<td><div class="bar-wrap"><div class="bar-bg"><div class="bar-fill bar-teal" style="width:85%"></div></div><span class="sc">8.5/10</span></div></td>
</tr>
<tr class="data-row">
<td class="rk">4</td>
<td><div class="nm"><a href="https://pubmed.ncbi.nlm.nih.gov" target="_blank" rel="noopener">PubMed</a></div><div class="sb">36M+ biomédicos</div></td>
<td><span class="badge bg">✓ MCP conectado</span> <span class="badge bp">ya es tuyo</span><div class="sb">Activo en tus conectores de Claude</div></td>
<td><span class="badge bb">precisión MeSH</span> <span class="badge bb">biología vegetal</span> <span class="badge ba">sin conteo de citas</span><div class="sb">Mayor precisión disciplinar para ciencias de la vida. Combinar con Semantic Scholar u OpenAlex para ranking de impacto.</div></td>
<td><div class="bar-wrap"><div class="bar-bg"><div class="bar-fill bar-teal" style="width:70%"></div></div><span class="sc">7/10</span></div></td>
</tr>
<tr><td colspan="5" class="sl">✦ Nivel gratuito: útil para pasos específicos ✦</td></tr>
<tr class="data-row">
<td class="rk">5</td>
<td><div class="nm"><a href="https://github.com/54yyyu/zotero-mcp" target="_blank" rel="noopener">Zotero MCP</a></div><div class="sb">Tu biblioteca personal</div></td>
<td><span class="badge bg">✓ MCP disponible</span> <span class="badge bgy">autoalojado</span><div class="sb">zotero-mcp (54yyyu) vía PyPI/GitHub</div></td>
<td><span class="badge bb">gestionar referencias</span> <span class="badge bb">anotaciones PDF</span> <span class="badge bb">exportar BibTeX</span> <span class="badge bb">alertas de retractación</span><div class="sb">No es para descubrir — es para organizar lo que ya tienes.</div></td>
<td><div class="bar-wrap"><div class="bar-bg"><div class="bar-fill bar-teal" style="width:65%"></div></div><span class="sc">6.5/10</span></div></td>
</tr>
<tr class="data-row">
<td class="rk">6</td>
<td><div class="nm"><a href="https://github.com/openags/paper-search-mcp" target="_blank" rel="noopener">Paper-Search MCP</a></div><div class="sb">Agrega 20+ fuentes</div></td>
<td><span class="badge bg">✓ MCP disponible</span> <span class="badge bgy">autoalojado</span><div class="sb">openags/paper-search-mcp en GitHub</div></td>
<td><span class="badge bb">preprints bioRxiv</span> <span class="badge bb">amplia cobertura</span> <span class="badge ba">sin ranking de citas</span><div class="sb">Útil para capturar preprints recientes de biología vegetal. Amplitud sobre profundidad — sin puntuación de calidad.</div></td>
<td><div class="bar-wrap"><div class="bar-bg"><div class="bar-fill bar-teal" style="width:60%"></div></div><span class="sc">6/10</span></div></td>
</tr>
<tr class="data-row">
<td class="rk">7</td>
<td><div class="nm"><a href="https://github.com/ndchikin/reference-mcp" target="_blank" rel="noopener">CiteAssist MCP</a></div><div class="sb">CiteAs + Google Scholar</div></td>
<td><span class="badge bg">✓ MCP disponible</span> <span class="badge bgy">autoalojado</span><div class="sb">@ndchikin/reference-mcp vía Smithery/uvx</div></td>
<td><span class="badge bb">recuperar BibTeX</span> <span class="badge ba">solo formateo</span><div class="sb">Caso de uso limitado — formatea citas que ya conoces. No sirve para descubrimiento ni ranking.</div></td>
<td><div class="bar-wrap"><div class="bar-bg"><div class="bar-fill bar-amber" style="width:45%"></div></div><span class="sc">4.5/10</span></div></td>
</tr>
<tr><td colspan="5" class="sl">✦ Excluidos ✦</td></tr>
<tr class="out-row">
<td class="rk" style="color:#9ca3af">✗</td>
<td><div class="nm" style="color:#9ca3af">arXiv MCP</div></td>
<td><span class="badge bgy">disponible</span></td>
<td><span style="font-size:11px; font-style:italic; color:#9ca3af">Disciplina incorrecta — física/CS/matemáticas. bioRxiv (dentro de Paper-Search MCP) es el servidor de preprints para biología vegetal.</span></td>
<td><span style="font-size:11px; color:#9ca3af">excluido</span></td>
</tr>
<tr class="out-row">
<td class="rk" style="color:#9ca3af">✗</td>
<td><div class="nm" style="color:#9ca3af">CiteCheck MCP</div></td>
<td><span class="badge ba">prototipo</span></td>
<td><span style="font-size:11px; font-style:italic; color:#9ca3af">Solo preprint de arXiv — sin servidor desplegable confirmado a mayo de 2026.</span></td>
<td><span style="font-size:11px; color:#9ca3af">excluido</span></td>
</tr>
<tr class="out-row">
<td class="rk" style="color:#9ca3af">✗</td>
<td><div class="nm" style="color:#9ca3af">Citation Finder AI</div></td>
<td><span class="badge br">no verificado</span></td>
<td><span style="font-size:11px; font-style:italic; color:#9ca3af">Solo en listado de PulseMCP — sin fuente en GitHub, documentación ni historial de mantenimiento.</span></td>
<td><span style="font-size:11px; color:#9ca3af">excluido</span></td>
</tr>
</tbody>
</table>
</div>
