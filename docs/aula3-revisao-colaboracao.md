# Manual Avançado de Fluxo de Trabalho, Colaboração e Boas Práticas no GitHub

O GitHub evoluiu de um ecossistema de hospedagem de código para uma plataforma completa de DevOps e colaboração. Para operar em nível profissional, engenheiros de software seguem fluxos de trabalho estruturados que garantem a estabilidade do código, a segurança da informação e a eficiência do time.

---

## 1. O Fluxo de Trabalho Profissional (GitHub Flow Detalhado)

O GitHub Flow é um fluxo de trabalho leve e centrado em branches que suporta equipes que realizam entregas e implantações contínuas. Abaixo estão as etapas detalhadas do ciclo de vida de uma funcionalidade:

```text
[main] ───────────────────────────────────────────────────────────────► (Deploy)
          │                                              ▲
          └─► [feature/nova-tela] ──► (Commits) ──► [PR] ──┤ (Code Review)
```

### Passo 1: Isolamento em Branch de Tópico (Topic Branch)
A branch principal (main ou master) representa o código em estado de produção, o que significa que ele deve estar estável e pronto para o usuário. Nunca se deve commitar diretamente nela. Ao iniciar uma tarefa, cria-se uma branch a partir da main devidamente atualizada.

Padrão de Nomenclatura: Adote prefixos descritivos para organizar o repositório:
* feature/nome-da-feature: Para novas funcionalidades.
* bugfix/nome-do-bug: Para correção de problemas em ambiente de desenvolvimento.
* hotfix/correcao-urgente: Para correções críticas diretamente em produção.
* docs/atualiza-readme: Para exclusividade de documentação.

### Passo 2: O Ciclo de Desenvolvimento e Commits Locais
Com a branch isolada, o desenvolvedor realiza alterações no código. O salvamento deve ser granular:
* Evite acumular um dia inteiro de trabalho em um único commit gigante.
* Faça commits a cada unidade lógica de trabalho concluída (por exemplo: criar a interface de um botão, depois criar a validação do clique, depois integrar com a API).

### Passo 3: Criação do Pull Request (PR) como Ferramenta de Comunicação
O Pull Request não é apenas um botão de mesclar, mas uma ferramenta de comunicação síncrona e assíncrona. Ao abrir um PR, o autor deve preencher um modelo contendo:
* Descrição: O que foi feito e o porquê das alterações.
* Contexto: Link para a tarefa correspondente em ferramentas de gestão (como Jira, Trello ou GitHub Issues).
* Instruções de Teste: O passo a passo para o revisor rodar e validar o código localmente.
* Evidências: Capturas de tela ou GIFs mostrando a alteração visual, o que é essencial para o Frontend.

### Passo 4: Code Review (Revisão de Código)
Nenhum código entra em produção sem o olhar de pelo menos um par (Peer Review). Durante o Code Review, avalia-se:
* Qualidade do código: Legibilidade, arquitetura e padrões do projeto.
* Segurança: Ausência de chaves de API expostas ou vulnerabilidades no código.
* Cobertura de testes: Verificação se foram inclusos testes unitários ou de integração.

### Passo 5: CI/CD (Integração e Entrega Contínuas)
O GitHub possui o GitHub Actions, que roda testes automatizados assim que o PR é aberto. Se os testes falharem, o PR fica bloqueado para Merge, impedindo que código defeituoso seja integrado à branch principal.

### Passo 6: Estratégias de Merge (Mesclagem)
Após aprovação humana e automatizada, o código é integrado. Existem três formas principais de fazer isso no GitHub:
1. Merge Commit: Mantém todo o histórico de commits da branch de forma cronológica, gerando um commit específico de merge.
2. Squash and Merge: Consolida todos os commits da sua branch de trabalho em um único commit limpo antes de enviar para a main. É ideal para manter o histórico da branch principal linear e limpo.
3. Rebase and Merge: Reaplica os commits da sua branch no topo da main sem criar um commit de merge, mantendo uma linha do tempo estritamente linear.

---

## 2. Modelos Avançados de Colaboração

Dependendo do modelo de governança do software, a colaboração se divide em dois formatos:

### A. Modelo de Repositório Compartilhado (Shared Repository Model)
Utilizado internamente em empresas e agências.
* Acesso: Os desenvolvedores recebem permissão de escrita (Write Access) direta no repositório da organização.
* Fluxo: Todos criam suas branches e Pull Requests dentro do mesmo endereço eletrônico.
* Proteção de Branches: Geralmente, as configurações do GitHub bloqueiam pushes diretos na main, exigindo que as alterações passem obrigatoriamente por Pull Requests aprovados.

