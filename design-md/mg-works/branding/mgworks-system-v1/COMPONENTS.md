# Componentes e padrões

Os componentes seguem a camada web compartilhada. Usar HTML semântico e os tokens de `tokens.css`. `components.css` contém estilos reutilizáveis com o prefixo `mw-`. A página `index.html` demonstra as classes locais, sem framework ou etapa de compilação.

## Botão

### Uso

Uma ação por controle. Usar verbo específico e indicar resultado esperado. A ordem visual não substitui a ordem do DOM ou a ordem de teclado.

### Variantes

| Variante | Aparência | Uso |
| --- | --- | --- |
| Primário | Fundo laranja, texto preto, borda laranja | Ação principal do painel |
| Secundário | Fundo branco ou claro, texto preto, borda neutra | Ação complementar |
| Contorno | Fundo transparente, borda de 1 px | Ação de menor peso |
| Texto | Sem fundo, rótulo preto ou laranja com sublinhado no foco | Navegação contextual |
| Perigo | Texto e borda de erro, fundo claro de erro | Ação destrutiva reversível, com confirmação próxima |

### Tamanhos e estados

- Compacto: altura mínima 36 px, padding horizontal 12 px.
- Padrão: altura mínima 44 px, padding horizontal 16 px.
- Grande: altura mínima 52 px, padding horizontal 20 px.
- Estados: padrão, hover, pressionado, foco visível, desabilitado e carregando.
- Desabilitado tem contraste reduzido sem parecer habilitado. Para ações pendentes, preferir explicação próxima ao controle.
- Carregando preserva a largura do botão, anuncia estado e impede envios duplicados.

### Teclado e leitor de tela

Usar `<button>` para ação e `<a>` para navegação. Manter `Enter` e `Space` para botão nativo. Não usar `div` como botão. Ícone sem rótulo visível requer nome acessível. Descrever foco com `:focus-visible`.

## Campo de texto e seleção

### Anatomia

Rótulo persistente, campo, texto de ajuda opcional e mensagem de validação. Placeholder ilustra um formato, não substitui rótulo. Unidade ou moeda fica próxima ao campo e não apenas como placeholder.

### Variantes e estados

- Texto, número, busca, textarea e seleção.
- Padrão, foco, preenchido, leitura, desabilitado, erro e confirmado.
- Borda padrão usa neutro médio. Foco usa anel visível. Erro usa borda e mensagem textual.
- Nunca comunicar erro só pelo laranja ou vermelho.
- Campos financeiros recebem valor e precisão esperada explicitamente.

### Semântica

Associar `<label for>` ao controle. Associar ajuda e erro por `aria-describedby`. Usar `aria-invalid="true"` no erro. Seleções nativas devem continuar utilizáveis por teclado.

## Navegação

### Primária

- Navegação global identifica produto, seção atual e ações de conta.
- Navegação lateral é adequada para áreas com quatro ou mais destinos persistentes.
- Navegação por abas serve para visões irmãs do mesmo contexto, não para passos de um fluxo extenso.
- Breadcrumb é usado quando mostra uma relação real de hierarquia e oferece retorno.

### Estados

Item atual deve combinar indicador visual com `aria-current="page"`. Hover e foco não podem ser confundidos com seleção. Em tela estreita, oferecer menu com botão rotulado, foco controlado e Escape para fechar.

### Classes (1.2.0)

- **Global:** `mw-topbar` com `mw-topbar__brand`, `mw-topbar__nav` (links `mw-nav-link`), `mw-topbar__actions` e `mw-topbar__menu`. O botão de menu aparece abaixo de 720 px e controla um painel com `aria-expanded`, foco controlado e Escape para fechar.
- **Lateral:** `mw-sidenav` com `mw-sidenav__label`, `mw-sidenav__link` e `mw-sidenav__index` opcional em mono. O item atual tem filete laranja de 2 px à esquerda, fundo `--color-surface-soft` e `aria-current="page"`.
- **Abas:** `mw-tabs` (`role="tablist"`) com `mw-tab` (`role="tab"`, `aria-selected`, `aria-controls`) e `mw-tabpanel`. As setas movem entre as abas; só a aba ativa fica em `tabindex="0"`.
- **Breadcrumb:** `<nav class="mw-breadcrumb" aria-label="Você está em">` com uma `<ol>`. O último item tem `aria-current="page"`. O separador `/` é gerado pelo CSS.

