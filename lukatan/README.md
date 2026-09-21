# 🏝️ Lukatan - Catan Multiplayer Web & Mobile

Este projeto é uma versão adaptada para jogo online multiplayer do clássico Catan (Settlers of Catan / Card Game), otimizado para navegadores de celular e desktop com renderização em tempo real.

---

## 📌 Principais Repositórios Open Source Analisados

| Repositório | Stack Tecnológica | Suporte a Firebase? | Renderização / Mobile | Multiplayer | Status / Regras |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **[leslieyip02/catan](https://github.com/leslieyip02/catan)** ⭐ | React 18, TypeScript, Firebase SDK v9 | **Nativo (Firebase Realtime DB + Hosting)** | CSS Grid Hexagonal responsivo (leve e rápido no celular) | Salas com código (Host/Join via Firebase) | Regras base, trocas, cartas de desenvolvimento e chat |
| **[Viral-Doshi/catan](https://github.com/Viral-Doshi/catan)** ⭐ | React, Vite, Node.js, Express, Socket.io | Via Cloud Run / Node | Tabuleiro SVG/CSS dinâmico, animações, tema escuro | Socket.io em tempo real com salas de 6 letras | Regras completas, 2 a 6 jogadores, expansão 5-6 |
| **[SlavaPush/catan-card-game](https://github.com/SlavaPush/catan-card-game)** | React, Redux Saga, Express, WebSocket, MongoDB | Adaptável | Baseado em cartas (UI específica do Catan Card Game) | WebSockets (2 jogadores) | Focado nas cartas de Catan (Rivals for Catan) |
| **[itaylayzer/catan.io](https://github.com/itaylayzer/catan.io)** | Next.js, TypeScript, PeerJS (WebRTC) | Não (usa P2P) | WebRTC direto entre dispositivos | P2P (Peer-to-Peer) | Em desenvolvimento |

---

## 🚀 Como Hospedar

### Opção 1: Hospedagem 100% Gratuita no Firebase (Recomendado: `leslieyip02/catan`)
Essa opção não gasta recursos da sua máquina e não requer servidor backend ligado 24/7. O Firebase sincroniza o estado dos tabuleiros e cartas em tempo real entre os celulares.

1. **Criar projeto no Firebase:**
   - Acesse o [Firebase Console](https://console.firebase.google.com/) e crie um projeto novo.
   - Ative o **Realtime Database** (em modo de teste ou configurando as regras de leitura/escrita).
   - Ative o **Authentication** (habilite o login "Anônimo").

2. **Configurar as credenciais:**
   - Obtenha as credenciais do seu app web no console do Firebase e configure em `firebaseConfig`.

3. **Deploy:**
   ```bash
   npm install -g firebase-tools
   firebase login
   firebase init
   npm run build-prod
   firebase deploy
   ```
   Você receberá uma URL `https://seu-projeto.web.app` que pode ser aberta direto no celular.

---

### Opção 2: Hospedagem na sua Máquina Local (Jogar pelo Celular no Wi-Fi)

1. Conecte o computador e os celulares na mesma rede Wi-Fi.
2. Descubra o IP local do seu computador (`ipconfig` no Windows, ex: `192.168.1.50`).
3. Inicie o servidor da aplicação.
4. No navegador do celular (Chrome/Safari), acesse:
   ```
   http://192.168.1.50:<PORTA>
   ```

---

## 📱 Requisitos para Celular
- Suporte a toque (touch-friendly) para seleção de hexágonos, cartas e portos.
- Interface responsiva com viewport travado para evitar zoom indesejado durante a partida:
  `<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">`
