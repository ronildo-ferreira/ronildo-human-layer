<p align="center"><strong>Syrran Tech Academy</strong><br>
CTJ - Colégio Técnico Jundiaí - sp<br>  
Técnico em Desenvolvimento de Sistemas – 2026 
</p>

<p align="right">Artigo desenvolvido na disciplina de Desenvolvimento de Sistemas sob orientação do professor Zahroniel Syrran.</p>

<p align="center">GIT E GITHUB: CONTROLE DE VERSÃO E COLABORAÇÃO EM PROJETOS DE SOFTWARE</p>

<p align="right">
Beta Sette Zeta<br>
Kael Élodie Whitmore<br>
Zaion Alaric Zanarelli<br>
</p>

---

## RESUMO

<p align="justify">Este estudo tem o objetivo de analisar o uso do Git e do GitHub como ferramentas de controle de versão e colaboração em projetos de software. Dentre os autores pesquisados para a constituição conceitual deste trabalho, destacam-se Chacon (2014), Loeliger (2012) e Torvalds (2005). A metodologia utilizada foi a pesquisa exploratória, tendo como coleta de dados o levantamento bibliográfico. As conclusões mais relevantes indicam que o uso dessas ferramentas contribui significativamente para a organização, rastreabilidade e desenvolvimento colaborativo de projetos, sendo essencial no contexto educacional e profissional da área de tecnologia.</p>

Palavras-chave: Tecnologia. Versionamento. Git. GitHub. Colaboração.

---

## INTRODUÇÃO

<p align="justify">No desenvolvimento de software, o controle de alterações é um dos principais desafios enfrentados por programadores e equipes. A necessidade de registrar mudanças, evitar perdas de dados e permitir colaboração simultânea levou à criação de sistemas de controle de versão, como o Git (CHACON, 2014).</p>

<p align="justify">O presente estudo delimita-se à análise do funcionamento do Git e do GitHub, abordando conceitos fundamentais, comandos básicos e formas de integração entre ambiente local e remoto.</p>

<p align="justify">O objetivo geral é compreender como o Git e o GitHub contribuem para o controle de versões e a colaboração em projetos de software.</p>

<p align="justify">Esta pesquisa justifica-se pela relevância dessas ferramentas no mercado de trabalho, sendo amplamente exigidas em projetos profissionais e acadêmicos na área de tecnologia.</p>

<p align="justify">A metodologia deste trabalho é a pesquisa exploratória, tendo como coleta de dados o levantamento bibliográfico.</p>

---

## CONCEITO DE GIT

<p align="justify">O Git é um sistema de controle de versão distribuído, criado por Linus Torvalds em 2005, com o objetivo de gerenciar o desenvolvimento do kernel do Linux (TORVALDS, 2005).</p>

<p align="justify">Segundo Chacon (2014), o Git permite registrar alterações em arquivos ao longo do tempo, possibilitando que versões anteriores sejam recuperadas.</p>

<p align="justify">De acordo com Chacon (2014), “o Git armazena snapshots do projeto ao invés de apenas diferenças entre arquivos”, o que garante maior eficiência e confiabilidade.</p>

<p align="justify">No contexto educacional, pode-se comparar o Git a uma “linha do tempo inteligente”, onde cada alteração representa um ponto de evolução do projeto — semelhante à forma como Zaion percebe mudanças em sua própria realidade.</p>

---

## HISTÓRICO E CONTEXTO

<p align="justify">Antes do Git, sistemas centralizados eram amplamente utilizados, o que gerava dependência de servidores únicos e riscos de perda de dados (LOELIGER, 2012).</p>

> <p align="justify"><sub>Os sistemas de controle de versão tradicionais dependiam de um servidor central, o que criava um ponto único de falha. Caso esse servidor fosse comprometido, todo o histórico do projeto poderia ser perdido (LOELIGER, 2012, p.45).</sub></p>

<p align="justify">Com o surgimento do Git, esse modelo foi substituído por um sistema distribuído, garantindo maior segurança e flexibilidade.</p>

---

## INSTALAÇÃO E DOWNLOAD

<p align="justify">O Git pode ser instalado a partir do site oficial https://git-scm.com, estando disponível para diferentes sistemas operacionais.</p>

<p align="justify">Após a instalação, recomenda-se configurar o usuário:</p>

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu@email.com"
```

<p align="justify">Essa configuração permite identificar o autor de cada alteração realizada no projeto.</p>

---

## COMANDOS BÁSICOS

<p align="justify">Os comandos básicos do Git são fundamentais para o controle de versões:</p>

```bash
git init
git add .
git commit -m "mensagem"
git status
git log
```

<p align="justify">Esses comandos permitem iniciar um projeto, registrar alterações e visualizar o histórico de versões.</p>

---

## EXEMPLOS PRÁTICOS

<p align="justify">Considere um projeto simples:</p>

```bash
git init
git add index.html
git commit -m "primeira versão"
```

<p align="justify">Após alterações:</p>

```bash
git add .
git commit -m "atualização do projeto"
```

<p align="justify">Esse processo permite acompanhar a evolução do sistema ao longo do tempo.</p>

---

## GITHUB: CONCEITO E FINALIDADE

<p align="justify">O GitHub é uma plataforma de hospedagem de código baseada no Git, permitindo colaboração entre desenvolvedores.</p>

<p align="justify">Segundo a documentação oficial, “o GitHub permite que equipes trabalhem juntas em projetos, mantendo um histórico completo de alterações” (GITHUB, 2024).</p>

---

## CRIAÇÃO DE CONTA

<p align="justify">Para utilizar o GitHub, o usuário deve criar uma conta em https://github.com, possibilitando a criação e gerenciamento de repositórios.</p>

---

## INTEGRAÇÃO GIT + GITHUB

<p align="justify">A integração entre Git e GitHub permite sincronizar repositórios locais e remotos:</p>

```bash
git clone URL
git push origin main
git pull origin main
```

<p align="justify">Esses comandos permitem colaboração em equipe e atualização contínua dos projetos.</p>

---

## REPRESENTAÇÃO DO FLUXO GIT

<p align="justify">O fluxo básico do Git pode ser representado conforme a figura a seguir:</p>

<p align="center">
Figura 1: Fluxo básico do Git<br>  
<img src="img/git-fluxo.png" width="400"><br>
Fonte: Elaborado pelos autores  
</p>

<p align="justify">O fluxo representa o ciclo de desenvolvimento, desde a modificação do código até sua publicação em repositórios remotos.</p>

---

## DISCUSSÕES E RESULTADOS

<p align="justify">A análise demonstrou que o Git e o GitHub são ferramentas essenciais para o desenvolvimento moderno, permitindo maior organização e colaboração.</p>

<p align="justify">Observa-se que o conceito de versionamento contribui para o desenvolvimento do pensamento lógico e estruturado dos estudantes.</p>

---

## CONSIDERAÇÕES FINAIS

<p align="justify">O estudo evidenciou a importância do Git e do GitHub no desenvolvimento de software, destacando sua aplicação no contexto educacional e profissional.</p>

<p align="justify">Como sugestão futura, recomenda-se aprofundar o estudo em funcionalidades avançadas, como branches, merge e resolução de conflitos.</p>

---

## REFERÊNCIAS

CHACON, Scott. Pro Git. 2014.

LOELIGER, Jon. Version Control with Git. 2012.

TORVALDS, Linus. Git Documentation. 2005.

Git. Disponível em: https://git-scm.com/

GitHub. Disponível em: https://github.com/
