---
title: "Aula 1 — Fundamentos"
nav_order: 3
permalink: /aula-1
---

# 📑 Aula 1: Fundamentos de Go (Golang)

**Objetivo:** Sair do zero até a criação de funções em 4 horas.  
**Público:** Iniciantes em Programação  
**Duração:** 4 horas (Teoria + Prática)

---

## 1. Variáveis e Constantes

Go é uma linguagem **estaticamente tipada** — o tipo do dado é fixo após a declaração.

| Palavra-chave | O que faz | Onde usar |
| :------------ | :-------- | :-------- |
| `var` | Declaração padrão | Qualquer escopo |
| `const` | Valor que nunca muda | Qualquer escopo |
| `:=` (curto) | Declara e infere o tipo | Apenas dentro de funções |

```go
package main
import "fmt"

func main() {
    const curso = "Treinamento Go"
    var versao string = "1.26"
    idade := 20 // Go entende como int

    fmt.Println(curso, versao, idade)
}
```

---

## 2. Tipos de Dados Básicos

| Tipo | Descrição | Exemplo |
| :--- | :-------- | :------ |
| `string` | Texto entre aspas duplas | `"Jogador"` |
| `int` | Números inteiros | `10`, `-5` |
| `float64` | Números decimais | `1.75`, `80.5` |
| `bool` | Valores lógicos | `true`, `false` |

---

## 3. Estruturas Condicionais (`if` / `else` / `else if`)

As estruturas de decisão permitem que o código tome caminhos diferentes dependendo da situação.

- **`if` (Se):** Testa uma condição inicial. Se for verdadeira, o bloco executa.
- **`else` (Senão):** O caso contrário — executa quando o `if` é falso.
- **`else if` (Senão Se):** Permite testar várias condições em sequência, até achar uma verdadeira ou cair no `else` final.

> Em Go, **não usamos parênteses** `()` para a condição, mas as chaves `{}` são **obrigatórias**.

```go
if idade >= 18 {
    fmt.Println("Maior de idade")
} else if idade > 12 {
    fmt.Println("Adolescente") // Cai aqui se não for >= 18, mas for > 12
} else {
    fmt.Println("Criança") // Cai aqui se todas as opções acima forem falsas
}
```

---

## 4. Estrutura de Seleção (`switch` / `case`)

Quando você tem muitos `else if` testando o valor exato da **mesma variável**, o código fica confuso. O `switch` resolve isso funcionando como um "menu de opções".

Ele pega uma variável, testa contra vários `case` (casos) e o `default` é equivalente ao `else` final.

```go
func EscolherFerramenta(bloco string) string {
    // 1. Declaração no topo
    var ferramenta string

    // 2. Lógica de seleção
    switch bloco {
    case "Pedra":
        ferramenta = "Picareta"
    case "Madeira":
        ferramenta = "Machado"
    case "Terra":
        ferramenta = "Pá"
    default:
        ferramenta = "Mão nua"
    }

    // 3. Retorno
    return ferramenta
}
```

---

# 🛠️ Mão na Massa: Desafios de Lógica I

**Instruções:** Utilize `fmt.Scan(&variavel)` para receber entradas. Lembre-se: no Go, variável declarada e não usada **gera erro de compilação!**

### 🟢 Problema 1: O Verificador de Login (Fácil)

Crie um programa que peça um nome de usuário.
- Se o usuário for `"admin"`, exiba: `"Acesso total liberado"`.
- Se for qualquer outro nome, exiba: `"Acesso restrito: [nome]"`.

### 🟡 Problema 2: Calculadora de Bônus (Médio)

Receba o **salário** e os **anos de empresa** de um funcionário.
- Se tem **mais de 5 anos** de casa **E** ganha **menos de R$ 3.000**, o bônus é de 20% do salário.
- Caso contrário, o bônus é de 10%.
- **Saída:** Exiba o valor do bônus em reais.

### 🔴 Problema 3: Simulador de Sensor de Pressão (Difícil)

Simule a leitura de um sensor (tipo `float64`).

1. Se a pressão for **menor que 0**: Exiba `"Erro: Sensor desconectado"`.
2. Se estiver entre **0 e 5.0**: Exiba `"Status: Normal"`.
3. Se estiver entre **5.1 e 10.0**: Exiba `"Alerta: Pressão Alta"`.
4. Se for **maior que 10.0**: Exiba `"PERIGO: EVACUAR ÁREA!"`.
5. **Condição Especial:** Se a pressão for exatamente **7.5**, exiba também: `"Realizando calibração automática..."`.

---

# 🎮 Parte 2: Operadores, Contratos e Funções

## 1. Operadores Aritméticos

Antes de criarmos funções, precisamos saber fazer contas.

| Operador | O que faz | Exemplo (Minecraft/Pokémon) |
| :------: | :-------- | :-------------------------- |
| `+` | Soma | `vida + pocaoCura` |
| `-` | Subtração | `vidaAtual - danoAtaque` |
| `*` | Multiplicação | `madeiraBruta * 4` (tábuas) |
| `/` | Divisão | `esmeraldas / precosAldeao` |
| `%` | **Resto da Divisão** | `pokebolas % treinadores` |

> **O que é o `%` (Módulo/Resto)?**
> Imagine que você tem 5 poções e quer dividir entre 2 jogadores. Cada um recebe 2, e **sobra 1**. O `%` retorna exatamente essa sobra. É muito usado para descobrir se um número é **Par ou Ímpar**: qualquer número `% 2` com resultado `0` é par!

