---
name: mg-works-design-system
description: Sistema visual MG Works (e camada digital compartilhada com Northbound Financial Intelligence) — tokens, tipografia Archivo + IBM Plex Mono, laranja #FA5002, componentes mw-, logos e fontes locais. Use sempre que o usuário pedir algo "no estilo MG Works", "com o design system MG Works", "on-brand MG Works" ou "Northbound", ou quando for criar/ajustar UI, páginas, apresentações, documentos ou peças da MG Works.
---

# MG Works Design System

O pacote completo está instalado em `design-md/mg-works/` (versão 1.0.0, 22/09/2026). Ele é a fonte de verdade — não invente valores.

## Ordem de leitura

1. `design-md/mg-works/DESIGN.md` — documento consolidado (guia, tokens, componentes, implementação).
2. `design-md/mg-works/branding/mgworks-system-v1/tokens.css` e `tokens.json` — valores exatos.
3. `design-md/mg-works/branding/mgworks-system-v1/components.css` — classes `mw-` (botão, campo, chip, alerta, cartão, tabela).
4. `design-md/mg-works/branding/mgworks-system-v1/index.html` — catálogo visual de referência (não copiar estaticamente para o produto).
5. Assets: `branding/mgworks-v1/` (logos e avatares MG Works), `branding/northbound-v2/logo-primary.svg`, `branding/northbound-v2/fonts/` (Archivo variável, IBM Plex Mono 400/500, licenças OFL).

## Para integrar em outro projeto

Siga `design-md/mg-works/PROMPT-PARA-CLAUDE-CODE.md`: identificar framework, entrada, estilos globais e componentes; aplicar tokens, tipografia, componentes, estados e acessibilidade; preservar nome, marca, rotas e funcionalidades do projeto; usar MG Works só como referência visual, salvo se o projeto for da MG Works.

## Regras essenciais (resumo do pacote)

- Preto, branco e laranja `#FA5002` são a identidade. Laranja e azul claro `#A3D6F4` somam até ~5% da composição.
- Texto preto sobre laranja; nunca texto branco pequeno sobre laranja.
- Archivo para títulos, texto e interface; IBM Plex Mono (400/500) para códigos, números, versões e metadados. Corpo nunca abaixo de 16 px na web.
- Filete cromático (`--color-signal-gradient`, laranja → névoa → azul) só como linha curta/borda — nunca atrás de texto, em estados ou nos logos.
- Bordas de 1 px; contorno de 2 px ou `--focus-ring` para foco. Raio 4 px em controles, 8 px em cartões. Sombras mínimas.
- Cor nunca é o único indicador de estado; status sempre escrito.
- Nunca recriar, recolorir ou distorcer logotipos: usar os SVGs do pacote. Northbound mantém sua própria assinatura.
- Movimento: 120 / 180 / 260 ms, `cubic-bezier(0.2, 0.75, 0.25, 1)`; respeitar `prefers-reduced-motion`.
