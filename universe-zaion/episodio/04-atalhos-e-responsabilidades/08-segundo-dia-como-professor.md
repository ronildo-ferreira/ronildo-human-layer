
## Biblioteca e Comentários (ponte entre linguagens)

(Quarto do Leo — continuação da aula)

Zaion escreve no quadro:

```
#include <stdio.h>

int main() {
	printf("Olá, Leo!\n");
    return 0;
}
````

---


— Leo, lembra disso:

👉 Cada linguagem tem suas regras.

— Não é porque existe a palavra "if" no inglês e no C…

— que elas significam exatamente a mesma coisa.

— Ok?

— Ok!

---

## O que é linguagem C

— Então C é a linguagem que o computador fala? — pergunta Leo.

— Podemos pensar assim.

— Mas na verdade…

👉 é uma linguagem que NÓS usamos
👉 para conversar com o computador

---

##  Primeiro conceito (biblioteca)

Leo aponta:

— Mano… o que é isso aqui?

```
#include <stdio.h>
```

— Isso se chama **biblioteca**.

>👉 #include = incluir
>
>👉 <stdio.h> = biblioteca pronta


— Biblioteca é como…

— um conjunto de ferramentas prontas.

— Alguém já fez.

— Você só usa.

---

— Muito bem, Zaion!

— Você está sendo um bom professor para ele.

_ Obrigado, Zahy, mas não seria o mesmo sem seu apoio..


---


— É reaproveitamento de código.

— Você não precisa reinventar tudo.

— E essa biblioteca faz o quê?

— Ela permite:

>👉 mostrar coisas na tela
>
>👉 ler o que o usuário digita

---

— Ou seja...

>👉 printf → fala
>
>👉 scanf → escuta


— Então é tipo a voz e os ouvidos do programa?

— Exatamente!

# 🧠 Estrutura do Programa

---

## Código

```
int main() {
    return 0;
}
```

---

— Isso é a função principal.

👉 main = começo do programa

👉 Todo programa começa aqui

— E isso?

```c
return 0;
```

---

👉 0 = terminou bem
👉 outro número = erro

---

— Então 0 é tipo "tudo certo"?

— Exatamente.

---


Zaion escreve abaixo:

---

# 💻 Exemplo em C — Ler nome e exibir mensagem

```c
/*
Programa: Leitura de nome e mensagem de boas-vindas
Objetivo: Ler o nome do usuário e exibir uma mensagem personalizada
Autor: Zahroniel Syrran
*/

#include <stdio.h> // Biblioteca padrão para entrada e saída (printf e scanf)

int main() { 

    // Declaração de variável para armazenar texto (até 49 caracteres + '\0')
    char nome[50];

    printf("Digite seu nome: "); // Exibe mensagem na tela

    scanf("%s", nome); // Lê o nome digitado pelo usuário (sem espaços)

    printf("Prazer em te conhecer, %s!\n", nome); // Exibe mensagem com o nome

    return 0; // Indica que o programa terminou com sucesso
}
```

# 🔍 Explicação linha por linha

## 🧠 1. Comentário de bloco

```c
/*
...
*/
```

👉 Usado para descrever o programa

👉 Pode ter várias linhas

👉 O computador ignora

---

## 📚 2. Biblioteca

```c
#include <stdio.h>
```

👉 Inclui funções prontas

👉 Aqui usamos:

* `printf()` → saída
* `scanf()` → entrada

---

## 🚀 3. Função principal

```c
int main() {
```

👉 Ponto de entrada do programa

👉 Tudo começa aqui

---

## 📦 4. Variável

```c
char nome[50];
```

👉 `char` → tipo texto (caractere)

👉 `[50]` → espaço para até 50 caracteres

---

## 🖥️ 5. Saída (mostrar mensagem)

```c
printf("Digite seu nome: ");
```

👉 Mostra texto na tela

---

## ⌨️ 6. Entrada (ler dados)

```c
scanf("%s", nome);
```

👉 `%s` → formato para texto

👉 `nome` → onde será armazenado

⚠️ Importante:

* lê apenas **uma palavra (sem espaço)**

---

## 🗣️ 7. Saída com variável

```c
printf("Prazer em te conhecer, %s!\n", nome);
```

👉 `%s` → substituído pelo valor de `nome`
👉 `\n` → quebra de linha

---

## 🏁 8. Finalização

```c
return 0;
```

👉 0 - Indica que deu tudo certo

---


Leo aponta:

```c
/* comentário */
```

— E isso aqui?

— Isso é um comentário.

---

##  Tipos

👉 // comentário de uma linha

👉 /* comentário de várias linhas */

---

👉 O computador IGNORA.

— Então por que escrever?

— Para humanos.

— Não para o computador.

— É como anotar no caderno.

— Ou marcar um livro.

---

— Comentários ajudam:

👉 entender

👉 organizar

👉 manter o código

---

— Então isso aqui:

```c
// começo do programa
```

— o computador ignora…

— mas ajuda quem lê.

— Exatamente!

---


Leo olha para o código.

Dessa vez…

sem medo.

— Agora eu entendi…

— não é decorar…

— é entender as peças.

Zaion sorri.

— Exatamente.

---

Leo aponta para o topo do código.

— Só não entendi uma coisa…

— Quem é Zahroniel Syrran?

---

Zaion hesita por um instante.

---

— Esse é o seu nome, Zahy?

— Sim…

---

— Ah…

— É só um exemplo…

— E amanhã…

— a gente começa a programar de verdade.

|[` < voltar `](07-primeira-aula-de-c.md)| [` avançar > `](09-primiero-programa-do-leo.md)|
|--------|-----|
