---
title: Início
nav_order: 1
description: "Formação completa em Go (Golang) — do zero ao backend escalável."
permalink: /
---

# 🚀 Formação Go (Golang): Do Zero ao Backend Escalável

Bem-vindo à trilha de formação em Go! Este material foi desenhado para levar você do zero absoluto até o nível de produção de backend.

> **🎯 Metodologia:** Construção progressiva. Você aprenderá como a memória funciona na base antes de usar abstrações dinâmicas de alto nível. Todo o conhecimento será aplicado em um **Projeto Único (Simulador de Batalhas Pokémon)**, que evoluirá de um simples script de terminal para uma API REST de alta performance.

---

## 🟢 FASE 1: Nível Iniciante — A Base de Concreto

*Foco: Sintaxe, controle de fluxo e organização de memória.*

### 📦 Aulas

| Aula | Tópicos |
| :--- | :------ |
| [Aula 0 — Setup e Lógica](./aula-0) | Algoritmos, Frontend vs Backend, Go Playground, instalação do Go e VS Code |
| [Aula 1 — Fundamentos e Decisões](./aula-1) | Variáveis, tipos, operadores, `if/else`, `switch` e funções |
| [Aula 2 — Arranjos e Iterações](./aula-2) | Arrays, strings, as quatro formas do `for` e laços aninhados |
| Aula 3 — Arsenal Dinâmico | Slices com `append()` e Maps chave-valor *(em breve)* |
| Aula 4 — Structs | Tipos customizados: construindo a struct `Pokemon` *(em breve)* |
| Aula 5 — Ponteiros e Métodos | `&` e `*`, passagem por referência, métodos com receivers *(em breve)* |

### 🏆 Projeto Fase 1: Simulador de Batalha (Console)

**Missão:** Criar um jogo de terminal onde dois Pokémon batalham entre si.  
**Validação:** `for` infinito para turnos, leitura de teclado, ponteiros e métodos obrigatórios para a vida diminuir de verdade na memória.

---

## 🟡 FASE 2: Nível Intermediário — Sistemas e I/O

*Foco: Modularizar o código e interagir com o mundo exterior.*

### 📦 Aulas

| Aula | Tópicos |
| :--- | :------ |
| Aula 6 — Módulos e Visibilidade | `go mod init`, `go get`, público vs privado *(em breve)* |
| Aula 7 — Tratamento de Erros | A filosofia Go: erros são valores, `if err != nil` *(em breve)* |
| Aula 8 — Arquivos e I/O | Pacotes `os` e `io`, leitura e escrita de ficheiros *(em breve)* |
| Aula 9 — JSON | Marshalling/Unmarshalling, tags estruturais *(em breve)* |
| Aula 10 — Interfaces | Polimorfismo e contratos flexíveis *(em breve)* |

### 🏆 Projeto Fase 2: A Pokédex de Arquivos

**Missão:** Ler uma Pokédex de um ficheiro `pokemons.json`, deixar o utilizador escolher o seu time e guardar o resultado em `historico.txt`.

---

## 🔴 FASE 3: Nível Avançado — O Padrão de Mercado

*Foco: Alta performance, servidores Web, concorrência e arquitetura profissional.*

### 📦 Aulas

| Aula | Tópicos |
| :--- | :------ |
| Aula 11 — Concorrência | Goroutines, Channels, `sync.WaitGroup` *(em breve)* |
| Aula 12 — Testes Unitários | Pacote `testing`, ficheiros `_test.go`, TDD básico *(em breve)* |
| Aula 13 — APIs REST | `net/http`, roteamento, requests, responses e status codes *(em breve)* |

### 🏆 Projeto Fase 3: Backend de Batalha (API REST)

**Missão:** Transformar o simulador de terminal num servidor Web completo na porta `8080`, com endpoints HTTP, Goroutines para múltiplas batalhas simultâneas e respostas em JSON validadas por testes unitários.

---

> Use o menu lateral para navegar entre as aulas disponíveis.
