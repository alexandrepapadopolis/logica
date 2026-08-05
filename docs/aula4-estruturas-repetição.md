# Estruturas de Repetição na Lógica de Programação

As estruturas de repetição — também conhecidas como **laços de repetição** ou ***loops*** — são blocos de código fundamentais na lógica de programação. Elas permitem que um conjunto de instruções seja executado repetidamente enquanto uma determinada condição for verdadeira ou por uma quantidade de vezes predefinida.

A principal função dessas estruturas é **evitar a duplicação de código**, poupar tempo de desenvolvimento e permitir o processamento eficiente de grandes volumes de dados (como listas e matrizes).

---

## 🧭 Os Três Pilares de um Loop

Para que qualquer estrutura de repetição funcione corretamente e não cause problemas no sistema, ela precisa de três elementos essenciais:

1. **Inicialização:** Definição do ponto de partida (geralmente uma variável contadora).
2. **Condição de Parada:** Uma expressão lógica que avalia se o *loop* deve continuar ou parar.
3. **Atualização (Incremento/Decremento):** Modificação do valor inicial para que a condição de parada seja alcançada no futuro.

> ⚠️ **Aviso de Perigo: Loop Infinito**
> Se a condição de parada nunca for atingida (por falta de atualização ou lógica incorreta), o programa entrará em um *loop* infinito, travando a execução do sistema ou consumindo toda a memória disponível.

---

## 🛠️ Principais Tipos de Estruturas de Repetição

A maioria das linguagens de programação modernas (como JavaScript, Python, C++, Java) trabalha com três tipos principais de laços. A escolha de qual usar depende se você sabe ou não quantas vezes precisará repetir o bloco de código.

### 1. Repetição com Variável de Controle (`for`)
O laço `for` (para) é ideal quando **sabemos exatamente quantas vezes** o código precisa ser executado antes mesmo do *loop* começar.

*   **Lógica:** "Para `i` começando em X, enquanto `i` for menor que Y, avance de 1 em 1."
*   **Exemplo Prático (JavaScript):**
    ```javascript
    // Exibe os números de 1 a 5 no console
    for (let i = 1; i <= 5; i++) {
        console.log(`Contagem: ${i}`);
    }
    ```

### 2. Repetição com Teste no Início (`while`)
O laço `while` (enquanto) é utilizado quando **não sabemos o número exato de repetições**, mas sabemos que o código deve rodar enquanto uma condição específica for verdadeira.

*   **Lógica:** "Enquanto a condição for verdadeira, faça o bloco de código. Verifique a condição *antes* de cada execução."
*   **Exemplo Prático (JavaScript):**
    ```javascript
    let energia = 100;

    // O loop roda até a energia acabar, mas não sabemos quantos passos exatos serão dados
    while (energia > 0) {
        console.log("Correndo...");
        energia -= 25; // Reduz a energia a cada volta
    }
    ```

### 3. Repetição com Teste no Final (`do...while`)
O laço `do...while` (faça... enquanto) é muito parecido com o `while`, com uma diferença crucial: **o bloco de código é executado pelo menos uma vez**, mesmo que a condição seja falsa logo de início. Isso acontece porque a validação é feita apenas no final do bloco.

*   **Lógica:** "Faça o bloco de código primeiro. Depois, verifique se a condição é verdadeira para decidir se repete."
*   **Exemplo Prático (JavaScript):**
    ```javascript
    let tentativa = 1;
    const senhaCorreta = "1234";
    let senhaDigitada;

    // Garante que o usuário digite a senha pelo menos uma vez antes de validar
    do {
        senhaDigitada = prompt("Digite sua senha:");
        tentativa++;
    } while (senhaDigitada !== senhaCorreta);
    ```

---

## 🎛️ Comandos de Interrupção

Às vezes, precisamos alterar o comportamento padrão de um *loop* antes que ele termine naturalmente. Para isso, existem duas palavras-chave universais:

*   **`break`:** Interrompe e sai imediatamente do laço de repetição, ignorando qualquer condição restante.
*   **`continue`:** Pula o restante do código da volta atual e vai direto para a próxima iteração (próxima rodada do *loop*).

---

## 📊 Resumo Comparativo

| Estrutura | Quando usar? | Executa se a condição inicial for falsa? |
| :--- | :--- | :--- |
| **`for`** | Quando o número de repetições é conhecido e fixo. | Não |
| **`while`** | Quando o número de repetições é imprevisível e depende de fatores externos. | Não |
| **`do...while`** | Quando o código precisa rodar obrigatoriamente pelo menos uma vez. | **Sim (Apenas a primeira vez)** |
