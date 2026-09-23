# Implementação

## Início rápido

Inclua os tokens e os estilos de componente no HTML da página:

```html
<link rel="stylesheet" href="tokens.css">
<link rel="stylesheet" href="components.css">
```

As fontes Archivo e IBM Plex Mono usam arquivos locais existentes em `branding/northbound-v2/fonts/`. Preserve as licenças SIL OFL existentes ao redistribuir os arquivos de fonte.

## Exemplo de controle

```html
<button class="mw-button mw-button--primary" type="button">
  Continuar
</button>
```

As classes `mw-button--secondary`, `mw-button--quiet`, `mw-button--text`, `mw-button--danger`, `mw-button--small` e `mw-button--large` oferecem as variantes documentadas em `COMPONENTS.md`.

## Exemplo de campo acessível

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

## Adaptação de marca

1. Manter os arquivos oficiais de logo da marca que aparece na interface.
2. Usar a identidade MG Works em páginas institucionais e comunicação corporativa.
3. Usar a identidade Northbound em telas do produto Northbound.
4. Compartilhar cores de interface, tipografia, espaçamento e acessibilidade quando isso não apagar diferenças entre as marcas.
5. Documentar qualquer exceção local junto ao produto que a introduz.

## Atualização de tokens

`tokens.json` documenta origem, finalidade e categorias. `tokens.css` tem variáveis CSS planas para aplicação direta. Ao mudar um token:

1. Atualizar o valor estruturado e o CSS de tokens.
2. Rever combinações de contraste e exemplos em `index.html`.
3. Atualizar `TOKENS.md`, `components.css` quando necessário e o histórico.
4. Marcar alterações incompatíveis com versão maior e orientar migração.

Este pacote ainda não usa um compilador de tokens. A sincronização entre JSON e CSS é editorial nesta versão.
