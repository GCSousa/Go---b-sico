---
title: "▶ Playground Go"
nav_order: 10
permalink: /playground
---

# ▶ Playground Go Online

Escreva e execute código Go diretamente no navegador, sem instalar nada!

> **Dica:** Clique em **"Run"** (ou pressione `Ctrl+Enter`) para executar. Use **"Share"** para salvar e compartilhar o link do seu código.

<div style="border: 2px solid #e8e8e8; border-radius: 10px; overflow: hidden; margin: 1.5rem 0; box-shadow: 0 4px 16px rgba(0,0,0,0.08);">
  <div style="background: #00acd7; padding: 0.6rem 1rem; display: flex; align-items: center; gap: 0.5rem;">
    <span style="color: white; font-weight: 600; font-size: 0.95rem;">🐹 Go Playground</span>
    <a href="https://go.dev/play/" target="_blank" style="margin-left: auto; color: white; font-size: 0.8rem; text-decoration: none; opacity: 0.85;">Abrir em nova aba ↗</a>
  </div>
  <iframe
    src="https://go.dev/play/"
    style="width: 100%; height: 600px; border: none; display: block;"
    title="Go Playground"
    loading="lazy">
  </iframe>
</div>

---

## 💡 Snippets para Começar

Experimente copiar e colar estes exemplos no playground:

### Olá, Mundo!

```go
package main

import "fmt"

func main() {
    fmt.Println("Olá, Mundo!")
}
```

### Variáveis e Tipos

```go
package main

import "fmt"

func main() {
    const jogo = "Pokémon"
    var nivel int = 5
    vida := 35.5

    fmt.Println("Jogo:", jogo)
    fmt.Println("Nível:", nivel)
    fmt.Println("Vida:", vida)
}
```

### Função com Retorno Duplo

```go
package main

import "fmt"

func BatalhaPokemon(hpAtual int, dano int) (int, bool) {
    var hpRestante int
    var desmaiou bool

    hpRestante = hpAtual - dano

    if hpRestante <= 0 {
        hpRestante = 0
        desmaiou = true
    } else {
        desmaiou = false
    }

    return hpRestante, desmaiou
}

func main() {
    hp, caiu := BatalhaPokemon(45, 60)
    fmt.Println("HP restante:", hp)
    fmt.Println("Desmaiou?", caiu)
}
```
