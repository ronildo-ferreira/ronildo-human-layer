# Programação avançada

(De volta em casa, no quarto, Leo já os aguardava, curioso, com o computador ligado.)

---

— Finalmente! Pensei que vocês iam demorar mais!

— Desculpa, Leo… o dia foi corrido… — responde Zaion, cansado, mas tentando sorrir.

---

— Tudo bem!

— Mas… você prometeu ensinar:

👉 string  
👉 vetores  
👉 função  

— Lembra?

---

Zaion olha para Ryo.

Ele apenas dá de ombros.

Mais calmo.

E segue para o quarto.

---

— Está certo…

— promessa é promessa.

— Vamos lá.

---

# 🧠 Aula 1 — String (texto de verdade)

---

— Leo…

— lembra quando usamos:

```c
char nome[50];
````

— Sim.

---

— Isso funciona…

— mas é complicado.

---

— Em C++, temos algo melhor:

```cpp
#include <string>

string nome;
```

---

— Isso se chama **string**.

👉 texto pronto
👉 mais fácil de usar

---

— Então não preciso mais daquele `[50]`?

— Exatamente.

---

— Vamos testar:

```cpp
string nome;

cout << "Digite seu nome: ";
cin >> nome;

cout << "Olá, " << nome << "\n";
```

---

— Simples… — diz Leo.

---

# 🧠 Aula 2 — Vetores (listas)

---

— Agora imagine…

— vários valores ao mesmo tempo.

---

— Tipo vários números?

— Isso.

---

```cpp
int notas[3] = {7, 8, 9};
```

---

— Isso é um **vetor**.

👉 vários valores
👉 na mesma variável

---

— Como acessa?

---

```cpp
cout << notas[0];
```

---

— Começa no zero?

— Sempre.

---

# 🧠 Aula 3 — Função (organizar código)

---

— Agora o mais importante…

— função.

---

— O que é isso?

---

— É um bloco de código com um nome.

👉 você chama
👉 ele executa

---

## 🎬 Exemplo

```cpp
void mensagem() {
    cout << "Olá, Leo!\n";
}
```

---

— Para usar:

```cpp
mensagem();
```

---

— Então é tipo um comando que eu crio?

— Exatamente!

---

# 🧠 Integração (tudo junto)

---

— Agora vamos juntar tudo:

```cpp
#include <iostream>
#include <string>

using std::cout;
using std::cin;
using std::string;

void saudacao(string nome) {
    cout << "Olá, " << nome << "!\n";
}

int main() {
    string nome;

    cout << "Digite seu nome: ";
    cin >> nome;

    saudacao(nome);

    return 0;
}
```

---

## 🎬 Reação

Leo olha para o código.

Dessa vez…

sem travar.

---

— Agora eu entendi…

— não é mais só comando…

— dá pra construir coisas.

---

Zaion sorri.

— Agora você começou a programar de verdade.

|[` < voltar `](05-03-no-shopping.md)| [` avançar > `](05-05-de-vogal-em-vogal.md)|
|--------|-----|