## Cartão e painel

Cartão agrupa um assunto e uma ação. Usar superfície branca, borda sutil e raio de 8 px. Evitar cartão aninhado em cartão sem relação funcional clara. Um cartão clicável precisa ser link ou botão e expor um nome compreensível.

## Seleção: checkbox e radio

Usar os inputs nativos dentro de `<label class="mw-choice">`, com o texto em `<span>`. Radios ficam em `<fieldset class="mw-choice-group">` com `<legend>`. A área de toque é de 44 px de altura e o controle mede 20 px. A cor de marcação vem de `accent-color: var(--color-brand-orange)`, e o foco usa `--focus-ring`. Quando a opção está desabilitada, explicar o motivo em texto próximo.

## Etiquetas e status

| Tipo | Cor | Exemplo de texto |
| --- | --- | --- |
| Neutro | Cinza sobre cinza claro | Rascunho |
| Sucesso | Verde sobre fundo verde claro | Concluído |
| Atenção | Ocre sobre fundo âmbar claro | Revisar |
| Erro | Vermelho sobre fundo rosa claro | Bloqueado |
| Informação | Azul escuro sobre azul claro | Atualizado |

Status sempre aparece como texto. O indicador pode usar ponto ou ícone, mas não substitui a palavra.

## Tabela de dados

### Estrutura

- Usar `<table>`, `<caption>`, `<thead>`, `<tbody>`, `<th scope="col">` e cabeçalho de linha onde fizer sentido.
- Alinhar texto à esquerda e números à direita.
- IBM Plex Mono é adequada a IDs, códigos e colunas numéricas.
- Manter a mesma precisão dentro de cada coluna. Mostrar moeda, unidade e período no rótulo.
- Divisores horizontais são preferíveis a linhas verticais densas.
- Linhas selecionáveis precisam de checkbox ou botão nomeado, além da mudança visual.

### Estados e adaptação

Incluir carregamento, vazio, resultado encontrado, erro de leitura e conjunto longo. Em celular, preservar rótulos e permitir leitura sem rolagem horizontal sempre que possível. Se a tabela ficar larga, agrupar cada linha como uma lista de campos nomeados.

## Feedback

| Padrão | Quando usar | Comportamento |
| --- | --- | --- |
| Mensagem inline | Campo, seção ou erro que exige correção | Permanece junto ao conteúdo relacionado |
| Toast | Confirmação breve sem ação obrigatória | Tem anúncio `role="status"`, desaparece sem capturar foco |
| Alerta | Informação importante que exige atenção | Permanece visível enquanto relevante |
| Diálogo | Confirmação ou decisão que interrompe o fluxo | Tem título, foco inicial, Escape e retorno de foco |
| Barra de progresso | Processo com duração e avanço conhecidos | Informa texto e valor, não apenas animação |

Mensagens devem informar o que ocorreu e como resolver. Nunca esconder a origem do erro.

### Mensagem inline e alerta (`mw-alert`)

| Variante | Classe | Marca | Exemplo |
| --- | --- | --- | --- |
| Informação | `mw-alert--info` | `i` | Dados de exemplo |
| Sucesso | `mw-alert--success` | `✓` | Rascunho salvo |
| Atenção | `mw-alert--warning` | `!` | Confirme antes de avançar |
| Erro | `mw-alert--danger` | `×` | Não foi possível ler o arquivo |

Anatomia: `mw-alert__mark` (marca em IBM Plex Mono, `aria-hidden="true"`), `mw-alert__title` (fato, em uma linha) e `mw-alert__content` (o que ocorreu e como resolver). A marca e o título repetem o significado da cor. Alerta que aparece depois de uma ação usa `role="status"` (informação, sucesso) ou `role="alert"` (erro que bloqueia). Não fechar sozinho alertas de atenção ou erro.

## Modal e menu contextual

Usar apenas quando o conteúdo interrompe menos a tarefa do que navegar para uma nova página. Dialog tem nome, descrição quando necessária, foco contido e retorno ao ponto de abertura. Menu contextual possui botão disparador e navegação de teclado previsível. Menu não serve para ocultar ação primária frequente.

