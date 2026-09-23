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

## Cartão e painel

Cartão agrupa um assunto e uma ação. Usar superfície branca, borda sutil e raio de 8 px. Evitar cartão aninhado em cartão sem relação funcional clara. Um cartão clicável precisa ser link ou botão e expor um nome compreensível.

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

## Navegação por etapa

Para fluxo de várias etapas, exibir quantidade ou nomes de etapas e indicar a atual com texto. Preservar valores anteriores quando o usuário volta. Em fluxo financeiro ou comercial, resumir dados antes de confirmar e mostrar erros junto à etapa de origem.

## Gráficos e métricas

- Rótulos sempre indicam unidade, período e fonte quando relevantes.
- Cor deve ser redundante com forma, posição, padrão ou rótulo.
- Usar laranja para destacar uma série ou decisão importante, não para colorir todas as séries.
- Manter uma alternativa textual ou tabular acessível.
- Evitar eixos cortados que aumentam visualmente a variação.

## Regras gerais de interação

- Área de toque recomendada de 44 por 44 px, mesmo quando o ícone visual é menor.
- Foco visível em qualquer elemento interativo.
- Hover nunca é o único meio para descobrir uma ação.
- Erros preservam entradas digitadas sempre que possível.
- A interface deve funcionar em zoom de 200 por cento e com teclado.
- Em motion reduzido, manter o estado final sem animar deslocamento, escala ou parallax.
