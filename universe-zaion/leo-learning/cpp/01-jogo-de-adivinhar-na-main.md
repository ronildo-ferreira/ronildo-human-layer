# Jogo de adivinhar um número

— Hoje vamos aprender a dividir um programa em partes menores, que podem ser reutilizadas sempre que quisermos. É assim que começamos a criar nossas próprias bibliotecas de funções — explicou Zaion.

— E como vamos fazer isso? — perguntou Leo, curioso.

— Com um mini-jogo. Simples, mas muito útil para treinar lógica.

Zaion se inclinou um pouco na cadeira e começou a explicar com calma:

— O programa vai sortear um número inteiro de 1 a 100.

— Você terá cinco chances para adivinhar.

— A cada tentativa, o programa verifica o seu palpite.

— Se você acertar, ele avisa.

— Se errar, ele informa se o número sorteado é maior ou menor do que o que você digitou.

— E no final, o programa ainda pergunta se você quer jogar novamente ou encerrar.

Leo abriu um leve sorriso.

— Até que parece legal…

— Parece, e é. Mas o mais importante aqui não é só o jogo — continuou Zaion. — É a estrutura.

— Primeiro, vamos fazer a versão mais simples: tudo dentro da `main`, do jeito que vínhamos fazendo até agora.

— Depois, vamos reorganizar o programa em funções.

— Assim, além de funcionar, ele fica mais bonito, mais fácil de entender e muito mais reaproveitável.

Zaion sorriu para o irmão, puxou o teclado para mais perto e concluiu:

— Então vamos começar pela versão direta.

— Depois, a gente transforma tudo em partes menores, e o programa começa a ficar com cara de projeto de verdade.

---

📝 Passos a seguir
1. Preparar o ambiente

◦ Incluir bibliotecas necessárias:

	▪ <iostream> para entrada e saída.
	▪ <cstdlib> e <ctime> para gerar números aleatórios.
	▪ <cctype> para trabalhar com maiúsculas/minúsculas na resposta final.

2. Inicializar o sorteio

	Usar std::srand(std::time(NULL)) para gerar números aleatórios diferentes a cada execução.

3. Iniciar o jogo em loop

	Estrutura while (true) para permitir jogar várias vezes até o usuário encerrar.

4. Sortear o número secreto
	Gerar número entre 1 e 100:
		
		int numero_secreto = 1 + (std::rand() % 100);

5. Definir o número de tentativas

	Exemplo:
	
		int tentativas_max = 5;

6. Receber palpites do jogador

	. Laço for para até 5 tentativas.

	. Ler o valor digitado com `std::cin`.

	. Se o palpite não for válido (não for número), limpar entrada e pedir de novo.

7. Comparar palpite com número secreto

	. Se for igual → jogador acertou, encerrar rodada.

	. Se for menor → mostrar mensagem: "O número sorteado é MAIOR".

	. Se for maior → mostrar mensagem: "O número sorteado é MENOR".

8. Informar tentativas restantes

	. A cada erro, exibir quantas tentativas ainda faltam.

9. Encerrar rodada

	. Se acertou → mostrar parabéns.

	. Se errou todas as tentativas → mostrar o número secreto.

10. Perguntar se deseja jogar novamente

	. Perguntar: "Deseja jogar novamente? (S/N)".

	. Se digitar "S" → reinicia o jogo.

	. Se digitar "N" → encerrar programa.

---
## Veja a o programa:

```
#include <iostream>
#include <cstdlib>
#include <ctime>
#include <cctype>

using std::cout;
using std::cin;
using std::endl;

/*
Programa: Jogo de adivinhação
Objetivo: Sortear um número de 1 a 100 e dar ao jogador 5 tentativas
Autores: Zaion e Leo
*/

int main() {
    srand(time(NULL));

    char opcao = 'S';

    cout << "=== Jogo de Adivinhacao (1 a 100) ===" << endl << endl;

    while (opcao == 'S') {
        int numeroSecreto = 1 + (rand() % 100);
        int tentativasMax = 5;
        bool acertou = false;

        cout << "Um numero entre 1 e 100 foi sorteado." << endl;
        cout << "Voce tem " << tentativasMax << " tentativas para acertar." << endl << endl;

        for (int tentativa = 1; tentativa <= tentativasMax; tentativa++) {
            int palpite;

            cout << "Tentativa " << tentativa << " de " << tentativasMax
                 << ". Digite seu palpite: ";

            if (!(cin >> palpite)) {
                cin.clear();
                cin.ignore(10000, '\n');
                cout << "Entrada invalida. Digite um numero inteiro." << endl;
                tentativa--;
                continue;
            }

            if (palpite == numeroSecreto) {
                cout << "Acertou! O numero era " << numeroSecreto << "." << endl;
                acertou = true;
                break;
            } else if (palpite < numeroSecreto) {
                cout << "Errou. Dica: o numero sorteado e MAIOR que " << palpite << "." << endl;
            } else {
                cout << "Errou. Dica: o numero sorteado e MENOR que " << palpite << "." << endl;
            }
        }

        if (!acertou) {
            cout << endl
                 << "Suas tentativas acabaram. O numero era "
                 << numeroSecreto << "." << endl;
        }

        cout << endl << "Deseja jogar novamente? (S/N): ";
        cin >> opcao;

        opcao = toupper(opcao);

        if (opcao != 'S') {
            cout << endl << "Encerrando. Obrigado por jogar!" << endl;
        }

        cout << endl << "-----------------------------" << endl << endl;
    }

    return 0;
}
```

