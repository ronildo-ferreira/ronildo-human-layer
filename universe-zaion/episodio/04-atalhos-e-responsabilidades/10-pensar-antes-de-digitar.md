# Pensar antes de digitar

— Agora vamos fazer um programa de verdade!

— Espera, vou buscar meu notebook! — disse Leo, já se levantando.

— Calma aí! — interrompeu Zaion. — Não precisamos do computador ainda.

— Como assim? Não dá pra programar sem computador… — Leo fez uma careta.

— Lembra que eu te falei que programar é uma arte?  
Antes de digitar qualquer coisa, temos que pensar no problema, transformá-lo em partes, estudar cada parte e fazer um esboço.

— Só depois disso partimos para o computador.  
Aí escrevemos o código, adicionamos comentários e testamos até funcionar do jeito esperado.

— Entendeu?

— Sim… mas isso é muito chato! Prefiro ir direto.

— Lembre-se: você já tentou atalhos antes… e onde isso te levou?

— Tá bom… entendi… — respondeu contrariado.

---

— Vamos trabalhar neste exercício:

👉 "Ler um **ano** e verificar se ele é **bissexto**."

---

— Vamos seguir estes passos:

1. Ler o enunciado várias vezes  
2. Interpretar logicamente  
3. Identificar o que o programa precisa fazer  
4. Identificar: entrada, processamento e saída  
5. Estabelecer um raciocínio passo a passo  
6. Escrever pequenos trechos que serão implementados  
7. Fazer um resumo do que foi aprendido  

---

— Tem que fazer tudo isso?

— Claro! Aprendendo esses passos, não importa o tamanho do programa, você vai conseguir.

---

— Você sabe o que é um ano bissexto?

— Sim! É um ano que tem um dia a mais em fevereiro.

— Isso mesmo. Isso acontece porque o ano real não tem exatamente 365 dias.

— Muito bem! E como calculamos isso?

👉 Um ano é bissexto quando:

- É divisível por **4**, **mas não** por **100**,  
- **Ou** é divisível por **400**

---

— Ótimo. Já podemos escrever o primeiro passo.

---

## 📌 Enunciado

Ler um **ano** e verificar se ele é **bissexto**.

O programa deve exibir o ano informado e indicar se ele é ou não bissexto.

---

## 🔍 Interpretação lógica

Este problema envolve uma regra com exceção:

- Verificar apenas `ano % 4 == 0` não é suficiente  
- Anos divisíveis por **100** não são bissextos  
- **Exceto** quando também são divisíveis por **400**

👉 Temos uma lógica com **E (&&)** e **OU (||)**

---

— Está entendendo?

— Sim… mas eu só pensava no dia 29 de fevereiro.

— Isso é o efeito. Aqui estamos estudando a causa.

---

## ⚙️ O que o programa precisa fazer

- Ler um ano  
- Aplicar a regra de ano bissexto  
- Exibir o resultado  

---

## 📥 Entrada

- Ano (número inteiro)

---

## 🔄 Processamento

```
(ano % 4 == 0 && ano % 100 != 0) || (ano % 400 == 0)
````

---

## 📤 Saída

* Informar se o ano é ou não bissexto

---

— Nossa é bem simples

— Sim... mas nem sempre.

— Vamos deixar o mais proximo possivel de um pragama, usando uma série de passos.

---

### 🧩 Raciocínio passo a passo

1. Declarar uma variável para armazenar o ano
2. Ler o valor digitado
3. Verificar se é divisível por 4 **e não por 100**
4. Verificar a exceção: divisível por 400
5. Combinar as condições com operador lógico
6. Exibir o resultado final

---

— Vamos escrever como ficaria a implementação, o mais simples possível

---

### 💡 Exemplo de implementação

```
inteiro ano

leia(ano)

se ((ano % 4 == 0 e ano % 100 != 0) ou (ano % 400 == 0)) {
   escreval(ano, " é bissexto")
}
senao {
   escreval(ano, " não é bissexto")
}
```

---

— Não entendi o que você escreveu, mano.

— Leo isso é Portugol. Você já estudou isso.

— É mas... não me lembro de muita coisa...

— Na importa. Vamos escrever em "C"

---

```
inteiro ano

```
— Em "C" fica:

```
int ano;
```

---
 
```
leia(ano)
```
— Em "C" fica:


```
scanf("%d",&ano);
```
---

— e por fim...

```
se ((ano % 4 == 0 e ano % 100 != 0) ou (ano % 400 == 0)) {
   escreval(ano, " é bissexto");
}
senao {
   escreval(ano, " não é bissexto");
}
```

— Em "C" fica:

```
if (((ano % 4 == 0) && (ano % 100 != 0)) || (ano % 400 == 0)) {
   printf("%d é bissexto",ano)
}
senao {
   printf("%d é bissexto",ano)
}
```


---

— Finalizando:


```

int ano;

scanf("%d",&ano);

if (((ano % 4 == 0) && (ano % 100 != 0)) || (ano % 400 == 0)) {
   printf("%d é bissexto",ano)
}
senao {
   printf("%d é bissexto",ano)
}
```

---

### ✅ Resumo

✔️ Use `%` para verificar divisibilidade

✔️ Use `==` para comparação de igualdade

✔️ Use `!=` para diferente

✔️ Operador lógico `e` é `&&`

✔️ Operador lógico `ou` é `||`

✔️ Atenção à **regra especial dos múltiplos de 100 e 400**

👉 Esse é um dos exercícios clássicos para treinar **lógica condicional composta**.

---

— Ficou claro?

— Sim… mas dá trabalho.

— Dá.

— Mas agora você sabe fazer.

---

Leo olha para o código…

Respira fundo…

E começa a escrever.

---

```
/*
Programa: Ler um ano e verificar se ele é bissexto.
Objetivo: Ler o nome do usuário e exibir uma mensagem personalizada
Autor: Leo Alexander Zanarelli
*/

#include <stdio.h>

int main() {
	int ano;

	// Ler o ano
	printf("Digite o ano que quer sabe se é bisseto: ")
	scanf("%d",&ano);
	
	// Calcular e verificar
	if (((ano % 4 == 0) && (ano % 100 != 0)) || (ano % 400 == 0)) {
   		printf("%d é bissexto\n",ano)
	} senao {
   		printf("%d é bissexto\n",ano)
	}
    return 0;
}
````
---

— Muito bem, Leo…

— Hoje você aprendeu a pensar como programador.


