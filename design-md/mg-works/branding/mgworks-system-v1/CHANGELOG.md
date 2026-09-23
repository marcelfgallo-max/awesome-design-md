# Histórico

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
