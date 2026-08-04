# Entendendo Estruturas de Decisão na Lógica de Programação

Na vida real, tomamos decisões a todo momento baseados em condições: *"Se estiver chovendo, eu levo um guarda-chuva. Caso contrário, vou sem ele"*. Na programação, o computador faz exatamente a mesma coisa através das **estruturas de decisão** (ou estruturas condicionais).

As estruturas de decisão permitem que o fluxo do seu algoritmo mude de caminho dependendo do resultado de uma condição analítica (Verdadeiro ou Falso).

---

## 1. A Estrutura Condicional Simples (`Se`)

É a forma mais básica de decisão. O programa testa uma condição. Se ela for **verdadeira**, ele executa um bloco de código. Se for falsa, ele simplesmente ignora esse bloco e segue em frente.

* **Sintaxe em pseudocódigo:**
  ```text
  Se (condição) Então
      // Código executado se for Verdadeiro
  FimSe
  ```
* **Exemplo prático:**
  ```text
  Se (velocidade > 80) Então
      Escreva("Usuário multado!")
  FimSe
  ```

---

## 2. A Estrutura Condicional Composta (`Se / Senão`)

Utilizada quando você tem dois caminhos possíveis: um bloco de código a ser executado caso a condição seja **verdadeira**, e um bloco diferente caso ela seja **falsa**.

* **Sintaxe em pseudocódigo:**
  ```text
  Se (condição) Então
      // Código executado se for Verdadeiro
  Senão
      // Código executado se for Falso
  FimSe
  ```
* **Exemplo prático:**
  ```text
  Se (idade >= 18) Então
      Escreva("Acesso liberado.")
  Senão
      Escreva("Acesso negado: menor de idade.")
  FimSe
  ```

---

## 3. Estruturas Encadeadas (`Se / Senão Se / Senão`)

Quando o seu problema exige analisar **múltiplas condições em sequência**, você pode encaixar uma estrutura dentro da outra. O programa vai testando as condições na ordem e executa apenas a primeira que for verdadeira.

* **Exemplo prático:**
  ```text
  Se (nota >= 7) Então
      Escreva("Aprovado!")
  Senão Se (nota >= 5) Então
      Escreva("Recuperação!")
  Senão
      Escreva("Reprovado.")
  FimSe
  ```

---

## 4. Estrutura de Escolha Múltipla (`Escolha Caso` / `Switch Case`)

Quando você precisa testar o valor de uma **única variável** contra várias opções fixas, o uso de muitos `Se / Senão` pode deixar o código confuso. Para isso, usamos a estrutura `Escolha` (ou `Switch`).

* **Exemplo prático (Menu de Atendimento):**
  ```text
  Escolha (opcao_menu)
      Caso 1:
          Escreva("Falar com o suporte técnico.")
      Caso 2:
          Escreva("Falar com o setor financeiro.")
      Caso 3:
          Escreva("Falar com um atendente humano.")
      OutroCaso:
          Escreva("Opção inválida.")
  FimEscolha
  ```

---

## 5. Operadores de Comparação e Lógicos

As condições das estruturas de decisão são criadas cruzando variáveis com a ajuda de operadores.

### Operadores de Comparação (Relacionais)
Servem para comparar dois valores e devolvem `Verdadeiro` ou `Falso`:
* `==` ou `=` : Igual a
* `!=` ou `<>` : Diferente de
* `>` : Maior que
* `<` : Menor que
* `>=` : Maior ou igual a
* `<=` : Menor ou igual a

### Operadores Lógicos
Servem para unir mais de uma condição na mesma frase:
* **E (AND):** Todas as condições precisam ser verdadeiras.
  * *Exemplo:* `Se (usuario == "admin" E senha == "123")`
* **OU (OR):** Pelo menos uma das condições precisa ser verdadeira.
  * *Exemplo:* `Se (dia == "Sábado" OU dia == "Domingo")`
* **NÃO (NOT):** Inverte o valor lógico da condição.

---

## Resumo dos Caminhos

| Tipo de Estrutura | Quando usar? | Quantidade de saídas |
| :--- | :--- | :--- |
| **Condicional Simples** | Quando só importa o que fazer se der certo. | 1 caminho |
| **Condicional Composta** | Quando há uma alternativa clara para o erro. | 2 caminhos distintos |
| **Condicional Encadeada**| Quando há várias faixas de valores (ex: notas). | Múltiplos caminhos sequenciais |
| **Escolha Caso** | Quando há opções exatas e fixas (ex: menus). | Múltiplos caminhos exatos |
