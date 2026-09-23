# Histórico

## 1.2.0 · 23 de setembro de 2026

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

## 1.1.0 · 23 de setembro de 2026

- **Tema escuro opcional.** Novo bloco `[data-theme="dark"]` em `tokens.css` e `themes.dark` em `tokens.json`.
  - Motivo: oferecer leitura em ambiente escuro e interfaces de produto que pedem superfície escura.
  - Impacto: nenhum no tema claro. Brand, reference e o filete cromático não mudam.
  - Migração: nenhuma obrigatória. Para ativar, aplicar `data-theme="dark"` no `<html>` ou em um contêiner e trocar o logo por `logo-reverse.svg`.
- **Tokens de componente.** Valores fixos de `components.css` viraram tokens (`--color-button-secondary-ink`, `--color-control-disabled-*`, `--color-feedback-danger-hover`, `--color-chip-neutral-*`, `--color-table-head`), com os mesmos valores no tema claro.
  - Impacto: visual idêntico no tema claro. O texto do botão secundário passa a vir de `--color-button-secondary-ink` (`#000000`).
- **Movimento documentado.** Tabela de uso de `--motion-fast`, `--motion-base`, `--motion-slow` e `--motion-ease-standard` em `GUIDE.md`.
- **Alertas.** Variantes de sucesso e erro documentadas em `COMPONENTS.md`, com marca, título e papel ARIA, e demonstradas no catálogo.

## 1.0.0 · 22 de setembro de 2026

- Versão inicial para avaliação.
