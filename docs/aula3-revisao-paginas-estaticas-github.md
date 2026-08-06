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
