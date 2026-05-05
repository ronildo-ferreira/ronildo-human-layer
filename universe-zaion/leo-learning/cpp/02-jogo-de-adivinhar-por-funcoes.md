# Mesmo jogo, separado por funções

— Leo, esta a versão 1 do nosso jogo, com tudo dentro da `main`.

— Ela funciona, mas tem um problema: fica difícil reaproveitar o código, complica a manutenção e atrapalha a leitura.

— Então a gente até consegue usar partes em outros programas… mas só copiando e colando? — perguntou Leo.

— Exatamente. E copiar e colar não é uma boa solução. O ideal é separar o programa em partes menores, cada uma com uma responsabilidade clara.

— E isso é o que você chama de funções?

— Isso mesmo. Na versão 2, a gente vai dividir o jogo em funções:
- `sortearNumero()`
- `lerPalpite()`
- `avaliarPalpite()`
- `querContinuar()`
- `jogarRodada()`

— E por que isso é melhor?

— Porque cada função faz uma tarefa específica. Aí fica mais fácil testar, corrigir, reaproveitar e entender o programa.

— Ah… então modularizar é como montar com blocos de LEGO.

— Perfeito — respondeu Zaion. — Agora vamos ver cada função separadamente e entender o que cada uma faz.

---

## 1) `sortearNumero()`

— Essa é a primeira função:

```cpp
#include <cstdlib>

int sortearNumero() {
    return 1 + (rand() % 100);
}
````

— O que ela faz? — perguntou Leo.

— Ela sorteia e devolve um número inteiro de 1 a 100.

— Então ela não mostra nada na tela?

— Não. Ela só faz o sorteio e entrega o resultado.

— E por que isso é bom?

— Porque assim a lógica do sorteio fica isolada. Se amanhã eu quiser mudar de 1 a 100 para 1 a 50, altero só aqui.

— Entendi. Ela é pequena, mas resolve uma tarefa inteira.

— Exatamente.

---

## 2) `lerPalpite()`

— Agora veja esta:

```cpp
#include <iostream>

using std::cout;
using std::cin;

int lerPalpite(int tentativaAtual, int tentativasMax) {
    int palpite;

    while (true) {
        cout << "Tentativa " << tentativaAtual
             << " de " << tentativasMax
             << ". Digite seu palpite: ";

        if (cin >> palpite) {
            return palpite;
        }

        cin.clear();
        cin.ignore(10000, '\n');
        cout << "Entrada invalida. Digite um numero inteiro.\n";
    }
}
```

— Zaion, eu não entendi isso aqui:

```cpp
int lerPalpite(int tentativaAtual, int tentativasMax)
```

— O que são essas coisas dentro dos parênteses? — perguntou Leo, franzindo a testa.

— Boa observação. Esses são os **parâmetros** da função.

— Parâmetros?

— Sim. Eles são como variáveis que recebem valores quando a função é chamada.

— Então `tentativaAtual` e `tentativasMax` são variáveis?

— Exatamente. Só que elas existem dentro dessa função.

— Então se eu chamar:

```cpp
lerPalpite(2, 5);
```

— o `tentativaAtual` vale 2 e `tentativasMax` vale 5?

— Isso mesmo.

— Ah… então eu consigo mandar informações de fora da função para dentro dela!

— Perfeito. E é assim que essa função consegue mostrar:
“tentativa 2 de 5”, “tentativa 3 de 5” e assim por diante.

— E o que essa função faz, no fim das contas?

— Ela lê o palpite do jogador com segurança.

— Segurança?

— Sim. Se a pessoa digitar algo inválido, como uma letra no lugar de um número, o programa não quebra. Ele limpa a entrada errada e pede novamente.

— Então essa função não serve só para ler. Ela também valida.

— Exatamente. Por isso vale a pena separar.

---

## 3) `avaliarPalpite()`

— Agora esta aqui:

```cpp
#include <iostream>

using std::cout;

bool avaliarPalpite(int palpite, int segredo) {
    if (palpite == segredo) {
        cout << "Acertou! O numero era " << segredo << ".\n";
        return true;
    } else if (palpite < segredo) {
        cout << "Errou. Dica: o numero sorteado eh MAIOR que " << palpite << ".\n";
    } else {
        cout << "Errou. Dica: o numero sorteado eh MENOR que " << palpite << ".\n";
    }

    return false;
}
```

— O que significa esse `bool`? — perguntou Leo.

— `bool` é um tipo de dado lógico. Ele só pode guardar dois valores:

* `true` → verdadeiro
* `false` → falso

— Então essa função devolve verdadeiro ou falso?

— Isso. Se o palpite estiver certo, ela mostra a mensagem e devolve `true`. Se estiver errado, dá a dica e devolve `false`.

— E por que isso é útil?

— Porque assim o restante do programa só precisa perguntar:
“acertou ou não acertou?”

— Entendi… então ela cuida da comparação, e o resto do código só reage ao resultado.

— Exatamente.

---

## 4) `querContinuar()`

— Agora esta função:

```cpp
#include <iostream>
#include <cctype>

