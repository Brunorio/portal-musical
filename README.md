# Portal Musical - App Hub

Um portal/launchpad elegante, limpo e minimalista em tons de cinza para listar e acessar rapidamente os sistemas, ferramentas e links do ecossistema do **Portal Musical** (Secretaria Musical de Presidente Prudente - SP).

Este projeto foi construído usando tecnologias simples e leves (HTML, CSS e JavaScript puros) com suporte dinâmico a dados locais e ícones via **Iconify**.

---

## 🚀 Como Executar o Projeto

Como o projeto faz requisições locais (`fetch`) para carregar a lista de aplicativos de um arquivo JSON, **ele precisa ser executado através de um servidor web local** para evitar erros de CORS no navegador.

### Opção 1: Usando Node/Npx (Recomendado)
Se você tem o Node.js instalado, execute na pasta do projeto:
```bash
npx http-server -p 8080
```
Depois, acesse: [http://localhost:8080](http://localhost:8080)

### Opção 2: Usando Python
Se você possui o Python instalado, execute na pasta do projeto:
```bash
python3 -m http.server 8080
```
Depois, acesse: [http://localhost:8080](http://localhost:8080)

---

## ⚙️ Configuração dos Aplicativos

A lista de aplicativos renderizada em tela é totalmente dinâmica e carregada a partir do arquivo `apps.json`. Por motivos de segurança e flexibilidade, **este arquivo está configurado no `.gitignore` e não deve ser versionado**.

### Como configurar os seus links:

1. Duplique o arquivo de modelo `apps.example.json` e salve-o como `apps.json`:
   ```bash
   cp apps.example.json apps.json
   ```
2. Abra o arquivo `apps.json` criado e customize a lista de aplicativos com a seguinte estrutura:

```json
[
  {
    "name": "Nome do Aplicativo",
    "link": "https://link-do-seu-sistema.com",
    "icon": "identificador-do-icone-iconify"
  }
]
```

### Escolhendo Ícones do Iconify:
Para customizar os ícones nos cards, você pode buscar por qualquer pacote de ícone no [Iconify Design Search](https://iconify.design/) e preencher o campo `"icon"` com a tag correspondente (ex: `mdi:music-clef-treble`, `ph:headphones`, `logos:spotify-icon`).

---

## ✨ Funcionalidades do Portal

- **Design Minimalista (Clean Gray Theme)**: Cores balanceadas em tons de cinza, cantos arredondados finos, e elevações suaves que trazem uma sensação moderna e profissional.
- **Filtro de Busca em Tempo Real**: Campo de pesquisa rápido que filtra os aplicativos conforme o usuário digita.
- **Carregamento Assíncrono com Estados**: Exibe esqueletos de carregamento animado (skeletons) enquanto busca os dados e exibe um estado de configuração amigável caso o `apps.json` ainda não exista.
- **Modo de Demonstração (Fallback)**: Caso o servidor não encontre o `apps.json`, o usuário pode clicar em um botão para pré-visualizar a página com os dados de exemplo de `apps.example.json`.
- **Copyright Dinâmico**: O ano do rodapé da página é gerado automaticamente com base na data do sistema do cliente.
- **Favicon Personalizado**: Favicon em SVG leve e responsivo contendo um ícone de nota musical minimalista.

---

## 📁 Estrutura de Arquivos

- `index.html` — Estrutura semântica e script Javascript de controle.
- `style.css` — Estilos visuais e variáveis de cores em tons de cinza.
- `favicon.svg` — Favicon vetorial do portal.
- `apps.example.json` — Modelo de exemplo/demonstração.
- `apps.json` — Arquivo local customizado pelo administrador do portal (ignorado pelo git).
- `.gitignore` — Impede que `apps.json` seja sincronizado no repositório.
