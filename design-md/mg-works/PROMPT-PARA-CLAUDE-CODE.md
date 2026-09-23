# Prompt para Claude Code

Cole este texto no Claude Code depois de extrair o pacote. Se a pasta estiver em outro local, ajuste o caminho abaixo.

---

Quero integrar ao projeto atual o design system que está em:

`MG-Works-Design-System/branding/mgworks-system-v1/`

Use os demais arquivos dentro de `MG-Works-Design-System/branding/` como assets necessários. Se o caminho não existir a partir da raiz deste repositório, localize a pasta extraída antes de começar.

Trate os arquivos incluídos como a fonte de verdade do sistema visual. Leia `README.md`, `GUIDE.md`, `TOKENS.md`, `COMPONENTS.md` e `IMPLEMENTATION.md` do design system, depois examine `tokens.json`, `tokens.css`, `components.css` e o catálogo `index.html`. Consulte também os logos e as fontes empacotados quando precisar entender os assets exatos.

Integre o sistema ao projeto existente de ponta a ponta, com a melhor adaptação possível à arquitetura e às convenções já usadas. Aplique os tokens, a tipografia Archivo e IBM Plex Mono, hierarquia, cores, espaçamento, composição, componentes, estados, padrões responsivos e orientações de acessibilidade documentados no pacote. Reutilize ou mapeie os estilos e componentes existentes quando isso evitar duplicação. Não faça uma cópia estática do catálogo no lugar do produto.

Antes de editar, identifique o framework, o ponto de entrada, as folhas de estilo globais, os componentes compartilhados e as telas relevantes. Em seguida faça a integração, mantendo rotas, funcionalidades, conteúdo, dados, autenticação e comportamentos já existentes. Preserve o nome e a marca próprios do projeto. Use MG Works somente como referência do sistema visual, salvo se o próprio projeto já for da MG Works. Não invente um objetivo de produto que não esteja no projeto.

Mantenha as mudanças concentradas no sistema visual e nas adaptações necessárias para aplicá-lo. Evite dependências novas, a menos que a arquitetura existente realmente precise delas. Não apague conteúdo ou estilos existentes sem substituição funcional. Se algum token ou padrão entrar em conflito com requisitos reais do projeto, preserve o comportamento e registre a decisão.

Ao concluir, confira as telas em larguras desktop e mobile e rode os comandos de validação que já existirem no projeto, se forem aplicáveis. Não crie uma bateria nova de testes. Resuma os arquivos e componentes alterados, as decisões de adaptação e qualquer parte do sistema que não tenha sido possível aplicar.