using std::cout;
using std::cin;

bool querContinuar() {
    char opcao;

    cout << "\nDeseja jogar novamente? (S/N): ";
    cin >> opcao;

    opcao = toupper(opcao);

    return (opcao == 'S');
}
```

— Essa parece mais simples… — comentou Leo.

— E é. Ela só pergunta se o jogador quer continuar.

— E por que usar função para algo tão pequeno?

— Porque mesmo coisas pequenas merecem organização. Além disso, se um dia eu quiser trocar essa pergunta por um menu, altero só aqui.

— E o que faz esse `toupper(opcao)`?

— Ele converte a letra para maiúscula.

— Ah… então se o jogador digitar `s` minúsculo, o programa trata como `S`?

— Exatamente.

— Legal. Isso evita erro bobo.

---

## 5) `jogarRodada()`

— Agora vem a função que junta as outras:

```cpp
#include <iostream>

using std::cout;

void jogarRodada(int tentativasMax = 5) {
    int numeroSecreto = sortearNumero();
    bool acertou = false;

    cout << "Um numero entre 1 e 100 foi sorteado.\n";
    cout << "Voce tem " << tentativasMax << " tentativas.\n\n";

    for (int tentativa = 1; tentativa <= tentativasMax; tentativa++) {
        int palpite = lerPalpite(tentativa, tentativasMax);

        if (avaliarPalpite(palpite, numeroSecreto)) {
            acertou = true;
            break;
        }

        int restantes = tentativasMax - tentativa;

        if (restantes > 0) {
            cout << "Voce ainda tem " << restantes << " tentativa(s).\n\n";
        }
    }

    if (!acertou) {
        cout << "\nSuas tentativas acabaram. O numero era " << numeroSecreto << ".\n";
    }
}
```

— Essa parece maior…

— Sim. Porque ela organiza o fluxo de uma rodada completa.

— Então ela não faz tudo sozinha?

— Não. Esse é justamente o ponto.

— Ela usa:

* `sortearNumero()`
* `lerPalpite()`
* `avaliarPalpite()`

— Ou seja, ela coordena as outras.

— Ah… então essa função é como se fosse a “gerente” da rodada.

— Excelente analogia — respondeu Zaion. — Ela não resolve tudo diretamente, mas chama quem resolve cada parte.

— E esse `void`?

— Significa que essa função **não devolve valor**. Ela apenas executa ações.

— Então:

* `int` devolve número
* `bool` devolve verdadeiro ou falso
* `void` não devolve nada?

— Isso mesmo.

---

## 6) Programa completo

— Agora que vimos cada função separadamente, vamos juntar tudo em um único programa.

```cpp
#include <iostream>
#include <cstdlib>
#include <ctime>
#include <cctype>

using std::cout;
using std::cin;

// ---------- Assinaturas ----------
int  sortearNumero();
int  lerPalpite(int tentativaAtual, int tentativasMax);
bool avaliarPalpite(int palpite, int segredo);
bool querContinuar();
void jogarRodada(int tentativasMax = 5);

int main() {
    srand(time(NULL));

    cout << "=== Jogo de Adivinhacao (1 a 100) — Versao por Funcoes ===\n\n";

    while (true) {
        jogarRodada(5);

        if (!querContinuar()) {
            cout << "\nEncerrando. Obrigado por jogar!\n";
            break;
        }

        cout << "\n-----------------------------\n\n";
    }

    return 0;
}

// ---------- Implementações ----------
int sortearNumero() {
    return 1 + (rand() % 100);
}

int lerPalpite(int tentativaAtual, int tentativasMax) {
    int palpite;

    while (true) {
        cout << "Tentativa " << tentativaAtual
             << " de " << tentativasMax
             << ". Digite seu palpite: ";

        if (cin >> palpite) {
            return palpite;
        }

        cin.clear();
        cin.ignore(10000, '\n');
        cout << "Entrada invalida. Digite um numero inteiro.\n";
    }
}

bool avaliarPalpite(int palpite, int segredo) {
    if (palpite == segredo) {
        cout << "Acertou! O numero era " << segredo << ".\n";
        return true;
    } else if (palpite < segredo) {
        cout << "Errou. Dica: o numero sorteado eh MAIOR que " << palpite << ".\n";
    } else {
        cout << "Errou. Dica: o numero sorteado eh MENOR que " << palpite << ".\n";
    }

    return false;
}

