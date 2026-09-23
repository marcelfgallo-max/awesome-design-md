# MG Works Design System

Pacote autocontido para estudar e integrar o sistema visual MG Works em outro projeto. Inclui o catálogo HTML, fundamentos, tokens, componentes, exemplos, previews mobile, assinaturas de marca e as fontes locais usadas pelo catálogo.

## Usar com Claude Code

1. Extraia a pasta `MG-Works-Design-System` dentro do repositório que receberá o sistema, ou em um local acessível ao Claude Code.
2. Abra `PROMPT-PARA-CLAUDE-CODE.md`, ajuste o caminho indicado para a pasta extraída e cole o conteúdo no Claude Code.
3. O prompt pede ao Claude para ler a documentação, entender a arquitetura existente e integrar os tokens e padrões sem substituir a identidade ou as funcionalidades próprias do projeto.

## Catálogo visual

Abra `branding/mgworks-system-v1/index.html` em um navegador. Os logos e fontes usados pelo catálogo estão organizados nas pastas irmãs para manter os caminhos locais funcionando. A pasta do design system também tem `mobile-preview.png` para visualização em dispositivos que não exibem SVG.

## Conteúdo

- `branding/mgworks-system-v1/`, HTML, CSS, tokens JSON, guia, especificação de componentes e exemplos de implementação.
- `branding/mgworks-v1/`, apenas as quatro assinaturas em SVG usadas pelo catálogo.
- `branding/northbound-v2/logo-primary.svg`, marca usada na seção de aplicações do catálogo.
- `branding/northbound-v2/fonts/`, Archivo e IBM Plex Mono, com os avisos e licenças SIL Open Font License originais.

MG Works permanece um nome provisório. O pacote documenta uma direção visual, não uma verificação de disponibilidade ou autorização de uso comercial de marca.