---

# 🎞️ O número secreto


— Zaion… pode me explicar o que é isso?

Leo aponta para o código:

```cpp
int numeroSecreto = 1 + (rand() % 100);
````

---

Zaion sorri.

— Boa pergunta.

— Essa linha é onde o jogo “pensa” no número secreto.

---

## 🧠 Parte 1 — rand()

— Primeiro isso aqui:

👉 rand()

— Ele gera um número aleatório.

---

— Tipo qualquer número?

— Sim… mas dentro de um intervalo grande.

— Algo como:

```text
1804289383
846930886
1681692777
```

---

Leo arregala os olhos.

— Tudo isso?!

— Pois é.

— Por isso precisamos “controlar” esse número.

---

## 🧠 Parte 2 — operador %

Zaion aponta:

```cpp
rand() % 100
```

— Esse símbolo `%` significa:

👉 resto da divisão

---

— Como assim?

— Exemplo:

```text
7 % 3 = 1
```

— Porque:

👉 7 ÷ 3 = 2 e sobra 1

---

— Então…

```cpp
rand() % 100
```

— vai gerar números de:

👉 0 até 99

---

## 🧠 Parte 3 — o +1

— E agora vem isso:

```cpp
1 + (rand() % 100)
```

— Isso serve para ajustar o intervalo.

---

— Como assim?

— Antes tínhamos:

👉 0 até 99

— Agora fica:

👉 1 até 100

---

## 🎯 Resumo

```cpp
int numeroSecreto = 1 + (rand() % 100);
```

👉 gera um número aleatório
👉 entre 1 e 100

---

Leo cruza os braços.

Pensando.

---

— Então…

— rand gera qualquer número…

— o % limita…

— e o +1 ajusta o começo?

---

Zaion sorri.

— Exatamente.

---

— Agora o jogo começa a fazer sentido.

— Não é mágica…

— é lógica.

---

# 🎞️ O segredo do “aleatório”

— E isso aqui…

Leo aponta:

```cpp
srand(time(NULL));
````

— Tem alguma coisa a ver com o `rand()`?

---

Zaion sorri.

— Tem tudo a ver.

---

## 🧠 Parte 1 — o problema escondido

— Leo… olha isso.

```cpp
cout << rand() << endl;
cout << rand() << endl;
cout << rand() << endl;
```

---

— Se você rodar o programa duas vezes…

— ele gera os MESMOS números.

---

Leo franze a testa.

— Ué… mas não era aleatório?

---

— Parece.

— Mas não é de verdade.

---

## 🧠 Parte 2 — o que está acontecendo

— O `rand()` não é realmente aleatório.

👉 Ele segue uma sequência.

---

— Tipo uma lista?

— Exatamente.

---

— E ele sempre começa do mesmo ponto.

---

## 🧠 Parte 3 — entra o srand

Zaion escreve:

```cpp
srand(time(NULL));
```

---

— O `srand` serve para:

👉 mudar o ponto de início da sequência

---

— É como embaralhar antes de usar.

---

## 🧠 Parte 4 — o time(NULL)

— Agora isso aqui:

```cpp
time(NULL)
```

---

— Ele pega o tempo atual do sistema.

👉 em segundos

---

— Então cada vez que o programa roda…

👉 o número inicial muda

---

## 🎯 Resultado

```cpp 
srand(time(NULL));
rand();
```

👉 agora sim parece aleatório

---

## 🎬 Analogia

— Imagine um baralho.

👉 `rand()` → tirar cartas
👉 `srand()` → embaralhar antes

---

Leo sorri.

— Então antes eu estava jogando…

— com o baralho sempre na mesma ordem?

---

— Exatamente.

---

— Agora sim ficou justo.

---

Zaion completa:

— Em programação…

— até o “aleatório” tem lógica.

---

# 💡 Resumo didático (curto)

👉 `rand()` → gera números  
👉 `srand()` → define o início da sequência  
👉 `time(NULL)` → usa o tempo atual  

👉 juntos → parecem aleatórios  

---