### Classes (1.2.0)

- **Diálogo:** `<dialog class="mw-dialog">` nativo, aberto com `showModal()`. Tem `mw-dialog__title` (`aria-labelledby`), `mw-dialog__body` (`aria-describedby`) e `mw-dialog__actions`, com a ação principal à direita. O fundo é escurecido a 48%, a entrada usa `--motion-slow` e, ao fechar, o foco volta ao botão que abriu.
- **Menu:** `mw-menu` (`role="menu"`) com `mw-menu__item` (`role="menuitem"`), `mw-menu__item--danger`, `mw-menu__shortcut` e `mw-menu__separator`. Adicionar `data-open` para a animação de entrada de 180 ms. Setas navegam, Escape fecha e devolve o foco ao disparador.
- **Toast:** `mw-toast-region` (fixo no canto inferior direito) com `mw-toast` (`role="status"`), `mw-toast__mark` e `mw-toast__action` opcional. O fundo usa `--color-ink-strong` e o texto `--color-surface-raised`, e as cores se invertem entre os temas. O toast some sozinho depois de 5 a 8 segundos, sem capturar foco. Mensagens com ação ficam visíveis enquanto o ponteiro ou o foco estiver sobre elas.
- **Progresso:** `mw-progress` com `mw-progress__head` (`mw-progress__label` e `mw-progress__value` em mono) e `mw-progress__track` (`role="progressbar"` com `aria-valuenow` e `aria-valuetext`) contendo `mw-progress__bar`. A barra é laranja sólida. O filete cromático não indica progresso real.

## Navegação por etapa

Para fluxo de várias etapas, exibir quantidade ou nomes de etapas e indicar a atual com texto. Preservar valores anteriores quando o usuário volta. Em fluxo financeiro ou comercial, resumir dados antes de confirmar e mostrar erros junto à etapa de origem.

### Classes (1.2.0)

`<ol class="mw-steps">` com `mw-step`. Usar `mw-step--done` para etapas concluídas (círculo com ✓) e `aria-current="step"` para a atual (círculo laranja com número). A numeração 01, 02… é gerada pelo CSS. Abaixo, `mw-steps__status` escreve "ETAPA 2 DE 3 · REVISÃO".

## Gráficos e métricas

- Rótulos sempre indicam unidade, período e fonte quando relevantes.
- Cor deve ser redundante com forma, posição, padrão ou rótulo.
- Usar laranja para destacar uma série ou decisão importante, não para colorir todas as séries.
- Manter uma alternativa textual ou tabular acessível.
- Evitar eixos cortados que aumentam visualmente a variação.

### Classes (1.2.0)

Gráfico de barras horizontal em `<figure class="mw-chart">`: `mw-chart__title`, `mw-chart__meta` (unidade, período e fonte em mono), `mw-chart__rows` com `mw-chart__row` (`mw-chart__label`, `mw-chart__track` > `mw-chart__bar` com `width` em %, `mw-chart__value`) e `mw-chart__source`. Só a série em decisão recebe `.is-highlight` (laranja); as demais usam `--color-ink-muted`. O valor fica sempre escrito ao lado da barra. Para gráficos mais complexos, seguir as mesmas regras de cor e rótulo com a biblioteca do projeto.

## Filete e placa de marca (1.2.0)

- `mw-signal`: filete cromático de 64 × 2 px (`mw-signal--wide` ocupa 100%). É decorativo, então usar `aria-hidden="true"`.
- `mw-brand-plate`: placa branca que mantém assinaturas de tinta única, como a Northbound, legíveis sobre fundo escuro sem recolorir o arquivo.

## Regras gerais de interação

- Área de toque recomendada de 44 por 44 px, mesmo quando o ícone visual é menor.
- Foco visível em qualquer elemento interativo.
- Hover nunca é o único meio para descobrir uma ação.
- Erros preservam entradas digitadas sempre que possível.
- A interface deve funcionar em zoom de 200 por cento e com teclado.
- Em motion reduzido, manter o estado final sem animar deslocamento, escala ou parallax.