bool querContinuar() {
    char opcao;

    cout << "\nDeseja jogar novamente? (S/N): ";
    cin >> opcao;

    opcao = toupper(opcao);

    return (opcao == 'S');
}

void jogarRodada(int tentativasMax) {
    int numeroSecreto = sortearNumero();
    bool acertou = false;

    cout << "Um numero entre 1 e 100 foi sorteado.\n";
    cout << "Voce tem " << tentativasMax << " tentativas.\n\n";

    for (int tentativa = 1; tentativa <= tentativasMax; tentativa++) {
        int palpite = lerPalpite(tentativa, tentativasMax);

        if (avaliarPalpite(palpite, numeroSecreto)) {
            acertou = true;
            break;
        }

        int restantes = tentativasMax - tentativa;

        if (restantes > 0) {
            cout << "Voce ainda tem " << restantes << " tentativa(s).\n\n";
        }
    }

    if (!acertou) {
        cout << "\nSuas tentativas acabaram. O numero era " << numeroSecreto << ".\n";
    }
}
```

---

## 7) Fechamento da explicação

— Agora eu entendi melhor… — disse Leo, olhando para o código.

— O programa ficou maior…

— Mas ao mesmo tempo ficou mais organizado.

— Exatamente — respondeu Zaion. — O objetivo não é só fazer funcionar. É fazer funcionar de um jeito que você consiga entender, manter e reaproveitar.

— Então programar bem não é só escrever menos…

— É escrever melhor.

— Isso mesmo.

— E quando a gente separa em funções…

— o programa começa a parecer um projeto de verdade.

Leo sorriu.

— Agora fez sentido. A `main` não precisa carregar o mundo inteiro nas costas.

Zaion riu.

— Perfeito. Essa foi uma boa definição.

— Mas me diga uma coisa!

— Que diabos é isso aqui?

Leo aponta para o código:

```cpp
// ---------- Assinaturas ----------
int  sortearNumero();
int  lerPalpite(int tentativaAtual, int tentativasMax);
bool avaliarPalpite(int palpite, int segredo);
bool querContinuar();
void jogarRodada(int tentativasMax = 5);
````

---

Zaion sorri.

— Boa…

— Isso se chama **assinatura de função**.

---

— Assinatura?

— Sim.

— É como um “resumo” da função.

---

## 🧠 O que isso significa?

— Aqui a gente está dizendo para o compilador:

👉 “Olha… essas funções existem”

👉 “Você vai encontrá-las mais abaixo”

---

— Mas… por que isso é necessário? — perguntou Leo.

---

## 🧠 O problema sem assinatura

— Imagine isso:

```cpp
int main() {
    jogarRodada();
}
```

— Se o compilador ainda não viu a função `jogarRodada`…

👉 ele não sabe que ela existe

👉 e dá erro

---

— Então essas assinaturas avisam antes?

— Exatamente.

---

## 🎯 Analogia

— Pense assim:

👉 assinatura = índice de um livro

— você sabe que o conteúdo existe…

— mesmo sem ter lido ainda

---

## 🔍 Vamos analisar uma linha

```cpp
int lerPalpite(int tentativaAtual, int tentativasMax);
```

— Isso quer dizer:

👉 a função se chama `lerPalpite`
👉 recebe dois números inteiros
👉 e retorna um número inteiro

---

— Mas… cadê o código dela?

— Está mais abaixo.

— Aqui só estamos “anunciando”.

---

## 🧠 Outro exemplo

```cpp
bool querContinuar();
```

— Essa função:

👉 não recebe nada
👉 retorna verdadeiro ou falso

---

## 🧠 E esse aqui?

```cpp
void jogarRodada(int tentativasMax = 5);
```

— Esse é interessante…

👉 `void` → não retorna nada
👉 recebe um número
👉 e tem um valor padrão: 5

---

— Valor padrão?

— Se você chamar:

```cpp
jogarRodada();
```

— ele assume automaticamente:

👉 5 tentativas

---

— Ahhh…

— então essas linhas são tipo…

— um contrato?

---

Zaion sorri.

— Perfeito.

— Você acabou de definir muito bem.

---

## 🎯 Resumo

👉 assinatura = nome + parâmetros + retorno
👉 não tem código
👉 só informa que a função existe

---

Leo cruza os braços.

---

— Então…

— primeiro eu aviso que a função existe…

— depois eu escrevo ela de verdade?

---

— Exatamente.

---

— Programar é muito mais organizado do que eu imaginava…

— comentou Leo.

---

Zaion responde, tranquilo:

— E você só viu o começo.

