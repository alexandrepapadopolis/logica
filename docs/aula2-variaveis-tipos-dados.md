# Entendendo Variáveis e Tipos de Dados na Lógica de Programação

Na lógica de programação, construir um software é como seguir uma receita de bolo: você precisa de instruções (algoritmos) e de ingredientes. Esses ingredientes são os **dados** que o seu programa manipula. Para guardar e organizar esses dados, utilizamos **variáveis** e **tipos de dados**.

---

## 1. O que é uma Variável?

Uma **variável** é um espaço na memória do computador reservado para armazenar uma informação que pode mudar ao longo da execução do programa.

Imagine a variável como uma **caixa etiquetada**:
* **A etiqueta (Nome/Identificador):** Serve para você saber o que tem dentro e chamar o dado quando precisar.
* **O conteúdo (Valor):** É a informação guardada dentro da caixa, que pode ser trocada a qualquer momento.

### Regras comuns para nomear variáveis
Para que o computador entenda seu código e ele fique legível para outros programadores, siga estas boas práticas:
* Não comece nomes de variáveis com números (use `idade1` e não `1idade`).
* Não utilize espaços em branco (use `nomeCompleto` ou `nome_completo`).
* Não utilize caracteres especiais ou acentos (`preco` em vez de `preço`).
* Seja descritivo: prefira `salario_funcionario` a apenas `s`.

---

## 2. Tipos de Dados Primitivos

Para que o computador saiba como tratar a informação dentro da "caixa", cada variável precisa ter um **tipo de dado**. Os tipos determinam quais operações podemos fazer (por exemplo: você pode somar números, mas não pode somar textos).

Os quatro tipos de dados fundamentais (primitivos) na lógica de programação são:

### 📌 Inteiro (Integer)
Representa números inteiros, sejam eles positivos, negativos ou zero. Não possuem casas decimais.
* **Exemplos:** `10`, `-5`, `0`, `2026`.
* **Uso comum:** Idade, quantidade de produtos no estoque, ano atual.

### 📌 Real / Flutuante (Float / Double)
Representa números com casas decimais (números fracionários).
* **Exemplos:** `1.75`, `99.90`, `-3.14`.
* **Uso comum:** Altura, preço de produtos, notas de uma prova.
* *Nota: Na programação, usamos o ponto (`.`) como separador decimal, seguindo o padrão americano.*

### 📌 Caractere / Texto (String)
Representa uma sequência de caracteres alfanuméricos (letras, números, símbolos e espaços). Geralmente, os textos são escritos entre aspas simples (`'`) ou duplas (`"`).
* **Exemplos:** `"Olá, Mundo!"`, `"João Silva"`, `"A"`, `"12345-678"` (CEP).
* **Uso comum:** Nomes, endereços, mensagens de erro, senhas.

### 📌 Lógico / Booleano (Boolean)
É o tipo de dado mais simples. Ele possui apenas dois valores possíveis: **Verdadeiro (True)** ou **Falso (False)**. É a base das tomadas de decisão nos algoritmos.
* **Exemplos:** `true`, `false`.
* **Uso comum:** Verificar se o usuário está logado (`usuarioLogado = true`), se um produto está disponível, ou se uma pessoa é maior de idade.

---

## 3. Exemplo Prático em Pseudocódigo

Veja como declarar variáveis e atribuir valores a elas usando uma estrutura simples de algoritmo (Pseudocódigo):

```text
Algoritmo "Cadastro de Usuário"

Variáveis
    nome: Caractere
    idade: Inteiro
    altura: Real
    esta_ativo: Lógico

Início
    // Atribuindo valores às variáveis
    nome <- "Mariana Costa"
    idade <- 28
    altura <- 1.68
    esta_ativo <- Verdadeiro

    // Exibindo os dados na tela
    Escreva("Nome: ", nome)
    Escreva("Idade: ", idade, " anos")
    Escreva("Altura: ", altura, "m")
    Escreva("Status Ativo: ", esta_ativo)
FimAlgoritmo
```

---

## 4. Tipagem Estática vs. Tipagem Dinâmica

Dependendo da linguagem de programação que você escolher após aprender a lógica, as variáveis podem se comportar de duas formas:

1. **Tipagem Estática:** Você é obrigado a declarar o tipo da variável antes de usá-la, e esse tipo não pode mudar.
   * *Exemplos de linguagens:* Java, C++, C#.
2. **Tipagem Dinâmica:** O próprio computador descobre o tipo do dado baseado no valor que você colocou nele. Você pode mudar o tipo ao longo do programa.
   * *Exemplos de linguagens:* JavaScript, Python, PHP.

---

## Resumo Visual

| Tipo de Dado | O que armazena? | Exemplo prático |
| :--- | :--- | :--- |
| **Inteiro** | Números sem vírgula | `quantidade = 5` |
| **Real** | Números com vírgula | `preco = 19.90` |
| **Caractere (String)** | Textos e frases | `mensagem = "Bem-vindo"` |
| **Booleano** | Verdadeiro ou Falso | `pago = false` |
