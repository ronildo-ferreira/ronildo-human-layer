## Leia atentamente o texto.

### Ciclo de vida e processo de desenvolvimento de um aplicativo móvel

Desenvolver um aplicativo não significa apenas começar a programar. Antes da construção, é necessário entender **qual problema será resolvido, quem utilizará o aplicativo e quais funcionalidades serão necessárias**.

O desenvolvimento normalmente acontece em etapas. Essas etapas formam um **processo de desenvolvimento**, que ajuda a organizar o trabalho e diminuir problemas durante a criação do aplicativo.

Um processo simplificado pode ser representado assim:

**Problema → Planejamento → Projeto da interface → Desenvolvimento → Testes → Distribuição → Manutenção**

#### 1. Identificação do problema e dos usuários

O primeiro passo é compreender **por que o aplicativo será criado**.

Por exemplo, imagine que uma escola queira desenvolver um aplicativo para ajudar os estudantes a controlar as datas de entrega das atividades.

Antes de desenvolver, algumas perguntas precisam ser respondidas:

* Quem utilizará o aplicativo?
* Qual problema ele pretende resolver?
* Quais informações deverão ser armazenadas?
* Quais funcionalidades realmente serão necessárias?

Essa etapa evita desenvolver recursos que não possuem utilidade para o usuário.

#### 2. Planejamento

Depois de compreender o problema, é possível definir as funcionalidades do aplicativo.

No exemplo anterior, poderíamos definir:

* cadastrar uma atividade;
* informar disciplina e data de entrega;
* visualizar atividades cadastradas;
* excluir uma atividade;
* marcar uma atividade como concluída.

Também é possível criar desenhos simples das telas antes de começar o desenvolvimento. Esses desenhos são chamados de **wireframes** ou protótipos de baixa fidelidade.

#### 3. Desenvolvimento da interface

No App Inventor, boa parte dessa etapa acontece no **Designer**.

O desenvolvedor escolhe e organiza componentes como:

* `Label`;
* `Button`;
* `TextBox`;
* `Image`;
* `ListView`;
* `HorizontalArrangement`;
* `VerticalArrangement`.

Nesse momento também devem ser consideradas questões como tamanho dos elementos, facilidade de navegação, legibilidade e organização das informações.

Uma interface bonita, mas difícil de utilizar, não representa necessariamente uma boa solução.

#### 4. Desenvolvimento da lógica

Depois da interface, é necessário definir **como o aplicativo deverá funcionar**.

No App Inventor, isso ocorre principalmente no editor **Blocks**.

Por exemplo:

**Quando o usuário clicar no botão "Salvar" → verificar os dados → armazenar a atividade → atualizar a lista → informar que o cadastro foi realizado.**

Os blocos representam eventos, decisões, operações e ações executadas pelo aplicativo.

É importante perceber que interface e programação possuem funções diferentes:

* **Designer:** como o aplicativo será apresentado ao usuário;
* **Blocks:** como o aplicativo irá se comportar.

#### 5. Testes

Um aplicativo não deve ser considerado pronto apenas porque funcionou uma vez.

Ele precisa ser testado em diferentes situações.

Por exemplo:

* O que acontece se o usuário não preencher um campo?
* O que acontece se digitar um valor incorreto?
* Os dados continuam disponíveis depois que o aplicativo é fechado?
* Os botões funcionam corretamente?
* A navegação entre as telas está correta?
* O aplicativo funciona em diferentes tamanhos de tela?

No App Inventor, o **AI Companion** permite testar o aplicativo durante seu desenvolvimento.

Encontrar um erro durante os testes não significa necessariamente que o projeto fracassou. Os testes existem justamente para encontrar problemas **antes que eles cheguem ao usuário final**.

#### 6. Distribuição

Depois de desenvolvido e testado, o aplicativo pode ser preparado para instalação em dispositivos.

Em um projeto real, essa etapa também pode envolver sua publicação em uma **loja de aplicativos**, que possui regras e requisitos próprios.

Antes da distribuição, é necessário verificar questões como:

* nome e identificação do aplicativo;
* ícone;
* versão;
* permissões necessárias;
* funcionamento;
* privacidade e tratamento dos dados dos usuários.

#### 7. Manutenção e evolução

A publicação não significa necessariamente o fim do desenvolvimento.

Depois que usuários começam a utilizar o aplicativo, podem surgir:

* erros que não haviam sido identificados;
* sugestões;
* mudanças nos dispositivos;
* novos requisitos;
* necessidades de segurança;
* novas funcionalidades.

O aplicativo pode então receber novas versões.

Por exemplo:

**Versão 1.0**
Cadastro e consulta de atividades.

**Versão 1.1**
Correção de erros.

**Versão 1.2**
Inclusão de filtros por disciplina.

**Versão 2.0**
Inclusão de notificações e novas funcionalidades.

