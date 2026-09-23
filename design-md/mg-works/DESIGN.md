# MG Works Design System — DESIGN.md

> Versão 1.2.0, rascunho de sistema, 23 de setembro de 2026. Temas claro e escuro: automático pelo sistema operacional, ou fixo com `data-theme`.
> Documento consolidado a partir dos arquivos oficiais do pacote em `branding/mgworks-system-v1/`
> (`GUIDE.md`, `TOKENS.md`, `COMPONENTS.md`, `IMPLEMENTATION.md`, `CHANGELOG.md`). Em caso de divergência,
> `tokens.json` e `tokens.css` são a fonte de verdade dos valores.

## Arquivos-fonte

| Arquivo | Conteúdo |
| --- | --- |
| `branding/mgworks-system-v1/tokens.css` | Variáveis CSS prontas (com `@font-face` locais) |
| `branding/mgworks-system-v1/tokens.json` | Fonte estruturada dos tokens |
| `branding/mgworks-system-v1/components.css` | Componentes reutilizáveis com prefixo `mw-` |
| `branding/mgworks-system-v1/index.html` | Catálogo visual local |
| `branding/mgworks-v1/*.svg` | Assinaturas MG Works (logo primário, reverso, avatares) |
| `branding/northbound-v2/logo-primary.svg` | Assinatura Northbound |
| `branding/northbound-v2/fonts/` | Archivo (variável) e IBM Plex Mono, licenças SIL OFL |




---

## MG Works Design System

Versão 1.2.0, rascunho de sistema, 23 de setembro de 2026. Histórico em `CHANGELOG.md`.

### Papel do sistema

Uma linguagem comum para a marca MG Works e para seus pontos de contato, incluindo apresentações, documentos, site, conteúdo social e interfaces digitais. Produtos com identidade própria, como Northbound Financial Intelligence, podem usar a camada digital compartilhada e manter seus logotipos aprovados.

O nome MG Works permanece provisório. Este arquivo documenta direção visual e padrões de uso. Não confirma disponibilidade de marca, não cria uma nova identidade legal e não substitui as aprovações comerciais documentadas em `branding/`.

### Ideia central

Clareza que conecta visão e execução. A composição mostra relações, etapas e sinais com hierarquia direta. Cada elemento gráfico deve ajudar a entender o conteúdo, navegar pelo trabalho ou reconhecer a marca.

#### Princípios

1. **Clareza antes do efeito.** Títulos dizem o que importa, dados permanecem legíveis e o próximo passo é fácil de localizar.
2. **Estrutura visível.** Retículas, divisores e rótulos ajudam a organizar relações sem transformar toda superfície em diagrama.
3. **Contraste com propósito.** Preto e branco sustentam a leitura. Laranja chama atenção para ações e pontos de decisão. Azul claro e o filete cromático aparecem com parcimônia.
4. **Precisão humana.** A voz é experiente, direta e acessível. Evitar exageros, promessas genéricas e linguagem excessivamente técnica.
5. **Um sistema, vários formatos.** A mesma hierarquia se adapta a telas, documentos e comunicação, sem forçar todas as aplicações a parecerem interfaces.

### Relação entre as marcas

- **MG Works** é a marca principal deste sistema. Usar a assinatura existente `MG Works · AI, Design & Technology` quando o contexto pedir a descrição das frentes de trabalho.
- **Northbound Financial Intelligence** é uma marca de produto no contexto deste projeto. Manter o símbolo e as assinaturas de `branding/northbound-v2/`. Não trocar o nome do produto pelo nome da empresa em telas ou materiais já aprovados.
- **Piloto MCI** mantém as regras específicas de conteúdo, documentos e tratamento de dados descritas em `PRODUCT.md`, `docs/DATA-HANDLING.md` e nos materiais privados. Este sistema não autoriza inserir documentos ou dados comerciais reais.

### Assinaturas de marca

Os arquivos em `branding/mgworks-v1/` são a fonte oficial da identidade MG Works registrada até esta versão. O wordmark horizontal usa Archivo 600 em preto ou branco, com quadrado laranja separado. O avatar preto aprovado usa lettering branco e quadrado laranja. O conjunto de opções antigas permanece preservado.

#### Uso

- Priorizar `logo-primary.svg` em fundos brancos ou muito claros.
- Usar `logo-reverse.svg` em fundos pretos ou muito escuros.
- Usar o avatar aprovado quando não houver espaço para a assinatura completa.
- Manter área livre ao redor equivalente à altura do quadrado laranja.
- Não recriar letras, alterar a proporção, recolorir o quadrado, aplicar sombras ou colocar textura sobre o logo.
- Nunca reduzir uma assinatura até perder leitura. Trocar pelo avatar ou nome em texto quando o tamanho for insuficiente.
- Evitar posicionar o wordmark sobre fotografias com contraste irregular.

#### Arquivos Northbound

Usar as assinaturas aprovadas em `branding/northbound-v2/`. O pacote tem só a versão preta: sobre fundo escuro, aplicar a placa branca `mw-brand-plate` em vez de recolorir. A direção Northbound tem símbolo próprio e não deve herdar o avatar MG Works. Para composição conjunta, manter marcas independentes, alinhar pelas linhas de base e criar separação com espaço ou divisor simples.

### Paleta

Preto, branco e laranja pertencem à identidade. Carvão, névoa, cinza claro e azul claro vêm da referência visual e ampliam a camada de interface e comunicação. Ver `TOKENS.md` para valores e pares recomendados.

#### Distribuição sugerida