---

## 2. Operadores Lógicos e de Comparação

| Categoria | Operadores |
| :-------- | :--------- |
| Comparação | `==` (igual) · `!=` (diferente) · `>` · `<` · `>=` · `<=` |
| Lógica | `&&` (E) · `\|\|` (OU) · `!` (NÃO) |

---

## 3. Contratos (Funções), Entradas e Saídas

Em programação, uma função é como uma **Mesa de Trabalho (Crafting Table)**. Para ela funcionar, estabelecemos um **Contrato de Tipagem**: dizemos exatamente o *tipo* de material que entra e o *tipo* de material que sai.

1. **Entrada (Parâmetros):** O que entra e qual o tipo (ex: `troncos int`).
2. **Processamento:** A lógica interna.
3. **Saída (Retorno):** O que a função devolve e qual o tipo (ex: `int`).

> **Regra de Ouro:** Todas as variáveis usadas dentro da função devem ser declaradas no topo, definindo seus tipos antes de começar a lógica.

---

## 4. Exemplos Guiados

### 🟢 Exemplo Fácil: Crafting de Tábuas (Minecraft)

**Contrato:**
- **Entra:** 1 `int` (`troncos`)
- **Sai:** 1 `int` (quantidade de tábuas)

```go
package main
import "fmt"

func CraftarTabuas(troncos int) int {
    // 1. Declaração de variáveis no topo
    var tabuas int

    // 2. Lógica e processamento
    tabuas = troncos * 4

    // 3. Retorno
    return tabuas
}
```

---

### 🟡 Exemplo Médio: Regra de Batalha Pokémon (Paridade)

**Contrato:**
- **Entra:** 1 `int` (`nivel`)
- **Sai:** 1 `string`
- **Regra:** Se o nível da rota for par, batalha em dupla. Se for ímpar, 1x1.

```go
func DefinirTipoBatalha(nivel int) string {
    // 1. Declarações no topo
    var resto int
    var tipoBatalha string

    // 2. Lógica (uso do módulo % para achar par/ímpar)
    resto = nivel % 2

    if resto == 0 {
        tipoBatalha = "Batalha em Dupla (2x2)"
    } else {
        tipoBatalha = "Batalha Individual (1x1)"
    }

    // 3. Retorno
    return tipoBatalha
}
```

---

### 🔴 Exemplo Difícil: Calculadora de Batalha (Pokémon)

**Contrato:**
- **Entram:** 2 `int` (`hpAtual`, `dano`)
- **Saem:** 2 valores — `int` (HP restante) e `bool` (se desmaiou)

```go
func BatalhaPokemon(hpAtual int, dano int) (int, bool) {
    // 1. Declarações no topo
    var hpRestante int
    var desmaiou bool

    // 2. Lógica
    hpRestante = hpAtual - dano

    // Garantir que a vida não fique negativa
    if hpRestante <= 0 {
        hpRestante = 0
        desmaiou = true
    } else {
        desmaiou = false
    }

    // 3. Retorno duplo
    return hpRestante, desmaiou
}
```

---

## 🛠️ Desafios de Funções

**Regra:** Crie funções para os problemas abaixo. Respeite os contratos (defina os tipos de entrada e saída) e declare todas as variáveis no topo da função.

### 🟢 Problema 1: Crafting de Gravetos (Fácil — Minecraft)

No Minecraft, com **2 tábuas** você consegue craftar **4 gravetos**.  
Crie a função `CraftarGravetos`.
- **Contrato:** Recebe a quantidade de *tábuas* (`int`) e retorna a quantidade de *gravetos* (`int`).
- *Dica: Quantos gravetos rende 1 única tábua?*

### 🟡 Problema 2: Divisão de Loot de Raid (Médio — Resto)

Você e seus amigos derrotaram uma Raid e caíram várias Poções de Cura. Vocês precisam dividir igualmente.  
Crie a função `DividirPocoes`.
- **Contrato:** Recebe `totalPocoes` (`int`) e `jogadores` (`int`). Retorna **dois valores** `(int, int)`:
  1. Quantas poções cada jogador recebe.
  2. Quantas poções sobram no baú (use o operador `%`).

### 🔴 Problema 3: Captura com Pokébola (Difícil)

Crie a função `TentarCaptura`.
- **Contrato:** Recebe `hpMaximo` (`int`), `hpAtual` (`int`) e `taxaPokebola` (`int`). Retorna `bool`.
- **Lógica:**
  1. Calcule a saúde do Pokémon em percentagem: `(hpAtual * 100) / hpMaximo`.
  2. Se o HP for **≤ 20%** E a `taxaPokebola` for **> 50**, retorna `true`.
  3. Caso contrário, retorna `false`.

### 🟡 Problema 4: A Escolha do Inicial (Médio — Switch)

Crie a função `VantagemElemental`.
- **Contrato:** Recebe o `tipoPokemon` (`string`) e retorna contra qual tipo ele tem vantagem (`string`).
- **Lógica:** Use `switch / case`.
  - `"Fogo"` → retorna `"Grama"`
  - `"Agua"` → retorna `"Fogo"`
  - `"Grama"` → retorna `"Agua"`
  - `default` → retorna `"Neutro"`