# Primeio programa do Leo

## 🎞️ Variáveis e Entrada de Dados
### Continuação (Quarto do Leo)

Leo já está com o caderno aberto.

Dessa vez…

organizado.

— Pronto, mano! Hoje eu tô preparado!

Zaion sorri.

— Então vamos começar de verdade.

---

## 🎬 Revisão rápida

— Me diz…

— o que é um dado?

— Informação!

— Pode ser número, texto ou mistura!

— Perfeito.

---

— Agora…

— onde guardamos esses dados?

Pausa.

— Em variáveis.

---

Zaion escreve:

👉 Variável = espaço na memória para guardar dados  

---

## 🎬 Analogia

— É como uma caixa.

— Você coloca algo dentro…

— e pode trocar depois.

---

## 🎬 Exemplo

```
int idade;
````

— Aqui criamos uma variável chamada **idade**.

---

## 🎬 Tipos principais

Zaion escreve:

👉 int → números inteiros

👉 float → números com decimal

👉 char → caractere

👉 char[] → texto

---

— Então o tipo define o que pode guardar?

— Exatamente!

---

## 🎬 Entrada de dados (de verdade)

— Agora vamos fazer o programa conversar com o usuário.

---

## 🎬 Código

```c
#include <stdio.h>

int main() {

    int idade;

    printf("Digite sua idade: ");
    scanf("%d", &idade);

    printf("Você tem %d anos.\n", idade);

    return 0;
}
```

---

## 🎬 Explicação rápida

— Aqui temos:

👉 scanf → entrada
👉 printf → saída
👉 %d → número inteiro
👉 &idade → onde guardar

---

— Por que agora tem esse &?

— Porque idade é uma variável simples.

👉 precisamos informar o endereço dela

— Lembra do nome?

👉 char nome[50] → sem &

```
scanf("%s", nome);
```

— Agora:

👉 int idade → com &

```
scanf("%d", &idade); 
```

---


— Então…

— número usa &

— texto não?

— Isso!

---

## 🎬 Mini desafio

— Agora você.

— Crie um programa que:

👉 leia o nome
👉 leia a idade
👉 mostre:

"Olá, Leo! Você tem 13 anos."

---

Leo começa a escrever.

Erra.

Apaga.

Tenta de novo.

---

— Mano…

— agora eu sei por onde começar.

Zaion observa.

Sem interferir.

---

— Consegui!

---

## 🎬 Código do Leo

```c
#include <stdio.h>

int main() {

    char nome[50];
    int idade;

    printf("Digite seu nome: ");
    scanf("%s", nome);

    printf("Digite sua idade: ");
    scanf("%d", &idade);

    printf("Olá, %s! Você tem %d anos.\n", nome, idade);

    return 0;
}
```

---

Zaion sorri.

— Agora sim.

— Você começou.

---

Leo olha para o código.

Dessa vez…

com orgulho.

— Acho que agora…

— eu não preciso mais copiar.

|[` < voltar `](08-segundo-dia-como-professor.md)| [` avançar > `](10-pensar-antes-de-digitar.md)|
|--------|-----|