---
title: "Aula 2 — Arranjos e Laços"
nav_order: 4
permalink: /aula-2
---

# 📑 Aula 2: Arranjos, Caracteres e Iterações em Go (Golang)

**Objetivo:** Entender coleções de dados (Arrays/Strings) e como repetir ações no código usando o `for`.  
**Público:** Iniciantes em Programação  
**Duração:** 4 horas (Teoria + Prática)

---

## 1. Arranjos (Arrays) e Caracteres

Antes de aprendermos a repetir ações, precisamos entender como o computador guarda várias informações agrupadas.

### Arranjos (Arrays)

Um arranjo é uma lista de variáveis do **mesmo tipo**, agrupadas sob um único nome e com **tamanho fixo**.  
Imagine o cinto de utilidades do Batman: ele tem, digamos, 5 compartimentos exatos — não dá para guardar 6 itens.

Em Go, acessamos as posições de um arranjo usando **índices**. O primeiro elemento **sempre começa no índice 0**.

```go
func ExemploArray() {
    // 1. Declaração
    var inventario [3]string // Um array de exatamente 3 espaços

    // 2. Atribuição
    inventario[0] = "Espada"
    inventario[1] = "Escudo"
    inventario[2] = "Poção"
}
```

---

### Caracteres e Strings

Uma `string` (texto) nada mais é do que um **arranjo de caracteres**. Em linguagens clássicas, uma única letra é chamada de `char`. Em Go, usamos `byte` (letras simples) ou `rune` (letras com acento).

Se você tem a palavra `"Goku"`, você tem um arranjo de 4 posições:

| Índice | Caractere |
| :----: | :-------: |
| `0` | `'G'` |
| `1` | `'o'` |
| `2` | `'k'` |
| `3` | `'u'` |

Para saber o tamanho total de uma palavra, usamos a função **`len(palavra)`**.

> **⚠️ Atenção:** Se o tamanho é 4, o último índice é `3`! O último índice é sempre `tamanho - 1`.

---

## 2. O Paradigma de Repetição no Go

Diferente de linguagens como C, Java ou PHP (que possuem `for`, `while`, `do-while` e `foreach`), **o Go possui apenas uma única palavra-chave para laços: o `for`**.

No entanto, o `for` do Go é flexível o suficiente para assumir o comportamento de todos os outros laços clássicos.

> **Regra de Ouro:** Continuamos declarando todas as variáveis no topo das funções (o nosso "Contrato de Memória")!

---

## 3. As Quatro Faces do `for` em Go

### Forma 1: O `for` Clássico (O Contador)

Usado quando você **sabe exatamente** quantas vezes deseja repetir um bloco. Possui três partes: `Inicialização ; Condição ; Passo`.

```go
func ContarPocoes(quantidade int) {
    var i int

    // Repete de 1 até o número exato passado em quantidade
    for i = 1; i <= quantidade; i++ {
        fmt.Println("Poção número:", i)
    }
}
```

---

### Forma 2: O `for` Condicional (Equivalente ao `while`)

Usado quando você **não sabe o número exato de repetições**, mas sabe qual condição deve manter o laço rodando. Basta omitir a inicialização e o passo.

```go
func CurarPokemon(hpAtual int, hpMaximo int) int {
    var curasAplicadas int
    curasAplicadas = 0

    // Funciona como "enquanto (hpAtual < hpMaximo) faça..."
    for hpAtual < hpMaximo {
        hpAtual = hpAtual + 20
        curasAplicadas = curasAplicadas + 1
    }

    return curasAplicadas
}
```

---

### Forma 3: Simulando o `do-while` (Garantindo ao menos uma execução)

O `do-while` clássico executa o código primeiro e testa a condição no final. A melhor prática em Go é usar uma **variável booleana de controle**.

```go
func BatalhaTreinador() {
    var continuarBatalhando bool
    var hpInimigo int

    continuarBatalhando = true // Força a entrada no laço a primeira vez
    hpInimigo = 50

    for continuarBatalhando {
        fmt.Println("Você atacou o inimigo!")
        hpInimigo = hpInimigo - 10

        // A condição é reavaliada no final do bloco (simulando o "while" no final)
        if hpInimigo <= 0 {
            continuarBatalhando = false
        }
    }
}
```