- 65 a 80 por cento: branco, superfícies claras ou preto, conforme o contexto.
- 15 a 30 por cento: neutros de estrutura, texto secundário e divisores.
- Até 5 por cento: laranja e azul claro. O azul claro nunca substitui o contraste necessário em texto.
- O filete em gradiente é um acento gráfico, não uma cor de texto nem uma assinatura de marca.

Esses percentuais são guias de composição, não limites matemáticos. Materiais de alto contraste podem usar uma superfície preta dominante.

#### Tema escuro

O sistema tem tema escuro desde a versão 1.1.0. A partir da 1.2.0, sem `data-theme` no `<html>` a página segue o sistema operacional; `data-theme="light"` ou `data-theme="dark"` fixam o tema. Ele troca texto, bordas, superfícies, feedback, sombras e foco (ver `TOKENS.md`). Preto, branco e laranja da identidade não mudam, e a composição escura continua reservada para capas e destaques quando o tema claro estiver ativo. No escuro, usar `logo-reverse.svg`. Northbound, que só tem a versão preta, fica sobre a placa branca `mw-brand-plate`.

### Tipografia

#### Archivo

Fonte primária para wordmark, títulos, navegação, leitura longa e interfaces. Usar Archivo variável local, incluída em `branding/northbound-v2/fonts/`, respeitando a licença local.

- Display: 600 a 700, linhas curtas e poucas quebras.
- Títulos: 500 a 600, sem caixa alta longa.
- Corpo: 400, entre 45 e 80 caracteres por linha em leitura editorial.
- Rótulos: 500 ou 600, caixa alta curta e espaçamento de letras discreto.

#### IBM Plex Mono

Fonte secundária para códigos, metadados, números alinhados, SKU, versões e pequenos rótulos técnicos. Usar nos pesos 400 e 500. Evitar parágrafos inteiros em mono.

#### Hierarquia

Aplicar a escala em `TOKENS.md`. O display pode ocupar 48 a 88 px conforme o espaço. Texto corrido começa em 16 px na web. Rótulos podem usar 12 px, com contraste suficiente. Reduzir display de forma fluida no celular, sem reduzir corpo abaixo de 16 px.

### Composição

#### Retícula

- Desktop: 12 colunas, gutter de 24 px, largura de conteúdo até 1280 px.
- Tablet: 8 colunas, gutter de 20 a 24 px.
- Celular: 4 colunas, gutter de 16 px.
- Margens laterais recomendadas: 32 px no desktop, 24 px no tablet, 16 px no celular.
- Usar alinhamentos consistentes entre título, texto, imagem e dados.

#### Linhas e molduras

Retículas finas e guias de alinhamento aparecem em materiais de apresentação, diagramas e capas. Em interface diária, usar divisores só quando esclarecem agrupamento ou hierarquia. Bordas de 1 px são padrão. Contorno de 2 px marca foco ou ênfase.

#### Motivo cromático

O filete horizontal laranja, névoa e azul claro é a extensão mais reconhecível da referência. Usar em pequenos comprimentos, como divisor, topo de cartão editorial, linha de progresso não semântica ou borda de uma composição. A ordem é laranja, névoa, azul. Não usar o gradiente atrás de texto, em dados de estado ou dentro das assinaturas de marca.

#### Formas e textura

Preferir retângulos retos, círculos simples, recortes geométricos e linhas. Cantos suaves aparecem em controles e cartões de interface. Materiais editoriais podem usar cantos retos. Evitar sombras pesadas, ruído decorativo e gradientes de fundo extensos.

### Fotografia e imagem

- Priorizar imagens reais de contexto de trabalho, equipamentos, espaços, pessoas e produto, com enquadramento claro.
- Buscar luz controlada, detalhe material e contraste natural. Não usar fotografia como substituto de informação.
- Não aplicar filtros que mudem a identidade do sujeito ou saturem o laranja.
- Quando uma imagem não ajudar a explicar ou dar contexto, preferir uma composição tipográfica ou diagrama simples.
- Não reutilizar imagens da publicação de referência. As fotografias desta apresentação são substituídas por exemplos tipográficos e geométricos próprios.

### Ícones e diagramas

- Ícones funcionais usam contorno simples, traço consistente de 1.5 a 2 px e área de desenho óptica de 24 px.
- Manter uma família por contexto. Evitar misturar ícones preenchidos e contornados sem razão.
- Ícones decorativos não precisam de anúncio por leitor de tela. Ícones que agem como controle precisam de nome acessível.
- Diagramas usam linha, legenda e rótulo diretamente associados ao dado. Não depender apenas de cor para indicar significado.
- A direção de fluxo deve permanecer clara em layout estreito, com alternativas em lista quando o diagrama não se adaptar.

### Movimento

Movimento é breve, funcional e não essencial para compreender o conteúdo. Usar 120 ms para resposta simples, 180 ms para componentes e até 260 ms para painéis. Em `prefers-reduced-motion: reduce`, remover deslocamentos e transições não essenciais.


#### Tokens de movimento

| Token | Valor | Quando usar |
| --- | --- | --- |
| `--motion-fast` | 120 ms | Resposta simples: hover, pressionado, cor, borda e foco de botões, campos e links |
| `--motion-base` | 180 ms | Componentes: abrir menu, mostrar toast, expandir cartão ou acordeão |
| `--motion-slow` | 260 ms | Painéis: gaveta lateral, modal, troca de painel |
| `--motion-ease-standard` | `cubic-bezier(0.2, 0.75, 0.25, 1)` | Curva única do sistema, entrada rápida e assentamento suave |

