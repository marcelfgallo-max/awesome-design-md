# Tokens visuais

Fonte estruturada: `tokens.json`. Implementação web: `tokens.css`.

## Cor

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

### Pares de feedback

| Uso | Texto ou ícone | Fundo |
| --- | --- | --- |
| Sucesso | `--color-feedback-success` `#176B45` | `--color-feedback-success-soft` `#E4F2EA` |
| Atenção | `--color-feedback-warning` `#835000` | `--color-feedback-warning-soft` `#FFF1D8` |
| Erro | `--color-feedback-danger` `#B42318` | `--color-feedback-danger-soft` `#FDE8E7` |
| Informação | `--color-feedback-info` `#005A86` | `--color-feedback-info-soft` `#E2F3FA` |

Sempre mostrar também um rótulo ou ícone com nome acessível. Feedback deve informar condição e próximo passo quando isso ajudar a resolver.

### Filete cromático

`--color-signal-gradient` define uma progressão horizontal do laranja de marca para névoa e azul claro. Reservar para uma linha curta ou uma borda decorativa. Não aplicar a texto, logotipo, controles de estado ou fundos extensos.

### Regras de contraste

- Usar texto preto sobre laranja e branco sobre preto.
- Sobre branco, texto principal usa `--color-ink-default` ou `--color-ink-strong`.
- `--color-ink-subtle` não identifica erro, estado ou instrução indispensável. Usar em informação complementar com tamanho e contraste adequados.
- Em dados, parear a cor com nome, forma ou padrão.

## Tema escuro

Adicionado na versão 1.1.0. Ativar com `data-theme="dark"` no `<html>` ou em um contêiner; sem o atributo, vale o tema claro. Cores de identidade (`--color-brand-*`, `--color-reference-*`) e `--color-signal-gradient` não mudam entre temas. Texto preto sobre laranja continua valendo no escuro.

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

No tema escuro, usar `logo-reverse.svg` e o avatar preto. Laranja de marca sobre `#0E0E0E` mede 5.7:1 e pode ser usado como texto de destaque grande.

### Tokens de componente

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

## Tipografia

### Famílias

| Token | Família | Uso |
| --- | --- | --- |
| `--font-family-sans` | Archivo | Títulos, texto, navegação e interface |
| `--font-family-mono` | IBM Plex Mono | Códigos, valores tabulares, versão e metadados |

### Tamanhos

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

### Pesos e linhas

- Pesos: 400 regular, 500 médio, 600 semibold, 700 bold.
- `--line-height-tight`: 1.05 para display curto.
- `--line-height-heading`: 1.12 para títulos.
- `--line-height-body`: 1.5 para interface e texto corrido.
- `--line-height-relaxed`: 1.65 para textos longos.
- `--letter-spacing-label`: 0.08em para rótulos curtos em caixa alta.

## Espaçamento

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

## Forma, borda e profundidade

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

## Layout e movimento

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
