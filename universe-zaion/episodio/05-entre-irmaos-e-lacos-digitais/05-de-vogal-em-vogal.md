# O programa mais difícil que já fiz

## Vamos à prática

— Agora vamos juntar tudo:

👉 string  
👉 vetor  
👉 função  

---

— Programa das vogais!

— Parece difícil…

— mas não é, veja…

---

## 💻 Código (com string + vetor + função)

```cpp
#include <iostream>
#include <string>
#include <cctype> // para tolower

using std::cout;
using std::cin;
using std::string;

// Função para contar vogais
void contarVogais(string frase) {

    int vogais[5] = {0, 0, 0, 0, 0}; // vetor: a, e, i, o, u

    for (int i = 0; i < frase.size(); i++) {
        char c = tolower(frase[i]);

        if (c == 'a') vogais[0]++;
        else if (c == 'e') vogais[1]++;
        else if (c == 'i') vogais[2]++;
        else if (c == 'o') vogais[3]++;
        else if (c == 'u') vogais[4]++;
    }

    cout << "\nQuantidade de vogais:\n";
    cout << "a: " << vogais[0] << "\n";
    cout << "e: " << vogais[1] << "\n";
    cout << "i: " << vogais[2] << "\n";
    cout << "o: " << vogais[3] << "\n";
    cout << "u: " << vogais[4] << "\n";
}

int main() {

    string frase;

    cout << "Digite uma frase: ";
    std::getline(cin, frase);

    contarVogais(frase);

    return 0;
}
```

---

## 🧠 Parte 1 — string

— Leo, lembra disso?

```cpp
string frase;
````

— Isso guarda uma frase inteira.

---

— E para ler tudo:

```cpp
getline(cin, frase);
```

— Agora sim pega frase completa.

---

## 🧠 Parte 2 — vetor

— Em vez de várias variáveis…

```cpp
int a=0, e=0, i=0...
```

— vamos usar vetor:

```cpp
int vogais[5] = {0,0,0,0,0};
```

---

— Cada posição representa:

👉 [0] = a
👉 [1] = e
👉 [2] = i
👉 [3] = o
👉 [4] = u

---

## 🧠 Parte 3 — função

— Agora o mais importante…

— vamos separar o código.

```cpp
void contarVogais(string frase)
```

---

— Isso é uma função.

👉 recebe a frase
👉 processa
👉 mostra resultado

---

— Então…

— a função faz o trabalho pesado.

---

## 🧠 Parte 4 — percorrer a string

```cpp
for (int i = 0; i < frase.size(); i++)
```

---

— Isso percorre cada letra.

---

## 🧠 Parte 5 — acessar letra

```cpp
frase[i]
```

---

— Igual vetor.

— pega letra por letra.

---

## 🧠 Parte 6 — padronizar

```cpp
tolower(frase[i])
```

---

— transforma em minúscula.

---

## 🧠 Parte 7 — contagem

```cpp
if (c == 'a') vogais[0]++;
```

---

— incrementa o contador.

---

## 🎬 Reação

Leo observa.

Sem travar.

---

— Agora eu entendi…

— string guarda tudo…

— vetor organiza…

— função separa…

---

Zaion sorri.

---

— Agora você não está mais copiando.

— Você está programando.

---

Pausa.

---

— Leo…

— eu já te ensinei o suficiente para você seguir sozinho.

---

Leo olha para o código na tela.

Dessa vez…

com segurança.

---

— Eu sei.

---

— Para treinar para a prova…

— vou deixar uma lista de exercícios em C++.

---

— Pode deixar, mano…

Pausa.

---

— Eu vou fazer.

— E dessa vez…

— sem copiar.

---

Zaion observa.

Orgulhoso.

---

— É assim que começa.

---

(Leo volta para o computador.)

Agora não como alguém que tenta…

Mas como alguém que constrói.

|[` < voltar `](04-programacao-avancada.md)| [` avançar > `](06-no-quarto-de-ryo.md)|
|--------|-----|