- Animar cor, opacidade e deslocamentos curtos (até 8 px). Evitar escala grande, rotação, parallax e efeitos elásticos.
- Não animar dados, valores numéricos ou estados de erro para chamar atenção.
- `components.css` já aplica `--motion-fast` com `--motion-ease-standard` em `mw-button`.
- Em `prefers-reduced-motion: reduce`, reduzir a duração a praticamente zero e manter o estado final.

### Voz e conteúdo

- Ser claro, específico e calmo.
- Preferir frases curtas com um verbo por ação.
- Botões começam com verbos concretos, como `Continuar`, `Revisar` e `Salvar rascunho`.
- Estados descrevem o fato e, quando necessário, o próximo passo.
- Não prometer resultados, capacidades ou segurança sem evidência validada.
- Escrever em português do Brasil, inglês ou espanhol conforme o público. Cada versão deve ser revisada como texto nativo, não traduzida palavra por palavra.

### Acessibilidade

- Cor nunca é o único indicador de estado, seleção ou erro.
- Texto corrido deve manter contraste de pelo menos 4.5:1. Texto grande e elementos gráficos informativos devem manter pelo menos 3:1.
- Usar texto preto sobre laranja. Evitar texto branco pequeno diretamente sobre laranja.
- Respeitar ordem lógica de títulos, landmarks, foco por teclado e alvos de toque adequados.
- Mostrar foco visível em todos os controles interativos.
- Informar erros junto ao campo, com relação programática por `aria-describedby`.
- Suportar zoom de 200 por cento e reflow em tela estreita.

### Aplicações

#### Site e páginas de produto

Abrir com um ponto de vista claro, uma explicação breve e uma ação direta. Usar o filete cromático como divisor; reservar a composição escura para capa, manifesto ou chamada principal. No restante da página, favorecer leitura e navegação.

#### Documentos e apresentações

Usar fundo branco, títulos pretos, laranja para ênfase e IBM Plex Mono para metadados e números. Em páginas de abertura, retícula e filete podem ocupar mais espaço. Em páginas de conteúdo, reduzir a ornamentação.

#### Interface digital

Usar `tokens.css` como base de cores, tipografia, espaçamento e foco. Interfaces de dados privilegiam alinhamento, rótulos explícitos, estados escritos e valores com unidades visíveis. Não usar o gradiente para classificar dados.

#### Comunicação social

Uma mensagem por peça. Usar título grande, espaço negativo e um acento gráfico. Manter a assinatura em área segura e revisar recortes em cada proporção.

### Governança

- Valores em `tokens.json` são fonte estruturada. `tokens.css` é a API web pronta para consumo e deve acompanhar mudanças feitas no JSON.
- Uma mudança de token deve incluir motivo, impacto, migração e versão no histórico do sistema.
- Uma mudança de logotipo exige atualizar o material de identidade correspondente e rever aplicações derivadas.
- Componentes novos começam por um problema de uso, não por variação estética isolada.
- Dados comerciais de pilotos e clientes não pertencem a esta pasta.

### Referência e interpretação

