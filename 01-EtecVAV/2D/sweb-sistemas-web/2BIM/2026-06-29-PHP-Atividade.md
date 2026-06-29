# 📚 Atividade de Pesquisa — PHP

## Tema

**Funções para Criptografia, Hash, Codificação e Proteção de Dados em PHP**

---

## 🎯 Objetivo

Pesquisar os principais recursos disponíveis na linguagem **PHP** para proteger informações, armazenar senhas com segurança, codificar dados e reduzir riscos de ataques em aplicações web.

O objetivo desta atividade é compreender a importância da segurança da informação durante o desenvolvimento de sistemas, além de desenvolver habilidades de pesquisa, organização e documentação técnica.

---

## 👥 Modalidade

- Atividade em **grupo**.

---

## 📅 Entrega

- Produzir o trabalho em formato **Markdown (`.md`)**.
- Enviar o arquivo pelo **Microsoft Teams**.
- Como esta atividade faz parte do **portfólio da disciplina**, o mesmo arquivo também deverá ser publicado no **GitHub do grupo**, seguindo a organização do repositório.
- Seguir todas as orientações apresentadas no **PDF disponibilizado pelo professor**.

> **Importante:** Como esta atividade também será utilizada para registro de frequência, **todos os integrantes do grupo deverão enviar exatamente o mesmo arquivo no Microsoft Teams**.

---

# 📖 Roteiro da Pesquisa

A pesquisa deve responder, no mínimo, às seguintes questões.

## 1. Segurança em aplicações Web

Explique:

- O que é segurança da informação.
- Por que proteger os dados dos usuários.
- Quais são os principais riscos em aplicações desenvolvidas para a Internet.

---

## 2. Criptografia, Hash e Codificação

Pesquise e explique a diferença entre:

- Criptografia
- Hash
- Codificação (Encoding)

Apresente exemplos de utilização de cada técnica.

---

## 3. Funções de Hash no PHP

Pesquise as principais funções utilizadas para gerar hashes.

Explique:

- `password_hash()`
- `password_verify()`
- `hash()`

Responda também:

- Para que servem?
- Quando devem ser utilizadas?
- Quais algoritmos são recomendados atualmente?

---

## 4. Funções de Codificação

Pesquise as funções:

- `base64_encode()`
- `base64_decode()`

Explique:

- Para que servem.
- Em quais situações podem ser utilizadas.
- Por que **Base64 não é criptografia**.

---

## 5. Criptografia no PHP

Pesquise a biblioteca **OpenSSL** utilizada pelo PHP.

Explique:

- O que é OpenSSL.
- Para que serve.
- Quais funções podem ser utilizadas para criptografar e descriptografar informações.

---

## 6. Proteção de Senhas

Explique:

- Como uma senha deve ser armazenada corretamente.
- Por que nunca devemos salvar senhas em texto puro.
- O que é *salt*.
- O que torna um algoritmo de hash seguro.

---

## 7. Proteção contra Ataques

Pesquise como o PHP pode ajudar a prevenir ataques como:

- SQL Injection
- Cross-Site Scripting (XSS)
- Cross-Site Request Forgery (CSRF)

Explique brevemente cada ataque e apresente formas de prevenção.

---

## 8. Aplicações Práticas

Pesquise situações reais em que esses recursos são utilizados.

Exemplos:

- Sistemas de login;
- Comércio eletrônico;
- Internet Banking;
- Redes sociais;
- Sistemas escolares;
- Aplicativos de gerenciamento de usuários.

Explique por que essas técnicas são importantes nesses sistemas.

---

## 9. Boas Práticas de Segurança

Pesquise recomendações para desenvolver aplicações PHP mais seguras.

Exemplos:

- validar entradas do usuário;
- utilizar consultas preparadas (*Prepared Statements*);
- proteger sessões;
- utilizar HTTPS;
- manter o PHP atualizado;
- proteger arquivos de configuração.

---

## 10. Conclusão

Escreva um pequeno texto respondendo:

- Qual a importância da segurança em aplicações web?
- Qual recurso pesquisado você considera mais importante?
- Quais conhecimentos o grupo adquiriu durante esta pesquisa?

---

# 📚 Referências

A pesquisa deverá conter:

- citações ao longo do texto;
- referências bibliográficas elaboradas conforme as **normas da ABNT**.

Podem ser utilizadas:

- documentação oficial do PHP;
- documentação do OpenSSL;
- livros;
- artigos científicos;
- sites confiáveis sobre desenvolvimento web e segurança da informação.

Evite utilizar blogs ou páginas sem autoria identificada.

---

# 📝 Formatação

O trabalho deverá ser produzido em **Markdown (`.md`)**.

Organize o documento utilizando:

- títulos;
- subtítulos;
- listas;
- tabelas (quando necessário);
- imagens ou diagramas para ilustrar os conceitos.

> **Não é necessário desenvolver códigos completos nesta atividade.** O foco é compreender os conceitos e identificar as principais funções utilizadas em PHP.

---

# 📂 Organização no GitHub

O trabalho deverá ser armazenado no repositório do grupo.

Exemplo:

```
php-seguranca/
│
├── README.md
├── pesquisa-seguranca-php.md
├── imagens/
└── referencias/
```

---

# ✅ Critérios de Avaliação

Serão avaliados os seguintes aspectos:

### 1. Pesquisa

- qualidade das informações;
- profundidade do conteúdo;
- uso de fontes confiáveis.

### 2. Organização

- estrutura do documento;
- clareza da escrita;
- uso adequado do Markdown.

### 3. Conteúdo Técnico

- compreensão dos conceitos de criptografia, hash e codificação;
- explicação correta das funções do PHP;
- entendimento das boas práticas de segurança.

### 4. Normas Acadêmicas

- uso correto de citações;
- referências conforme as normas ABNT.

### 5. Organização no GitHub

- estrutura do repositório;
- histórico de commits;
- participação dos integrantes.

---

# 💡 Dicas

- Consulte a documentação oficial do PHP antes de iniciar a pesquisa.
- Compare diferentes fontes para validar as informações.
- Utilize exemplos para facilitar a compreensão dos conceitos.
- Escreva o texto com suas próprias palavras.
- Faça commits frequentes durante o desenvolvimento do trabalho.
- Revise o conteúdo antes da entrega.
- Lembre-se de que **Base64 não substitui criptografia** e que **senhas devem ser protegidas com funções específicas de hash**, como `password_hash()`.

---
