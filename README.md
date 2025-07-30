# BrunexBots

![Licença](https://img.shields.io/badge/license-MIT-blue.svg)
![Versão](https://img.shields.io/badge/version-1.0.0-brightgreen.svg)
![Node.js](https://img.shields.io/badge/node.js-%3E%3D14.x-yellow.svg)

Um sistema de bots para o jogo Slither.io, O projeto consiste em um servidor backend em Node.js que gerencia os bots e uma extensão para navegador (Chrome) que injeta uma interface de controle no jogo e captura as informações necessárias para o funcionamento dos bots.

## 📸 Screenshot

![BrunexBots]

---

## ✨ Funcionalidades

- **Controle de Múltiplos Bots**: Inicie e gerencie dezenas de bots simultaneamente.
- **Seguir o Jogador**: Os bots são programados para seguir a posição da sua cobra no mapa.
- **Interface Integrada**: Uma interface simples é injetada diretamente na tela do jogo para facilitar o controle.
- **Movimento Aleatório**: Ative um modo de movimento aleatório para os bots.
- **Suporte a Proxy**: Utiliza proxies SOCKS e HTTP para distribuir as conexões dos bots e evitar bloqueios de IP.
- **Console Interativo**: O servidor exibe um painel de status com um design atraente no terminal.

---

## ⚙️ Pré-requisitos

Antes de começar, você vai precisar ter o seguinte instalado:
- [Node.js](https://nodejs.org/en/) (versão 14 ou superior)
- npm (geralmente vem com o Node.js)
- Um navegador baseado em Chromium (Google Chrome, Brave, etc.)

---

## 🚀 Instalação e Configuração

Siga estes passos para configurar e rodar o projeto:

**1. Clone o Repositório**
```bash
git clone https://github.com/Brunexgmaer09/BrunexBots.git
cd BrunexBots
```

**2. Instale as Dependências do Backend**
Execute o comando abaixo na raiz do projeto para instalar as bibliotecas Node.js necessárias.
```bash
npm install
```

**3. Configure os Proxies (Passo Crucial!)**
O sistema de bots precisa de proxies para funcionar corretamente. Você precisa fornecer uma lista de proxies.

- **Proxies SOCKS**: Abra o arquivo `config/proxies.txt` e adicione seus proxies SOCKS, um por linha, no formato `ip:porta`.
- **Proxies HTTP**: Abra o arquivo `config/httpProxy.txt` e adicione seus proxies HTTP, um por linha, no formato `ip:porta`.

> **Aviso**: O bot não funcionará sem uma lista de proxies válidos. Você pode encontrar listas de proxies gratuitos na internet, mas a qualidade e a velocidade podem variar.

**4. Instale a Extensão no Navegador**
- Abra seu navegador (Ex: Google Chrome).
- Navegue até `chrome://extensions`.
- Ative o **"Modo de Desenvolvedor"** (geralmente um botão no canto superior direito).
- Clique em **"Carregar sem compactação"** (ou "Load unpacked").
- Selecione a pasta `BrunexBots-Extensao` que está dentro do projeto.
- A extensão "BrunEX Bots" deverá aparecer na sua lista de extensões.

---

## ▶️ Como Usar

1. **Inicie o Servidor de Bots**
   Na raiz do projeto, execute o comando:
   ```bash
   node slither-bots.js
   ```
   Ou simplesmente execute o arquivo `INICIAR_SERVIDOR.bat` no Windows.
   Você deverá ver o painel de controle do servidor no seu terminal.

2. **Abra o Slither.io**
   Com o servidor rodando, acesse o site [slither.io](http://slither.io/) no seu navegador.

3. **Inicie os Bots**
   - A interface da extensão deve aparecer no topo da tela do jogo.
   - Clique no botão **"Iniciar Bots"**. A extensão irá detectar o IP do servidor do jogo e enviá-lo para o seu backend.
   - Os bots começarão a se conectar ao servidor e a seguir sua cobra.

4. **Controle os Bots**
   - **Toggle Random**: Ativa/desativa o movimento aleatório dos bots.
   - **Toggle ZigZag**: Ativa/desativa o movimento em zigue-zague.

---

## 📂 Estrutura do Projeto

```
.
├── BrunexBots-Extensao/  # Código da extensão do navegador
│   ├── content.js        # Script de conteúdo que injeta os outros scripts
│   ├── inject.js         # Injeta a UI e a lógica de comunicação no jogo
│   ├── manifest.json     # Arquivo de manifesto da extensão
│   └── position-tracker.js # Intercepta o WebSocket para rastrear a posição
│
├── config/               # Arquivos de configuração
│   ├── httpProxy.txt     # Lista de proxies HTTP
│   └── proxies.txt       # Lista de proxies SOCKS
│
├── src/                  # Código-fonte do backend (Node.js)
│   ├── Bot.js            # Classe que representa um único bot
│   ├── BotManager.js     # Gerencia todos os bots
│   ├── SocketHandler.js  # Lida com a comunicação via Socket.io com a extensão
│   └── ...               # Outros arquivos de utilidade
│
├── slither-bots.js       # Ponto de entrada principal do servidor backend
├── package.json          # Dependências do projeto Node.js
└── README.md             # Este arquivo
```

---

## ⚠️ Aviso Legal

Este projeto foi criado estritamente para fins educacionais e de aprendizado sobre Node.js, WebSockets e extensões de navegador. O uso de bots em jogos online pode violar os termos de serviço do jogo e resultar em banimento da sua conta. Use por sua conta e risco. O autor não se responsabiliza por qualquer consequência do uso deste software.

---

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.
