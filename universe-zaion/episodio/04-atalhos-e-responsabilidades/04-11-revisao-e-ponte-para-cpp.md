# Revisão — Repetição e ponte para C++

---

— Hoje vamos fazer uma revisão.

— Mas antes…

— vamos aprender um comando MUITO importante.

---

## 🔁 Laço de repetição — while

Zaion escreve:

```

while (condição) {
// comandos
}

```

---

— Esse comando serve para repetir um bloco de código

👉 ENQUANTO a condição for verdadeira

---

## 🎬 Exemplo simples

```

int a = 1;

while (a <= 5) {
printf("a = %d\n", a);
a++;
}

```

---

— Isso vai mostrar:

```

a = 1
a = 2
a = 3
a = 4
a = 5

````

---

— O que é esse `a++`?

— Isso se chama **incremento**.

👉 `a++` = `a = a + 1`

---

## 📌 Regra importante

👉 Incremento = aumentar valor  
👉 Decremento = diminuir valor  

---

## 💡 Agora um exemplo de verdade

— Vamos usar isso para gerar uma tabuada.

---

```c
#include <stdio.h>

int main() {
    int tabuada, i;

    printf("Qual tabuada deseja: ");
    scanf("%d", &tabuada);

    i = 0;

    while (i <= 10) {
        printf("%d x %d = %d\n", i, tabuada, i * tabuada);
        i++;
    }

    return 0;
}
````

---

— Entendi… — disse Leo, meio preocupado.

— Que foi?

— É que o professor falou que tem que ser em C++…

---

## 🔄 Ponte C → C++

— Não se preocupe — disse Zaion.

— A lógica é a mesma.

— Só mudamos a forma de escrever.

---

## 🔁 Conversão

👉 Biblioteca:

```
#include <stdio.h>
```

👉 vira:

```
#include <iostream>
```

---

👉 Saída:

```
printf("Texto");
```

👉 vira:

```
std::cout << "Texto";
```

---

👉 Entrada:

```
scanf("%d", &tabuada);
```

👉 vira:

```
std::cin >> tabuada;
```

---

## 💻 Código em C++

```
#include <iostream>

int main() {
    int tabuada, i;

    std::cout << "Qual tabuada deseja: ";
    std::cin >> tabuada;

    i = 0;

    while (i <= 10) {
        std::cout << i << " x " << tabuada << " = " << i * tabuada << "\n";
        i++;
    }

    return 0;
}
```

---

— O que é esse `std::`?

---

## 🧠 Explicação

— `std` é a biblioteca padrão do C++.

— `::` significa:

👉 "pegue algo de dentro dela"

---

## 💡 Tradução

👉 std::cout → saída padrão
👉 std::cin → entrada padrão

---

## ⚠️ Forma alternativa

— Dá pra evitar escrever `std::`.

---

```
using namespace std;
```

---

— Mas…

👉 não é recomendado em programas maiores

---

## ✅ Forma mais correta

```
using std::cout;
using std::cin;
```
---

— Então C++ é só um C melhorado?

— Podemos dizer que sim…

— Ele tem mais recursos…

— e facilita várias coisas.

---

Leo olha para o código.

Dessa vez…

com confiança.

— Agora eu começo a entender…

---

— Então o programa fica assim:

```

#include <iostream>

using std::cout;
using std::cin;

int main() {
	int tabuada, i;

	cout << "Qual tabuada deseja: ";
	cin >> tabuada;

	i = 0;

	while (i <= 10) {
    	cout << i << " x " << tabuada << " = " << i * tabuada << "\n";
    	i++;
	}

	return 0;
```

}

---

— Isso mesmo. Você entendeu.

---

Leo observa mais um pouco.

— Então… só existe esse tipo de repetição?

---

Zaion sorri de leve.

— Não.

— Esse é só o primeiro que estamos aprendendo.

---

— Existem outros tipos…

👉 for  
👉 do...while  

---

— Cada um é usado em situações diferentes.

— Mas todos seguem a mesma ideia:

👉 repetir algo enquanto uma condição for verdadeira

---

— A diferença é como você organiza isso.

---

Leo cruza os braços, pensando.

— Então… não é decorar comandos…

— é entender o padrão.

---

Zaion confirma.

— Exatamente.

— E quando você entende isso…

— qualquer linguagem começa a fazer sentido.

---


|[` < voltar `](04-10-pensar-antes-de-digitar.md)| [` avançar > `](../05-entre-irmaos-e-lacos-digitais/05-01-discussao-na-sala-de-aula.md)|
|--------|-----|
