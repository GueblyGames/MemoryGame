<div align="center">

<img src="https://games.guebly.com.br/gueblygames.png" alt="Guebly Games" width="320"/>

<br/>
<br/>

<img src="./assets/branding/slogan_icon.png" alt="Jogo da Memória — Guebly Games" width="260"/>

<br/>
<br/>

# Jogo da Memória

### Um jogo de memória com tema espacial. Encontre os pares de planetas e vença!

<br/>

[![Linguagem](https://img.shields.io/badge/linguagem-JavaScript-yellow?style=flat-square&logo=javascript)](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)](https://developer.mozilla.org/pt-BR/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)](https://developer.mozilla.org/pt-BR/docs/Web/CSS)
[![Licença](https://img.shields.io/badge/licença-MIT-blue?style=flat-square)](./LICENSE)
[![Status](https://img.shields.io/badge/status-online-brightgreen?style=flat-square)](https://games.guebly.com.br)

<br/>

![Demo do Jogo da Memória](./GitHub/Jogo%20Da%20Memória.gif)

<br/>

[▶ Jogar Agora](https://games.guebly.com.br) · [🌐 Site](https://games.guebly.com.br) · [🛒 Loja](https://store.games.guebly.com.br) · [⚙️ Engine](https://engine.games.guebly.com.br) · [📁 GitHub](https://github.com/GueblyGames)

</div>

---

## Índice

- [Sobre o Jogo](#sobre-o-jogo)
- [Funcionalidades](#funcionalidades)
- [Como Jogar](#como-jogar)
- [Mecânicas do Jogo](#mecânicas-do-jogo)
- [Planetas](#planetas)
- [Estrutura do Projeto](#estrutura-do-projeto)
- [Tecnologias](#tecnologias)
- [Rodando Localmente](#rodando-localmente)
- [Contribuindo](#contribuindo)
- [Sobre a Guebly Games](#sobre-a-guebly-games)
- [Licença](#licença)

---

## Sobre o Jogo

O **Jogo da Memória** é um jogo de cartas com tema espacial desenvolvido pela **Guebly Games**. Navegue pelo cosmos e encontre os pares de planetas — da Terra ao misterioso Plutão — no menor tempo possível!

O jogo possui:
- **20 cartas** organizadas em uma **grade 4×5** (10 pares de planetas)
- **Animação de virada 3D** usando transforms CSS puras
- **Sistema de pontuação** que recompensa velocidade e eficiência
- **Cronômetro** e **contador de jogadas** em tempo real
- **Suporte completo para dispositivos móveis** com layout responsivo

Sem instalação, sem build, sem dependências. Basta abrir o `index.html` em qualquer navegador moderno.

---

## Funcionalidades

| Funcionalidade | Descrição |
|---|---|
| Tema espacial | Fundos imersivos, imagens de planetas e foguete no verso das cartas |
| Animação 3D | Transform CSS `rotateY` para viradas de carta suaves e realistas |
| Pontuação inteligente | Baseada em jogadas + tempo — quanto menor, melhor |
| Nome do jogador | Tela de vitória personalizada com o seu nome |
| Cronômetro | Timer ao vivo no formato MM:SS durante toda a partida |
| Contador de jogadas | Registra quantas tentativas de par você fez |
| Preview inicial | As cartas aparecem brevemente no início e se escondem |
| Design responsivo | Totalmente jogável em dispositivos móveis |
| Embaralhamento Fisher-Yates | Randomização verdadeira do baralho a cada partida |
| Reiniciar | Jogue novamente sem sair da tela do jogo |

---

## Como Jogar

<div align="center">
<img src="./GitHub/Website.png" alt="Screenshot do Jogo" width="680"/>
</div>

<br/>

**1. Digite seu nome**
Abra `index.html` no navegador. Digite seu nome no campo da tela de boas-vindas.

**2. Inicie o jogo**
Clique em **PLAY**. O tabuleiro aparece com todas as 20 cartas viradas por 3 segundos — memorize o máximo que conseguir!

**3. Vire as cartas**
Após o preview, todas as cartas se escondem. Clique em qualquer carta para virá-la e revelar o planeta.

**4. Encontre o par**
Clique em uma segunda carta para tentar combiná-la. Se as duas cartas mostrarem o mesmo planeta — elas permanecem viradas! Se não, as duas voltam ao normal após 1 segundo.

**5. Vença**
Encontre todos os 10 pares para completar o jogo. Sua pontuação final, total de jogadas e tempo serão exibidos na tela de vitória.

**6. Jogar novamente**
Clique em **Jogar novamente** para reiniciar com um baralho novo e embaralhado, ou clique em **Voltar ao início** para inserir um novo nome.

---

## Mecânicas do Jogo

### Virada de Carta

Cada carta é um elemento de 120×120px (80×80px no mobile) com duas faces:

- **Verso** — Imagem de foguete em fundo ciano (`#05c3ff`)
- **Frente** — Imagem do planeta em fundo azul escuro (`#101c2c`)

A virada usa um transform CSS 3D `rotateY(180deg)` com `preserve-3d` e `backface-visibility: hidden` para um efeito de profundidade realista.

### Lógica de Turno

1. Jogador clica em uma carta → carta vira para a frente
2. Jogador clica em uma segunda carta → jogo trava (impede cliques)
3. Se os ícones coincidem → cartas permanecem viradas, trava liberada
4. Se os ícones não coincidem → 1 segundo de espera, ambas voltam ao normal, trava liberada

### Fórmula de Pontuação

```
pontuação = (pares × 1000) / ((jogadas + segundos_decorridos) / 4)
```

Uma pontuação maior significa que você concluiu o jogo mais rápido e com menos tentativas. A pontuação é apenas informativa — a condição de vitória é simplesmente encontrar todos os pares.

### Cronômetro

O cronômetro começa quando o tabuleiro é carregado. Conta no formato `MM:SS` e para quando todos os pares são encontrados. Segundos e minutos são rastreados como dígitos individuais para atualizações de exibição suaves.

### Algoritmo de Embaralhamento

O baralho é randomizado usando o [Algoritmo de Fisher-Yates](https://pt.wikipedia.org/wiki/Algoritmo_de_Fisher-Yates), garantindo distribuição aleatória uniforme a cada início de jogo.

---

## Planetas

O jogo apresenta **10 corpos celestes** do nosso sistema solar — cada um aparecendo duas vezes no baralho:

| Carta | Nome | Carta | Nome |
|:---:|---|:---:|---|
| ☀️ | Sol | 🌍 | Terra |
| 🌙 | Lua | ♂️ | Marte |
| ☿ | Mercúrio | ♃ | Júpiter |
| ♀️ | Vênus | ♄ | Saturno |
| ⛢ | Urano | ♇ | Plutão |

> Todos os versos das cartas mostram um 🚀 **Foguete** em fundo ciano.

---

## Estrutura do Projeto

```
MemoryGame/
│
├── index.html                   # Tela de boas-vindas / login
│
├── Interface/
│   ├── style.css               # Estilos da tela de login
│   ├── script.js               # Armazenamento do nome + lógica da tela de vitória
│   └── Fonte/
│       └── Games.woff          # Fonte customizada "Games Regular"
│
├── assets/
│   ├── index.html              # Tabuleiro principal do jogo
│   ├── style.css               # Estilos do tabuleiro e das cartas
│   │
│   ├── scripts/
│   │   ├── game.js             # Estado do jogo, lógica e pontuação
│   │   └── script.js           # Renderização DOM e interação do usuário
│   │
│   ├── images/
│   │   ├── AstronautSpace.jpg  # Fundo da tela de login
│   │   ├── SpaceMoon.jpg       # Fundo do tabuleiro
│   │   ├── Foguete.png         # Foguete (verso das cartas)
│   │   ├── Terra.png           # Terra
│   │   ├── Lua.png             # Lua
│   │   ├── Marte.png           # Marte
│   │   ├── Mercúrio.png        # Mercúrio
│   │   ├── Vênus.png           # Vênus
│   │   ├── Júpiter.png         # Júpiter
│   │   ├── Saturno.png         # Saturno
│   │   ├── Urano.png           # Urano
│   │   ├── Plutão.png          # Plutão
│   │   └── Sol.png             # Sol
│   │
│   └── branding/
│       ├── icon.png            # Favicon
│       ├── gueblygames.png     # Logo Guebly Games
│       ├── games.png           # Logo branca Guebly Games
│       └── slogan_icon.png     # Logo com slogan
│
├── GitHub/
│   ├── Foguete.png             # Imagem do foguete para a documentação
│   ├── Website.png             # Screenshot do jogo
│   └── Jogo Da Memória.gif     # Demo animado
│
├── README.md                    # Documentação em inglês
├── README.pt-BR.md              # Documentação em português (este arquivo)
└── CONTRIBUTING.md              # Guia de contribuição
```

---

## Tecnologias

| Tecnologia | Uso |
|---|---|
| **HTML5** | Marcação semântica da tela de login e do tabuleiro |
| **CSS3** | Flip 3D de cartas (`rotateY`), CSS Grid, transições, breakpoints responsivos |
| **JavaScript Vanilla** | Lógica do jogo, manipulação do DOM, cronômetro, algoritmo de embaralhamento |
| **localStorage** | Persiste o nome do jogador entre as páginas |
| **CSS `preserve-3d`** | Efeito de profundidade 3D realista no flip |
| **`backface-visibility: hidden`** | Esconde o lado de trás durante a rotação 3D |
| **WebFont Customizada** | `Games.woff` — fonte "Games Regular" para a identidade visual |

Sem bibliotecas externas, sem npm, sem ferramentas de build. Web puro.

---

## Rodando Localmente

Como este é um projeto frontend puro sem dependências server-side, executá-lo é simples:

```bash
# Clone o repositório
git clone https://github.com/GueblyGames/JogoDaMemoria.git

# Acesse a pasta do projeto
cd JogoDaMemoria

# Abra no navegador
open index.html       # macOS
start index.html      # Windows
xdg-open index.html   # Linux
```

Ou simplesmente dê dois cliques em `index.html` no explorador de arquivos.

> **Dica:** Para a melhor experiência, use um servidor local para evitar restrições de CORS com imagens locais. Você pode usar a extensão [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) para VS Code.

---

## Contribuindo

Contribuições são bem-vindas! Leia o [CONTRIBUTING.md](./CONTRIBUTING.md) para o guia completo.

**Início rápido:**

```bash
# 1. Faça um fork do repositório no GitHub
# 2. Clone seu fork
git clone https://github.com/SEU_USUARIO/JogoDaMemoria.git

# 3. Crie uma branch de funcionalidade
git checkout -b feat/minha-funcionalidade

# 4. Faça suas alterações e commit
git commit -m "feat: descreva sua mudança"

# 5. Envie e abra um Pull Request
git push origin feat/minha-funcionalidade
```

**Sugestões de contribuição:**
- Adicionar novas cartas de planetas/corpos celestes (Netuno, cometas, asteroides)
- Adicionar níveis de dificuldade (fácil: 3×4, médio: 4×5, difícil: 5×6)
- Adicionar música de fundo e efeitos sonoros
- Adicionar um placar global de pontuações
- Adicionar temas de cartas (animais, países, etc.)
- Melhorar acessibilidade (navegação por teclado, suporte a leitores de tela)

---

## Sobre a Guebly Games

<div align="center">

<img src="https://games.guebly.com.br/slogan_icon.png" alt="Criando Universos, Conectando Pessoas" width="300"/>

<br/>
<br/>

A **Guebly Games** é um estúdio brasileiro de jogos dedicado a criar jogos web divertidos, acessíveis e criativos.

Além dos jogos, a Guebly desenvolve sua própria **engine** e uma **loja digital** para desenvolvedores indie — um ecossistema completo para a próxima geração de criadores de games.

<br/>

| | |
|---|---|
| 🌐 **Site** | [games.guebly.com.br](https://games.guebly.com.br) |
| 🛒 **Loja** | [store.games.guebly.com.br](https://store.games.guebly.com.br) |
| ⚙️ **Game Engine** | [engine.games.guebly.com.br](https://engine.games.guebly.com.br) |
| 💻 **GitHub** | [github.com/GueblyGames](https://github.com/GueblyGames) |
| 📧 **Contato** | [contato@guebly.com.br](mailto:contato@guebly.com.br) |

<br/>

*"Criando Universos, Conectando Pessoas"*

<br/>

<img src="https://games.guebly.com.br/gueblyicon.png" alt="Ícone Guebly Games" width="64"/>

</div>

---

## Licença

```
MIT License

Copyright (c) 2026 Guebly Games

A permissão é concedida, gratuitamente, a qualquer pessoa que obtenha uma cópia
deste software e dos arquivos de documentação associados (o "Software"), para lidar
com o Software sem restrições, incluindo, sem limitação, os direitos de usar,
copiar, modificar, mesclar, publicar, distribuir, sublicenciar e/ou vender cópias
do Software, sujeito às seguintes condições:

O aviso de copyright acima e este aviso de permissão deverão ser incluídos em todas
as cópias ou partes substanciais do Software.

O SOFTWARE É FORNECIDO "NO ESTADO EM QUE SE ENCONTRA", SEM GARANTIA DE QUALQUER
TIPO, EXPRESSA OU IMPLÍCITA, INCLUINDO MAS NÃO SE LIMITANDO ÀS GARANTIAS DE
COMERCIALIZAÇÃO, ADEQUAÇÃO A UM FIM ESPECÍFICO E NÃO VIOLAÇÃO. EM NENHUM CASO OS
AUTORES OU DETENTORES DOS DIREITOS AUTORAIS SERÃO RESPONSÁVEIS POR QUALQUER
REIVINDICAÇÃO, DANO OU OUTRA RESPONSABILIDADE, SEJA EM UMA AÇÃO DE CONTRATO, ATO
ILÍCITO OU DE OUTRA FORMA, DECORRENTE DE, FORA DE OU EM CONEXÃO COM O SOFTWARE OU
O USO OU OUTRAS NEGOCIAÇÕES NO SOFTWARE.
```

---

<div align="center">

Feito com ❤️ pela [Guebly Games](https://games.guebly.com.br)

<img src="https://games.guebly.com.br/games.png" alt="Guebly Games" width="160"/>

</div>