---

### Forma 4: O `for range` (Equivalente ao `foreach`)

O `range` é usado para percorrer arranjos ou strings. Ele devolve automaticamente o **índice** (posição) e o **valor** daquela posição.

```go
func SoletrarNome(nomePokemon string) {
    var indice int
    var letra rune

    for indice, letra = range nomePokemon {
        fmt.Println("Posição:", indice, "- Letra:", string(letra))
    }
}
```

---

## 4. O `for` Aninhado (Laço dentro de Laço)

Problemas de matrizes (linhas e colunas) ou renderização de mapas usam um `for` dentro de outro. O laço "de dentro" roda por completo a cada única rodada do laço "de fora".

```go
func DesenharCampoMinado(linhas int, colunas int) {
    var x, y int

    for x = 1; x <= linhas; x++ {
        for y = 1; y <= colunas; y++ {
            fmt.Print("[ # ]") // Imprime lado a lado
        }
        fmt.Println("") // Quebra a linha quando termina as colunas
    }
}
```

---

## 🛠️ Desafios Clássicos de Algoritmos (Mão na Massa)

**Regras para todos os desafios:**
1. Respeite os contratos (Entrada e Saída claras).
2. Declare todas as variáveis (`var`) na primeira linha da função.

---

### 🟢 Problema 1: Inversão de String (Clássico Algorítmico)

Crie a função `InverterNome`.
- **Contrato:** Recebe uma `palavra` (`string`). Retorna a `palavraInvertida` (`string`).
- **Lógica:** Crie um laço que comece do **último índice** da palavra e vá diminuindo (`i--`) até chegar em `0` (inclusive).
- **Dicas de Ouro:**
  - O último índice é `len(palavra) - 1`.
  - Para juntar uma letra na resposta: `palavraInvertida = palavraInvertida + string(palavra[i])`.

### 🟡 Problema 2: Fatorial Matemático (`for` clássico)

O Fatorial de 5 (`5!`) é: `5 × 4 × 3 × 2 × 1 = 120`.

Crie a função `CalcularFatorial`.
- **Contrato:** Recebe um `numero` (`int`). Retorna o `resultado` (`int`).
- **Lógica:** Crie um `for` clássico que vá de `numero` até `1`, diminuindo. A cada rodada, multiplique o resultado pela variável de controle do laço.
- **⚠️ Atenção:** Se você inicializar a variável de resposta com `0`, qualquer multiplicação dará zero. Inicialize-a com `1`!

### 🔴 Problema 3: Simulador de Dano Contínuo (do-while)

Crie a função `BatalhaVenenosa`.
- **Contrato:** Recebe o `hpInimigo` (`int`). Retorna os `turnos` (`int`) que ele sobreviveu.
- **Lógica:** Simule um `do-while` usando uma variável booleana de controle (ex: `var vivo bool`). O veneno dá **7 de dano** por turno.
  1. O inimigo toma o dano.
  2. Adicione +1 ao contador de turnos.
  3. No final do bloco, verifique se `hpInimigo <= 0`. Se sim, altere a variável booleana para parar o laço.

### 🔴 Problema 4: A Pirâmide de Blocos (`for` aninhado)

Crie a função `ConstruirEscada`.
- **Contrato:** Recebe a `altura` (`int`). Retorna uma `string` contendo a escada desenhada.
- **Lógica:** Use **for aninhado**.
  - O laço de fora representa as `linhas` (de `1` até `altura`).
  - O laço de dentro: **não** vai até o tamanho total — ele vai de `1` até o valor da `linha` atual.
  - Adicione `"[] "` para cada degrau e `"\n"` (quebra de linha) no laço de fora.
- **Exemplo de saída (altura = 4):**

```text
[] 
[] [] 
[] [] [] 
[] [] [] []
```