### B. Modelo Fork e Pull Request (Fork and Pull Model)
Utilizado no desenvolvimento de software de código aberto (Open Source).
* Acesso: Desenvolvedores externos não têm permissão de escrita no projeto oficial.
* Fluxo: 
  1. O desenvolvedor faz um Fork, que gera uma cópia completa e independente do projeto para a sua própria conta do GitHub.
  2. Altera o código na sua cópia pessoal de forma totalmente livre.
  3. Abre um Pull Request de Origem Cruzada (Cross-Repository PR), solicitando que os mantenedores do projeto original revisem e aceitem a sua contribuição.

---

## 3. Boas Práticas de Engenharia no GitHub

Para manter projetos sustentáveis a longo prazo, equipes de alto desempenho seguem regras estritas de padronização:

### Mensagens de Commit Claras (Semantic Commits)
Evite mensagens genéricas como "ajustes", "correção" ou "funcionando". Adote a convenção internacional de Commits Semânticos:

```text
<tipo>(<escopo opcional>): <descrição curta em letras minúsculas>

[corpo opcional com mais detalhes]

[rodapé opcional para referenciar chamados ou tarefas]
```

Tipos mais comuns:
* feat: Uma nova funcionalidade sendo introduzida.
* fix: A correção de um bug.
* docs: Alterações exclusivamente na documentação (como o README.md).
* style: Alterações que não afetam o significado do código (espaços em branco, formatação, ponto e vírgula faltando).
* refactor: Uma alteração no código que não corrige um bug nem adiciona uma funcionalidade, mas melhora a estrutura interna.
* test: Adicionar ou corrigir testes existentes.
* chore: Atualizações de tarefas de build, configurações de ferramentas ou pacotes de terceiros.

Exemplos Práticos:
* feat(auth): adiciona autenticação de dois fatores com google authenticator
* fix(cart): corrige arredondamento centesimal no valor total do frete

### Gestão de Conflitos (Merge Conflicts)
Conflitos acontecem quando duas pessoas alteram exatamente as mesmas linhas do mesmo arquivo em branches diferentes. 
* Regra de ouro: Resolva o conflito sempre na sua branch de trabalho, nunca na branch principal.
* Como mitigar: Execute o comando `git pull origin main` na sua branch local todos os dias antes de começar a codificar. Quanto mais atualizada sua branch estiver em relação à principal, menor a chance de um conflito complexo.

### Uso de Issues e Projetos (GitHub Projects)
O GitHub possui ferramentas nativas de gerenciamento de projetos baseadas em Kanban:
* Issues: Servem para relatar bugs encontrados por usuários ou documentar novas funcionalidades requisitadas. Cada Issue recebe etiquetas como bug, enhancement ou ajuda necessária.
* Vinculação Automática: No corpo do seu Pull Request, se você escrever "Closes #12" ou "Fixes #12", o GitHub fechará automaticamente a Issue número 12 assim que o Merge for realizado.

### Segurança e Arquivos Ocultos (.gitignore)
Nunca envie para o GitHub arquivos de configuração local, pastas de dependências (como a node_modules no ecossistema JavaScript) ou credenciais de banco de dados.
* Utilize o arquivo `.gitignore` na raiz do projeto para listar tudo o que o Git deve ignorar e nunca rastrear.
* Chaves privadas e senhas devem ser salvas como GitHub Secrets caso precisem ser usadas em automações.

---

## Tabela Comparativa de Gerenciamento de Histórico

| Ferramenta / Abordagem | Vantagem Principal | Desvantagem Principal | Quando Escolher? |
| :--- | :--- | :--- | :--- |
| Merge Commit tradicional | Preserva a história real e cronológica de cada ramificação. | Cria um histórico visual poluído no terminal. | Equipes pequenas com fluxos de ramificação simples. |
| Squash and Merge | Mantém a branch principal limpa com um único commit por tarefa. | Perde os detalhes do micro-histórico de desenvolvimento. | Repositórios comerciais de ritmo acelerado e muitos PRs. |
| Rebase and Merge | Histórico totalmente linear, facilitando o rastreamento de alterações. | Altera o histórico de commits, exigindo cuidado ao lidar com branches públicas. | Equipes sêniores que prezam por uma linha do tempo linear. |