Por isso utilizamos a expressão **ciclo de vida**: o software pode continuar sendo analisado, modificado, testado e atualizado durante todo o período em que estiver sendo utilizado.

### Um processo que não precisa ser totalmente linear

Um ponto importante é evitar a impressão de que cada etapa acontece apenas uma vez.

Durante os testes, por exemplo, o grupo pode descobrir que uma funcionalidade foi mal planejada. Nesse caso, será necessário retornar ao planejamento, modificar a interface, alterar os blocos e testar novamente.

Assim, na prática, o processo pode acontecer desta maneira:

**Planejar → Desenvolver → Testar → Encontrar problema → Corrigir → Testar novamente**

Esse processo de melhoria contínua é comum no desenvolvimento profissional de software.

### Relacionando com o App Inventor

No App Inventor, já realizam várias dessas etapas, mesmo quando não percebem:

| Etapa           | Exemplo no App Inventor                    |
| --------------- | ------------------------------------------ |
| Problema        | Definir o que o aplicativo deverá resolver |
| Planejamento    | Definir telas e funcionalidades            |
| Interface       | Criar as telas no Designer                 |
| Desenvolvimento | Programar utilizando Blocks                |
| Dados           | Utilizar recursos como TinyDB              |
| Testes          | Testar com AI Companion                    |
| Correções       | Modificar componentes e blocos             |
| Distribuição    | Gerar uma versão instalável                |
| Manutenção      | Corrigir e acrescentar funcionalidades     |

Portanto, aprender App Inventor não envolve somente saber **encaixar blocos**. O objetivo é compreender um processo maior: **transformar uma necessidade ou problema em uma solução computacional que possa ser utilizada por outras pessoas**.

### Uma ideia importante para fechar o conteúdo

**Fazer o aplicativo funcionar é uma etapa do desenvolvimento. Desenvolver um aplicativo envolve também entender o problema, planejar, construir, testar, corrigir, distribuir e manter a solução.**


## Atividade em Grupo — Ciclo de Vida e Processo de Desenvolvimento

**Disciplina:** Desenvolvimento para Dispositivos Móveis I
**Plataforma:** MIT App Inventor
**Tema:** Ciclo de vida e processo de desenvolvimento de aplicativos móveis
**Entrega:** GitHub do grupo.

### Questão 1 — Antes de desenvolver

Um grupo recebeu a tarefa de desenvolver um aplicativo para ajudar os alunos a organizar trabalhos, provas e atividades escolares. Um dos integrantes sugeriu começar imediatamente criando as telas no App Inventor.

**Antes de iniciar o desenvolvimento, quais decisões o grupo deveria tomar?** Identifiquem pelo menos **quatro informações** que deveriam ser definidas e expliquem por que elas são importantes.

---

### Questão 2 — Funciona, então está pronto?

Durante o desenvolvimento, o grupo terminou a programação e conseguiu executar o aplicativo corretamente uma vez utilizando o **AI Companion**. Por isso, considerou o aplicativo finalizado.

Vocês concordam com essa decisão?

Discutam quais **testes deveriam ser realizados antes de considerar o aplicativo pronto**. Pensem também em situações inesperadas, como dados incorretos, campos vazios e diferentes formas de utilização pelo usuário.

---

### Questão 3 — Mudanças fazem parte do desenvolvimento?

Durante os testes, alguns usuários disseram que não conseguiam entender facilmente como utilizar o aplicativo. Entretanto, todas as funcionalidades estavam funcionando corretamente.

Um integrante afirmou:

> "Se o programa está funcionando, não precisamos mudar nada."

**O grupo concorda ou discorda dessa afirmação?**

Expliquem a decisão e discutam se um problema na interface ou na experiência do usuário pode justificar mudanças em um aplicativo que tecnicamente está funcionando.

---

### Questão 4 — E quando alguma coisa dá errado?

Um aplicativo desenvolvido no App Inventor possui cadastro de informações utilizando o **TinyDB**. Durante os testes, o grupo percebeu que alguns dados não estavam sendo armazenados como esperado.

Em vez de recomeçar todo o projeto, **como o grupo poderia investigar e resolver o problema seguindo um processo organizado de desenvolvimento?**

Descrevam uma sequência de ações envolvendo identificação do problema, testes, correções e novos testes.

---

### Questão 5 — Quando termina o desenvolvimento?

Um grupo terminou seu aplicativo, realizou os testes e disponibilizou a primeira versão para os usuários. Algumas semanas depois, surgiram pedidos de novas funcionalidades e também foi identificado um pequeno erro.

Um integrante afirmou:

> "Nosso projeto já terminou. Depois que o aplicativo é entregue, essas mudanças não fazem mais parte do desenvolvimento."

Com base no conceito de **ciclo de vida do software**, discutam essa afirmação.

**Um aplicativo realmente fica "pronto para sempre"?** Expliquem qual é a importância da manutenção, das correções e da criação de novas versões durante a vida de um aplicativo.