Referência observada em 22 de setembro de 2026: [DEVENZ STUDIO no Behance](https://www.behance.net/gallery/255636053/DEVENZ-STUDIO), projeto de identidade visual publicado em setembro de 2026 por ROBRAND/STUDIO, Rodrigo Balbino e Pedro Soares.

Elementos traduzidos para este sistema: preto e branco dominantes, composição modular, traços e divisores finos, tipografia sans geométrica, rotulagem em mono, paleta carvão e cinzas, e filete cromático do laranja ao azul claro. A assinatura Devenz, seu símbolo, fotografias e texto de marca não foram reutilizados. Os tokens de base MG Works e Northbound vêm dos materiais locais existentes; as extensões visuais são propostas para esta camada compartilhada.


---

## Tokens visuais

Fonte estruturada: `tokens.json`. Implementação web: `tokens.css`.

### Cor

| Token CSS | Valor | Papel |
| --- | --- | --- |
| `--color-brand-orange` | `#FA5002` | Laranja de identidade MG Works e Northbound |
| `--color-brand-black` | `#000000` | Preto da identidade e superfícies inversas |
| `--color-brand-white` | `#FFFFFF` | Branco da identidade e superfícies elevadas |
| `--color-reference-charcoal` | `#252424` | Carvão observado na referência, superfícies escuras secundárias |
| `--color-reference-mist` | `#CACBD2` | Névoa, linhas e parte média do filete cromático |
| `--color-reference-gray` | `#DADCE0` | Cinza claro para superfícies e demonstração cromática |
| `--color-reference-blaze` | `#F67300` | Laranja observado na referência, apoio editorial |
| `--color-reference-cyan` | `#A3D6F4` | Azul claro da referência, detalhe gráfico |
| `--color-ink-strong` | `#111111` | Títulos e texto de maior prioridade |
| `--color-ink-default` | `#252424` | Texto principal |
| `--color-ink-muted` | `#62666B` | Texto secundário com leitura normal |
| `--color-ink-subtle` | `#858A90` | Metadados visuais, evitar texto essencial pequeno |
| `--color-border-strong` | `#8E9399` | Limites de controle e elementos selecionados |
| `--color-border-default` | `#CACBD2` | Divisores e bordas padrão |
| `--color-border-subtle` | `#E6E7E9` | Separadores secundários |
| `--color-surface-page` | `#F4F4F2` | Fundo principal de páginas digitais |
| `--color-surface-raised` | `#FFFFFF` | Cartões, menus, campos e painéis claros |
| `--color-surface-soft` | `#ECEDEE` | Superfície auxiliar |
| `--color-surface-inverse` | `#000000` | Capa, rodapé escuro, painel de destaque |

#### Pares de feedback

| Uso | Texto ou ícone | Fundo |
| --- | --- | --- |
| Sucesso | `--color-feedback-success` `#176B45` | `--color-feedback-success-soft` `#E4F2EA` |
| Atenção | `--color-feedback-warning` `#835000` | `--color-feedback-warning-soft` `#FFF1D8` |
| Erro | `--color-feedback-danger` `#B42318` | `--color-feedback-danger-soft` `#FDE8E7` |
| Informação | `--color-feedback-info` `#005A86` | `--color-feedback-info-soft` `#E2F3FA` |

Sempre mostrar também um rótulo ou ícone com nome acessível. Feedback deve informar condição e próximo passo quando isso ajudar a resolver.

#### Filete cromático

`--color-signal-gradient` define uma progressão horizontal do laranja de marca para névoa e azul claro. Reservar para uma linha curta ou uma borda decorativa. Não aplicar a texto, logotipo, controles de estado ou fundos extensos.

#### Regras de contraste

- Usar texto preto sobre laranja e branco sobre preto.
- Sobre branco, texto principal usa `--color-ink-default` ou `--color-ink-strong`.
- `--color-ink-subtle` não identifica erro, estado ou instrução indispensável. Usar em informação complementar com tamanho e contraste adequados.
- Em dados, parear a cor com nome, forma ou padrão.

### Tema escuro

Adicionado na versão 1.1.0 e automático desde a 1.2.0:

| `<html>` | Resultado |
| --- | --- |
| sem `data-theme` | Segue o sistema operacional (`prefers-color-scheme`) |
| `data-theme="light"` | Sempre claro |
| `data-theme="dark"` | Sempre escuro |

O atributo também funciona em qualquer contêiner, para exibir um bloco num tema diferente do resto da página. Produtos que ainda não revisaram o próprio CSS para o escuro devem declarar `data-theme="light"` no `<html>`. Cores de identidade (`--color-brand-*`, `--color-reference-*`) e `--color-signal-gradient` não mudam entre temas. Texto preto sobre laranja continua valendo no escuro.

| Token CSS | Claro | Escuro | Contraste no escuro |
| --- | --- | --- | --- |
| `--color-ink-strong` | `#111111` | `#FFFFFF` | 17.4:1 sobre raised |
| `--color-ink-default` | `#252424` | `#ECEDEE` | 14.9:1 sobre raised |
| `--color-ink-muted` | `#62666B` | `#B4B7BC` | 8.7:1 sobre raised |
| `--color-ink-subtle` | `#858A90` | `#8E9399` | 5.6:1 sobre raised |
| `--color-border-strong` | `#8E9399` | `#7A7F86` | 3.8:1 sobre soft, limite de controle |
| `--color-border-default` | `#CACBD2` | `#3A3B3E` | divisor decorativo |
| `--color-border-subtle` | `#E6E7E9` | `#2A2A2C` | separador secundário |
| `--color-surface-page` | `#F4F4F2` | `#0E0E0E` | fundo de página |
| `--color-surface-raised` | `#FFFFFF` | `#1A1A1A` | cartões, campos, menus |
| `--color-surface-soft` | `#ECEDEE` | `#252424` | superfície auxiliar (carvão) |
| `--color-surface-inverse` | `#000000` | `#000000` | capa e rodapé |
| `--color-feedback-success` / `-soft` | `#176B45` / `#E4F2EA` | `#5CC98E` / `#10281C` | 7.6:1 |
| `--color-feedback-warning` / `-soft` | `#835000` / `#FFF1D8` | `#F2B24C` / `#2E2206` | 8.4:1 |
| `--color-feedback-danger` / `-soft` | `#B42318` / `#FDE8E7` | `#FF8A7F` / `#3A1411` | 7.1:1 |
| `--color-feedback-info` / `-soft` | `#005A86` / `#E2F3FA` | `#A3D6F4` / `#0C2433` | 10.3:1 |
| `--shadow-card` | 8% | 40% | sombra mais densa para ler sobre fundo escuro |
| `--shadow-overlay` | 18% | 60% | idem |
| `--focus-ring` | laranja a 32% | laranja a 72% | anel visível sobre superfícies escuras |

No tema escuro, usar `logo-reverse.svg` e o avatar preto. A assinatura Northbound só existe em preto: no escuro, colocá-la sobre `mw-brand-plate` (placa branca), sem recolorir. Laranja de marca sobre `#0E0E0E` mede 5.7:1 e pode ser usado como texto de destaque grande.

#### Tokens de componente

Adicionados na versão 1.1.0 para substituir valores fixos em `components.css` e permitir o tema escuro.

| Token CSS | Claro | Escuro | Uso |
| --- | --- | --- | --- |
| `--color-button-secondary-ink` | `#000000` | `#FFFFFF` | Texto do botão secundário |
| `--color-control-disabled-ink` | `#666666` | `#8E9399` | Texto de controle desabilitado |
| `--color-control-disabled-bg` | `#E3E3E3` | `#2A2A2C` | Fundo de controle desabilitado |
| `--color-control-disabled-border` | `#D4D4D4` | `#3A3B3E` | Borda de controle desabilitado |
| `--color-feedback-danger-hover` | `#FBD7D5` | `#4A1A16` | Hover do botão de perigo |
| `--color-chip-neutral-ink` | `#30343A` | `#DADCE0` | Texto do chip neutro |
| `--color-chip-neutral-bg` | `#E8E9EB` | `#2F3033` | Fundo do chip neutro |
| `--color-table-head` | `#F5F5F4` | `#151515` | Fundo do cabeçalho de tabela |

### Tipografia

#### Famílias

| Token | Família | Uso |
| --- | --- | --- |
| `--font-family-sans` | Archivo | Títulos, texto, navegação e interface |
| `--font-family-mono` | IBM Plex Mono | Códigos, valores tabulares, versão e metadados |

#### Tamanhos

| Token | Tamanho | Uso |
| --- | --- | --- |
| `--font-size-11` | 11 px | Legenda não essencial, usar com cuidado |
| `--font-size-12` | 12 px | Rótulo compacto |
| `--font-size-14` | 14 px | Texto auxiliar e controles densos |
| `--font-size-16` | 16 px | Texto corrido e controle padrão |
| `--font-size-18` | 18 px | Introdução e texto de apoio |
| `--font-size-20` | 20 px | Título pequeno |
| `--font-size-24` | 24 px | Título de cartão ou seção curta |
| `--font-size-32` | 32 px | Título de seção |
| `--font-size-40` | 40 px | Título de página secundária |
| `--font-size-48` | 48 px | Título de página |
| `--font-size-64` | 64 px | Display em desktop |

Display usa escala fluida e não deve provocar rolagem horizontal. Corpo permanece em 16 px ou maior na web.

#### Pesos e linhas

- Pesos: 400 regular, 500 médio, 600 semibold, 700 bold.
- `--line-height-tight`: 1.05 para display curto.
- `--line-height-heading`: 1.12 para títulos.
- `--line-height-body`: 1.5 para interface e texto corrido.
- `--line-height-relaxed`: 1.65 para textos longos.
- `--letter-spacing-label`: 0.08em para rótulos curtos em caixa alta.

### Espaçamento

| Token | Valor | Exemplo |
| --- | --- | --- |
| `--space-1` | 4 px | Ajuste entre ícone e texto |
| `--space-2` | 8 px | Espaço compacto |
| `--space-3` | 12 px | Agrupamento próximo |
| `--space-4` | 16 px | Espaço interno padrão |
| `--space-5` | 20 px | Separação dentro de grupo |
| `--space-6` | 24 px | Gutter e padding de painel |
| `--space-8` | 32 px | Separação entre grupos |
| `--space-10` | 40 px | Espaço entre conteúdo relacionado |
| `--space-12` | 48 px | Respiro entre blocos |
| `--space-16` | 64 px | Respiro de seção |
| `--space-20` | 80 px | Transição editorial ampla |

`--space-0` representa zero. Criar um valor novo apenas quando a composição não couber na escala.

### Forma, borda e profundidade

| Token | Valor | Uso |
| --- | --- | --- |
| `--border-width-hairline` | 1 px | Divisor e borda padrão |
| `--border-width-strong` | 2 px | Foco e destaque |
| `--radius-none` | 0 px | Composição editorial e bordas quadradas |
| `--radius-xs` | 2 px | Etiqueta compacta |
| `--radius-sm` | 4 px | Campo e botão |
| `--radius-md` | 8 px | Painel de interface |
| `--radius-lg` | 12 px | Modal ou cartão elevado |
| `--radius-pill` | 999 px | Indicador ou chip arredondado |
| `--shadow-card` | 0 1px 2px com 8% | Separação mínima de superfície |
| `--shadow-overlay` | 0 16px 48px com 18% | Modal, popover e menu sobreposto |

Elevação não substitui borda, contraste ou hierarquia. Em materiais editoriais, usar sombra nenhuma.

### Layout e movimento

| Token | Valor |
| --- | --- |
| `--container-max` | 1280 px |
| `--grid-columns-desktop` | 12 |
| `--grid-gutter` | 24 px |
| `--motion-fast` | 120 ms |
| `--motion-base` | 180 ms |
| `--motion-slow` | 260 ms |
| `--motion-ease-standard` | cubic-bezier(0.2, 0.75, 0.25, 1) |
| `--focus-ring` | anel de 3 px com laranja de marca a 32% |

Tablet usa 8 colunas. Celular usa 4 colunas. Para motion reduzido, zerar duração ou remover a transição que causa movimento.


---

## Componentes e padrões

Os componentes seguem a camada web compartilhada. Usar HTML semântico e os tokens de `tokens.css`. `components.css` contém estilos reutilizáveis com o prefixo `mw-`. A página `index.html` demonstra as classes locais, sem framework ou etapa de compilação.

### Botão

#### Uso

Uma ação por controle. Usar verbo específico e indicar resultado esperado. A ordem visual não substitui a ordem do DOM ou a ordem de teclado.

#### Variantes

| Variante | Aparência | Uso |
| --- | --- | --- |
| Primário | Fundo laranja, texto preto, borda laranja | Ação principal do painel |
| Secundário | Fundo branco ou claro, texto preto, borda neutra | Ação complementar |
| Contorno | Fundo transparente, borda de 1 px | Ação de menor peso |
| Texto | Sem fundo, rótulo preto ou laranja com sublinhado no foco | Navegação contextual |
| Perigo | Texto e borda de erro, fundo claro de erro | Ação destrutiva reversível, com confirmação próxima |

#### Tamanhos e estados

- Compacto: altura mínima 36 px, padding horizontal 12 px.
- Padrão: altura mínima 44 px, padding horizontal 16 px.
- Grande: altura mínima 52 px, padding horizontal 20 px.
- Estados: padrão, hover, pressionado, foco visível, desabilitado e carregando.
- Desabilitado tem contraste reduzido sem parecer habilitado. Para ações pendentes, preferir explicação próxima ao controle.
- Carregando preserva a largura do botão, anuncia estado e impede envios duplicados.

#### Teclado e leitor de tela

Usar `<button>` para ação e `<a>` para navegação. Manter `Enter` e `Space` para botão nativo. Não usar `div` como botão. Ícone sem rótulo visível requer nome acessível. Descrever foco com `:focus-visible`.

### Campo de texto e seleção

#### Anatomia

Rótulo persistente, campo, texto de ajuda opcional e mensagem de validação. Placeholder ilustra um formato, não substitui rótulo. Unidade ou moeda fica próxima ao campo e não apenas como placeholder.

#### Variantes e estados

- Texto, número, busca, textarea e seleção.
- Padrão, foco, preenchido, leitura, desabilitado, erro e confirmado.
- Borda padrão usa neutro médio. Foco usa anel visível. Erro usa borda e mensagem textual.
- Nunca comunicar erro só pelo laranja ou vermelho.
- Campos financeiros recebem valor e precisão esperada explicitamente.

#### Semântica

Associar `<label for>` ao controle. Associar ajuda e erro por `aria-describedby`. Usar `aria-invalid="true"` no erro. Seleções nativas devem continuar utilizáveis por teclado.

### Navegação

#### Primária

- Navegação global identifica produto, seção atual e ações de conta.
- Navegação lateral é adequada para áreas com quatro ou mais destinos persistentes.
- Navegação por abas serve para visões irmãs do mesmo contexto, não para passos de um fluxo extenso.
- Breadcrumb é usado quando mostra uma relação real de hierarquia e oferece retorno.

#### Estados

Item atual deve combinar indicador visual com `aria-current="page"`. Hover e foco não podem ser confundidos com seleção. Em tela estreita, oferecer menu com botão rotulado, foco controlado e Escape para fechar.

#### Classes (1.2.0)

- **Global:** `mw-topbar` com `mw-topbar__brand`, `mw-topbar__nav` (links `mw-nav-link`), `mw-topbar__actions` e `mw-topbar__menu`. O botão de menu aparece abaixo de 720 px e controla um painel com `aria-expanded`, foco controlado e Escape para fechar.
- **Lateral:** `mw-sidenav` com `mw-sidenav__label`, `mw-sidenav__link` e `mw-sidenav__index` opcional em mono. O item atual tem filete laranja de 2 px à esquerda, fundo `--color-surface-soft` e `aria-current="page"`.
- **Abas:** `mw-tabs` (`role="tablist"`) com `mw-tab` (`role="tab"`, `aria-selected`, `aria-controls`) e `mw-tabpanel`. As setas movem entre as abas; só a aba ativa fica em `tabindex="0"`.
- **Breadcrumb:** `<nav class="mw-breadcrumb" aria-label="Você está em">` com uma `<ol>`. O último item tem `aria-current="page"`. O separador `/` é gerado pelo CSS.

### Cartão e painel

Cartão agrupa um assunto e uma ação. Usar superfície branca, borda sutil e raio de 8 px. Evitar cartão aninhado em cartão sem relação funcional clara. Um cartão clicável precisa ser link ou botão e expor um nome compreensível.

### Seleção: checkbox e radio

Usar os inputs nativos dentro de `<label class="mw-choice">`, com o texto em `<span>`. Radios ficam em `<fieldset class="mw-choice-group">` com `<legend>`. A área de toque é de 44 px de altura e o controle mede 20 px. A cor de marcação vem de `accent-color: var(--color-brand-orange)`, e o foco usa `--focus-ring`. Quando a opção está desabilitada, explicar o motivo em texto próximo.

### Etiquetas e status

| Tipo | Cor | Exemplo de texto |
| --- | --- | --- |
| Neutro | Cinza sobre cinza claro | Rascunho |
| Sucesso | Verde sobre fundo verde claro | Concluído |
| Atenção | Ocre sobre fundo âmbar claro | Revisar |
| Erro | Vermelho sobre fundo rosa claro | Bloqueado |
| Informação | Azul escuro sobre azul claro | Atualizado |

Status sempre aparece como texto. O indicador pode usar ponto ou ícone, mas não substitui a palavra.

### Tabela de dados

#### Estrutura

- Usar `<table>`, `<caption>`, `<thead>`, `<tbody>`, `<th scope="col">` e cabeçalho de linha onde fizer sentido.
- Alinhar texto à esquerda e números à direita.
- IBM Plex Mono é adequada a IDs, códigos e colunas numéricas.
- Manter a mesma precisão dentro de cada coluna. Mostrar moeda, unidade e período no rótulo.
- Divisores horizontais são preferíveis a linhas verticais densas.
- Linhas selecionáveis precisam de checkbox ou botão nomeado, além da mudança visual.

#### Estados e adaptação

Incluir carregamento, vazio, resultado encontrado, erro de leitura e conjunto longo. Em celular, preservar rótulos e permitir leitura sem rolagem horizontal sempre que possível. Se a tabela ficar larga, agrupar cada linha como uma lista de campos nomeados.

### Feedback

| Padrão | Quando usar | Comportamento |
| --- | --- | --- |
| Mensagem inline | Campo, seção ou erro que exige correção | Permanece junto ao conteúdo relacionado |
| Toast | Confirmação breve sem ação obrigatória | Tem anúncio `role="status"`, desaparece sem capturar foco |
| Alerta | Informação importante que exige atenção | Permanece visível enquanto relevante |
| Diálogo | Confirmação ou decisão que interrompe o fluxo | Tem título, foco inicial, Escape e retorno de foco |
| Barra de progresso | Processo com duração e avanço conhecidos | Informa texto e valor, não apenas animação |

Mensagens devem informar o que ocorreu e como resolver. Nunca esconder a origem do erro.

#### Mensagem inline e alerta (`mw-alert`)

| Variante | Classe | Marca | Exemplo |
| --- | --- | --- | --- |
| Informação | `mw-alert--info` | `i` | Dados de exemplo |
| Sucesso | `mw-alert--success` | `✓` | Rascunho salvo |
| Atenção | `mw-alert--warning` | `!` | Confirme antes de avançar |
| Erro | `mw-alert--danger` | `×` | Não foi possível ler o arquivo |

Anatomia: `mw-alert__mark` (marca em IBM Plex Mono, `aria-hidden="true"`), `mw-alert__title` (fato, em uma linha) e `mw-alert__content` (o que ocorreu e como resolver). A marca e o título repetem o significado da cor. Alerta que aparece depois de uma ação usa `role="status"` (informação, sucesso) ou `role="alert"` (erro que bloqueia). Não fechar sozinho alertas de atenção ou erro.

### Modal e menu contextual

Usar apenas quando o conteúdo interrompe menos a tarefa do que navegar para uma nova página. Dialog tem nome, descrição quando necessária, foco contido e retorno ao ponto de abertura. Menu contextual possui botão disparador e navegação de teclado previsível. Menu não serve para ocultar ação primária frequente.

#### Classes (1.2.0)

- **Diálogo:** `<dialog class="mw-dialog">` nativo, aberto com `showModal()`. Tem `mw-dialog__title` (`aria-labelledby`), `mw-dialog__body` (`aria-describedby`) e `mw-dialog__actions`, com a ação principal à direita. O fundo é escurecido a 48%, a entrada usa `--motion-slow` e, ao fechar, o foco volta ao botão que abriu.
- **Menu:** `mw-menu` (`role="menu"`) com `mw-menu__item` (`role="menuitem"`), `mw-menu__item--danger`, `mw-menu__shortcut` e `mw-menu__separator`. Adicionar `data-open` para a animação de entrada de 180 ms. Setas navegam, Escape fecha e devolve o foco ao disparador.
- **Toast:** `mw-toast-region` (fixo no canto inferior direito) com `mw-toast` (`role="status"`), `mw-toast__mark` e `mw-toast__action` opcional. O fundo usa `--color-ink-strong` e o texto `--color-surface-raised`, e as cores se invertem entre os temas. O toast some sozinho depois de 5 a 8 segundos, sem capturar foco. Mensagens com ação ficam visíveis enquanto o ponteiro ou o foco estiver sobre elas.
- **Progresso:** `mw-progress` com `mw-progress__head` (`mw-progress__label` e `mw-progress__value` em mono) e `mw-progress__track` (`role="progressbar"` com `aria-valuenow` e `aria-valuetext`) contendo `mw-progress__bar`. A barra é laranja sólida. O filete cromático não indica progresso real.

### Navegação por etapa

Para fluxo de várias etapas, exibir quantidade ou nomes de etapas e indicar a atual com texto. Preservar valores anteriores quando o usuário volta. Em fluxo financeiro ou comercial, resumir dados antes de confirmar e mostrar erros junto à etapa de origem.

#### Classes (1.2.0)

`<ol class="mw-steps">` com `mw-step`. Usar `mw-step--done` para etapas concluídas (círculo com ✓) e `aria-current="step"` para a atual (círculo laranja com número). A numeração 01, 02… é gerada pelo CSS. Abaixo, `mw-steps__status` escreve "ETAPA 2 DE 3 · REVISÃO".

### Gráficos e métricas

- Rótulos sempre indicam unidade, período e fonte quando relevantes.
- Cor deve ser redundante com forma, posição, padrão ou rótulo.
- Usar laranja para destacar uma série ou decisão importante, não para colorir todas as séries.
- Manter uma alternativa textual ou tabular acessível.
- Evitar eixos cortados que aumentam visualmente a variação.

#### Classes (1.2.0)

Gráfico de barras horizontal em `<figure class="mw-chart">`: `mw-chart__title`, `mw-chart__meta` (unidade, período e fonte em mono), `mw-chart__rows` com `mw-chart__row` (`mw-chart__label`, `mw-chart__track` > `mw-chart__bar` com `width` em %, `mw-chart__value`) e `mw-chart__source`. Só a série em decisão recebe `.is-highlight` (laranja); as demais usam `--color-ink-muted`. O valor fica sempre escrito ao lado da barra. Para gráficos mais complexos, seguir as mesmas regras de cor e rótulo com a biblioteca do projeto.

### Filete e placa de marca (1.2.0)

- `mw-signal`: filete cromático de 64 × 2 px (`mw-signal--wide` ocupa 100%). É decorativo, então usar `aria-hidden="true"`.
- `mw-brand-plate`: placa branca que mantém assinaturas de tinta única, como a Northbound, legíveis sobre fundo escuro sem recolorir o arquivo.

### Regras gerais de interação

- Área de toque recomendada de 44 por 44 px, mesmo quando o ícone visual é menor.
- Foco visível em qualquer elemento interativo.
- Hover nunca é o único meio para descobrir uma ação.
- Erros preservam entradas digitadas sempre que possível.
- A interface deve funcionar em zoom de 200 por cento e com teclado.
- Em motion reduzido, manter o estado final sem animar deslocamento, escala ou parallax.


---

## Implementação

### Início rápido

Inclua os tokens e os estilos de componente no HTML da página:

```html
<link rel="stylesheet" href="tokens.css">
<link rel="stylesheet" href="components.css">
```

As fontes Archivo e IBM Plex Mono usam arquivos locais existentes em `branding/northbound-v2/fonts/`. Preserve as licenças SIL OFL existentes ao redistribuir os arquivos de fonte.

### Exemplo de controle

```html
<button class="mw-button mw-button--primary" type="button">
  Continuar
</button>
```

As classes `mw-button--secondary`, `mw-button--quiet`, `mw-button--text`, `mw-button--danger`, `mw-button--small` e `mw-button--large` oferecem as variantes documentadas em `COMPONENTS.md`.

### Exemplo de campo acessível

```html
<div class="mw-field">
  <label class="mw-field__label" for="company-name">Empresa</label>
  <input
    class="mw-input"
    id="company-name"
    name="company-name"
    type="text"
    aria-describedby="company-name-help"
  >
  <p class="mw-field__help" id="company-name-help">Use o nome confirmado para este contexto.</p>
</div>
```

Se houver erro, inclua a mensagem no `aria-describedby` e aplique `aria-invalid="true"`. Preserve o texto já digitado.

### Tema

Sem `data-theme` no `<html>`, a página segue o tema do sistema operacional. Para fixar o tema:

```html
<html lang="pt-BR" data-theme="light">
```

Use `data-theme="dark"` para fixar o escuro. Estilos próprios do projeto devem usar os tokens semânticos (`--color-ink-*`, `--color-surface-*`, `--color-border-*`, `--color-feedback-*`) para acompanhar os dois temas. Enquanto isso não for revisado, fixe `data-theme="light"`.

### Adaptação de marca

1. Manter os arquivos oficiais de logo da marca que aparece na interface.
2. Usar a identidade MG Works em páginas institucionais e comunicação corporativa.
3. Usar a identidade Northbound em telas do produto Northbound.
4. Compartilhar cores de interface, tipografia, espaçamento e acessibilidade quando isso não apagar diferenças entre as marcas.
5. Documentar qualquer exceção local junto ao produto que a introduz.

### Atualização de tokens

`tokens.json` documenta origem, finalidade e categorias. `tokens.css` tem variáveis CSS planas para aplicação direta. Ao mudar um token:

1. Atualizar o valor estruturado e o CSS de tokens.
2. Rever combinações de contraste e exemplos em `index.html`.
3. Atualizar `TOKENS.md`, `components.css` quando necessário e o histórico.
4. Marcar alterações incompatíveis com versão maior e orientar migração.

Este pacote ainda não usa um compilador de tokens. A sincronização entre JSON e CSS é editorial nesta versão.


---

## Histórico

### 1.2.0 · 23 de setembro de 2026

- **Tema automático.** Sem `data-theme` no `<html>`, `tokens.css` segue `prefers-color-scheme`. O novo bloco `[data-theme="light"]` fixa o claro, inclusive dentro de um contêiner escuro.
  - Motivo: respeitar a preferência do sistema de quem usa.
  - Impacto: páginas sem `data-theme` passam a ficar escuras em sistemas configurados no modo escuro.
  - Migração: projetos com CSS próprio que ainda não usa tokens semânticos devem declarar `data-theme="light"` no `<html>`. O catálogo `index.html` já faz isso.
- **Novos componentes em `components.css`**, que antes só existiam como padrões em `COMPONENTS.md`:
  - navegação global (`mw-topbar`, `mw-nav-link`), lateral (`mw-sidenav`), abas (`mw-tabs`) e breadcrumb (`mw-breadcrumb`);
  - checkbox e radio (`mw-choice`), diálogo (`mw-dialog`), menu contextual (`mw-menu`) e toast (`mw-toast`);
  - barra de progresso (`mw-progress`), etapas (`mw-steps`) e gráfico de barras (`mw-chart`);
  - filete cromático (`mw-signal`) e placa de marca (`mw-brand-plate`).
  - Impacto: somente adições. Nenhuma classe existente mudou.
- **Northbound no escuro.** O pacote tem só a assinatura preta. A regra agora é aplicar `mw-brand-plate` em fundo escuro, sem recolorir o arquivo, até existir uma versão reversa aprovada.
- **Catálogo.** Demonstrações de todos os novos componentes e do Northbound sobre fundo escuro.

### 1.1.0 · 23 de setembro de 2026

- **Tema escuro opcional.** Novo bloco `[data-theme="dark"]` em `tokens.css` e `themes.dark` em `tokens.json`.
  - Motivo: oferecer leitura em ambiente escuro e interfaces de produto que pedem superfície escura.
  - Impacto: nenhum no tema claro. Brand, reference e o filete cromático não mudam.
  - Migração: nenhuma obrigatória. Para ativar, aplicar `data-theme="dark"` no `<html>` ou em um contêiner e trocar o logo por `logo-reverse.svg`.
- **Tokens de componente.** Valores fixos de `components.css` viraram tokens (`--color-button-secondary-ink`, `--color-control-disabled-*`, `--color-feedback-danger-hover`, `--color-chip-neutral-*`, `--color-table-head`), com os mesmos valores no tema claro.
  - Impacto: visual idêntico no tema claro. O texto do botão secundário passa a vir de `--color-button-secondary-ink` (`#000000`).
- **Movimento documentado.** Tabela de uso de `--motion-fast`, `--motion-base`, `--motion-slow` e `--motion-ease-standard` em `GUIDE.md`.
- **Alertas.** Variantes de sucesso e erro documentadas em `COMPONENTS.md`, com marca, título e papel ARIA, e demonstradas no catálogo.

### 1.0.0 · 22 de setembro de 2026

- Versão inicial para avaliação.
