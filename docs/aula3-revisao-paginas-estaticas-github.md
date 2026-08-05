# Estruturas de Repetição na Lógica de Programação e Páginas Estáticas no GitHub

Este documento apresenta dois conceitos fundamentais para desenvolvedores: o controle de fluxo via laços de repetição na lógica de programação e a publicação de páginas estáticas na web utilizando o GitHub Pages.

---

## Parte 1: Estruturas de Repetição na Lógica de Programação

As estruturas de repetição — também conhecidas como laços de repetição ou loops — são blocos de código que permitem executar um conjunto de instruções repetidamente enquanto uma determinada condição for verdadeira ou por uma quantidade de vezes predefinida.

A principal função dessas estruturas é evitar a duplicação de código, poupar tempo de desenvolvimento e permitir o processamento eficiente de volumes de dados.

### Os Três Pilares de um Loop

Para que qualquer estrutura de repetição funcione corretamente, ela precisa de três elementos essenciais:

1. **Inicialização:** Definição do ponto de partida (geralmente uma variável contadora).
2. **Condição de Parada:** Uma expressão lógica que avalia se o loop deve continuar ou parar.
3. **Atualização (Incremento/Decremento):** Modificação do valor inicial para que a condição de parada seja alcançada no futuro.

> **Aviso de Perigo: Loop Infinito**
> Se a condição de parada nunca for atingida, o programa entrará em um loop infinito, travando a execução do sistema ou consumindo toda a memória disponível.

### Principais Tipos de Estruturas de Repetição

A maioria das linguagens de programação modernas trabalha com três tipos principais de laços:

#### 1. Repetição com Variável de Controle (`for`)
O laço `for` é ideal quando sabemos exatamente quantas vezes o código precisa ser executado antes mesmo do loop começar.

* Lógica: "Para `i` começando em X, enquanto `i` for menor que Y, avance de 1 em 1."
* Exemplo Prático (JavaScript):
    ```javascript
    for (let i = 1; i <= 5; i++) {
        console.log(`Contagem: ${i}`);
    }
    ```

#### 2. Repetição com Teste no Início (`while`)
O laço `while` é utilizado quando não sabemos o número exato de repetições, mas sabemos que o código deve rodar enquanto uma condição específica for verdadeira.

* Lógica: "Enquanto a condição for verdadeira, faça o bloco de código. Verifique a condição antes de cada execução."
* Exemplo Prático (JavaScript):
    ```javascript
    let energia = 100;
    while (energia > 0) {
        console.log("Correndo...");
        energia -= 25;
    }
    ```

#### 3. Repetição com Teste no Final (`do...while`)
O laço `do...while` executa o bloco de código pelo menos uma vez, mesmo que a condição seja falsa logo de início, pois a validação é feita apenas no final.

* Lógica: "Faça o bloco de código primeiro. Depois, verifique se a condição é verdadeira para decidir se repete."
* Exemplo Prático (JavaScript):
    ```javascript
    let tentativa = 1;
    const senhaCorreta = "1234";
    let senhaDigitada;
    do {
        senhaDigitada = prompt("Digite sua senha:");
        tentativa++;
    } while (senhaDigitada !== senhaCorreta);
    ```

### Comandos de Interrupção

* **`break`:** Interrompe e sai imediatamente do laço de repetição.
* **`continue`:** Pula o restante do código da volta atual e vai direto para a próxima iteração.

### Resumo Comparativo dos Loops

| Estrutura | Quando usar? | Executa se a condição inicial for falsa? |
| :--- | :--- | :--- |
| **`for`** | Quando o número de repetições é conhecido e fixo. | Não |
| **`while`** | Quando o número de repetições é imprevisível. | Não |
| **`do...while`** | Quando o código precisa rodar ao menos uma vez. | Sim (Apenas a primeira vez) |

---

## Parte 2: Criação de Páginas Estáticas no GitHub

O **GitHub Pages** é um serviço de hospedagem de sites estáticos oferecido diretamente pelo GitHub. Ele transforma arquivos de código-fonte salvos em um repositório em um site público acessível pela internet.

### Definição de Páginas Estáticas

Páginas estáticas são sites compostos por arquivos que são entregues ao navegador do usuário exatamente da mesma forma como estão armazenados no servidor. Eles utilizam tecnologias do lado do cliente (client-side):

* **HTML:** Define a estrutura e o conteúdo da página.
* **CSS:** Define o estilo visual, cores e layout.
* **JavaScript:** Adiciona interatividade no navegador do usuário (como os loops explicados na Parte 1).

**O que NÃO é uma página estática:** Sites estáticos não possuem processamento de banco de dados do lado do servidor (como linguagens PHP, Python/Django ou Node.js para backend) no momento do carregamento da página. Todos os dados dinâmicos precisam ser tratados via APIs no JavaScript do navegador.

### Explicação do Processo de Criação e Configuração

Para criar e publicar uma página estática no GitHub, o fluxo padrão consiste nos seguintes passos:

#### 1. Criação do Repositório
* Acesse sua conta no GitHub.
* Crie um novo repositório público.
* Se o objetivo for criar um site principal para seu usuário, nomeie o repositório exatamente como `seu-usuario.github.io`. Caso contrário, use qualquer nome para criar um site de projeto secundário.

#### 2. Preparação dos Arquivos
* O arquivo principal do seu site deve obrigatoriamente se chamar `index.html`. Ele servirá como a página inicial do site.
* Adicione seus arquivos adicionais de CSS, JavaScript e imagens ao repositório.

#### 3. Ativação do GitHub Pages
* No menu superior do seu repositório no GitHub, clique na aba **Settings** (Configurações).
* Na barra lateral esquerda, clique na seção **Pages**.
* Em **Build and deployment**, altere a opção **Source** para **Deploy from a branch**.
* No campo **Branch**, selecione a ramificação principal (geralmente `main` ou `master`) e defina a pasta raiz como `/(root)`.
* Clique em **Save**.

#### 4. Publicação e Acesso
* O GitHub iniciará uma automação interna (GitHub Actions) para processar os arquivos.
* Após um ou dois minutos, a página de configurações exibirá o endereço público do seu site.
* O formato da URL gerada será: `https://github.io` (ou apenas `https://github.io` se for o repositório principal).

### Vantagens do Uso
* **Gratuidade:** Hospedagem sem custos para projetos de código aberto.
* **Certificado SSL Automático:** O site já é publicado com protocolo de segurança HTTPS ativado.
* **Integração com Git:** Qualquer atualização feita nos arquivos do repositório através de um comando `git push` atualiza o site automaticamente em poucos instantes.
