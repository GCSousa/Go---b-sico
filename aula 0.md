---
title: "Aula 0 — Setup e Lógica"
nav_order: 2
permalink: /aula-0
---

# 🎮 Aula 0: Lógica, Algoritmos e o Mundo do Backend

**Objetivo:** Entender como os computadores "pensam", descobrir o que é o Backend e preparar o ambiente de trabalho para programar em Go.  
**Duração Estimada:** 2 horas (Teoria + Configuração)

---

## 1. Antes do Computador: O que é um Algoritmo?

Muitas pessoas acham que programar é decorar códigos complexos de hackers em ecrãs pretos. Na verdade, a programação é apenas a **tradução** de um pensamento lógico para uma língua que a máquina entenda. Esse pensamento chama-se **Algoritmo**.

Um algoritmo existe muito antes dos computadores. É simplesmente uma **receita passo a passo para resolver um problema**.

### Exemplo Trivial: Fazer um Ovo Estrelado

1. Pegar na frigideira.
2. Colocar óleo.
3. Ligar o fogão.
4. Partir o ovo.
5. **Se** o ovo estiver estragado:
   - Deitar fora e voltar ao passo 4.
   - **Senão**: Colocar na frigideira.
6. Esperar 3 minutos.
7. Servir no prato.

Repara nas palavras **Se** e **Senão** — no código, chamamos a isto de `if` e `else`. A nossa vida é feita de algoritmos e escolhas lógicas.

---

### A Lógica e a Tabela Verdade

Os computadores tomam decisões baseadas em lógica booleana (Verdadeiro ou Falso). Para combinar regras, usamos a **Tabela Verdade**.

Imagina a regra de um guarda noturno para abrir a porta: *"Só abro se a pessoa tiver crachá **E** estiver na lista."*

| Tem Crachá? | Está na Lista? | Operador | Resultado (Abre a porta?) |
| :---------: | :------------: | :------: | :-----------------------: |
| ✅ Sim (True)  | ✅ Sim (True)  | **E (AND)** | ✅ **Sim (True)**      |
| ✅ Sim (True)  | ❌ Não (False) | **E (AND)** | ❌ Não (False)         |
| ❌ Não (False) | ✅ Sim (True)  | **E (AND)** | ❌ Não (False)         |
| ❌ Não (False) | ❌ Não (False) | **E (AND)** | ❌ Não (False)         |

> Se a regra fosse: *"Abro se tiver crachá **OU** se o chefe autorizar"*, bastava **uma** das condições ser verdadeira para a porta abrir (Operador **OU / OR**).

---

## 2. O Palco e os Bastidores: Frontend vs Backend

No desenvolvimento de software moderno, dividimos as aplicações em duas grandes áreas.

### 🎨 O Frontend (O Palco — A Interface)

É tudo o que o utilizador **vê e toca**: os botões, as cores, as animações. Pode ser uma aplicação no telemóvel (iOS/Android) ou um site no navegador (usando HTML, CSS, JavaScript ou React).

### ⚙️ O Backend (Os Bastidores — O Cérebro)

É onde nós vamos trabalhar! O utilizador não vê o backend, mas é ele que faz o trabalho pesado:

- Valida se a password do utilizador está correta.
- Guarda os dados de forma segura na Base de Dados.
- Calcula as regras de negócio (ex: processar um pagamento).

---

### Como é que eles comunicam? (REST API)

Imagina um restaurante:

- O **Frontend** é o cliente sentado à mesa a ler o menu.
- O **Backend** é o cozinheiro na cozinha.
- Eles não falam diretamente — precisam de um empregado de mesa para levar o pedido e trazer a comida.

Esse "empregado de mesa" chama-se **API REST**. O Frontend faz um pedido (ex: `"Dar-me os dados do Pokémon número 25"`) e o Backend responde com uma mensagem estruturada, geralmente em formato **JSON**.

---

### Linguagens de Backend e o Poder do Go

Existem dezenas de linguagens ótimas para construir Backends: Java, C#, Node.js, Python, Ruby e PHP.

**Então, porquê aprender Go (Golang)?**

O Go foi criado pela **Google** em 2009 para resolver problemas de escala gigantescos. Ele junta o melhor de dois mundos: é fácil de ler e escrever (como Python), mas é incrivelmente rápido e consome pouquíssima memória (como C ou C++).

🏢 **Quem usa Go no dia a dia?**

| Empresa | Para quê |
| :------ | :------- |
| **Google** | Escala de infraestrutura interna |
| **Twitch** | Aguentar milhares de streams em direto |
| **Uber** | Calcular rotas em milissegundos |
| **Mercado Livre** | Processar milhões de transacções |
| **Netflix** | Servir conteúdo globalmente |

---

## 3. O Caminho Rápido: Programar Online (Sem Instalar Nada)

Para as primeiras aulas de lógica, **não precisas de instalar nada**. Escreve, testa e guarda o teu código Go diretamente no navegador.

**A melhor ferramenta online:**

1. Acede a: [**The Go Playground** → go.dev/play](https://go.dev/play/)
2. Verás um ecrã com um código básico (`Hello, 世界`).
3. Escreve o teu código na área de texto e clica no botão azul **"Run"** para veres o resultado.

> *Alternativa:* [Replit.com](https://replit.com/) — funciona como um editor completo na nuvem.

---

## 4. O Caminho Profissional: Instalar o Go no Computador

Para projetos reais, ler ficheiros e criar servidores, o Go precisa de estar instalado localmente.

### Passo 1: Descarregar a Linguagem

1. Vai ao site oficial: [**go.dev/dl**](https://go.dev/dl/)
2. Clica no botão de download correspondente ao teu Sistema Operativo.

### Passo 2: Instalação

- **Windows / macOS:** É o clássico "Next → Next → Finish". O instalador configura as variáveis de ambiente automaticamente.

### Passo 3: Testar se funcionou

Abre o **Terminal** (macOS/Linux) ou **PowerShell** (Windows) e executa:

```bash
go version
```

Se o computador responder com algo como `go version go1.24.0 windows/amd64`, estás pronto! ✅

### Passo 4: O Editor de Texto (A tua Mesa de Trabalho)

1. Descarrega e instala o **Visual Studio Code (VS Code)** — gratuito, da Microsoft.
2. Abre o VS Code → clica no ícone de **Extensões** (barra lateral esquerda).
3. Pesquisa por **"Go"** e instala a extensão oficial da Google.

A extensão dá-te superpoderes: colore o código, aponta erros em tempo real e sugere comandos automaticamente.

---

🚀 **Missão da Aula 0 Concluída!** Tens a tua mente afiada para pensar em algoritmos e o teu computador preparado. Na próxima aula, vamos escrever as tuas primeiras linhas de código!
