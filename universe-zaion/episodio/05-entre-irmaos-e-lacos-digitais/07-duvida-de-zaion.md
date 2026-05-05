# A duvida de Zaion

(No quarto do Leo)

— Mano… tirei 10 na prova!

— E fui um dos cinco a tirar 10!

Leo falava rápido, quase sem respirar, com um sorriso que não cabia no rosto.

---

Zaion olhou para ele.

Por um instante…

não disse nada.

---

— Parabéns, Leo… — respondeu, com um sorriso leve.

— Estou orgulhoso de você.

---

Leo respirou fundo, ainda animado.

— Eu fiz o desafio que você pediu…

— Na verdade… eu queria te mostrar o jogo que eu fiz.

— Foi o professor que deu como desafio.

---

Zaion cruzou os braços, curioso.

— Que jogo?

---

— A Torre de Hanói!

— Você já ouviu falar?

---

Zaion ficou em silêncio.

Por um segundo a mais do que o normal.

---

Algo ali…

era familiar.

---

— Sim… já ouvi.

---

— Então… eu fiz do jeito que você ensinou.

— Mas dei uma melhorada…

---

Leo abriu o notebook, empurrando na direção do irmão.

Os olhos brilhando.

Esperando aprovação.

---

Zaion se aproximou.

Observando a tela.

Com atenção.

Mais do que o Leo imaginava.

---

# Programa em C++

```cpp
#include <iostream>
#include <vector>
#include <iomanip>
#include <cctype>

using namespace std;

// --------------------------------------------------
// Função para desenhar um disco centralizado
// --------------------------------------------------
string desenharDisco(int tamanho, int maxDiscos) {
    int larguraTotal = maxDiscos * 2 + 1;

    if (tamanho == 0) {
        string s(larguraTotal, ' ');
        s[larguraTotal / 2] = '|';
        return s;
    }

    int larguraDisco = tamanho * 2 - 1;
    int espacos = (larguraTotal - larguraDisco) / 2;

    string s(espacos, ' ');
    s += string(larguraDisco, char('0' + tamanho));
    s += string(espacos, ' ');

    return s;
}

// --------------------------------------------------
// Função para mostrar as torres na tela
// --------------------------------------------------
void mostrarTorres(const vector<int>& A, const vector<int>& B, const vector<int>& C, int n) {
    cout << "\n================ TORRE DE HANOI ================\n\n";

    for (int nivel = n - 1; nivel >= 0; nivel--) {
        int discoA = (nivel < (int)A.size()) ? A[nivel] : 0;
        int discoB = (nivel < (int)B.size()) ? B[nivel] : 0;
        int discoC = (nivel < (int)C.size()) ? C[nivel] : 0;

        cout << desenharDisco(discoA, n) << "   "
             << desenharDisco(discoB, n) << "   "
             << desenharDisco(discoC, n) << "\n";
    }

    int larguraTotal = n * 2 + 1;
    cout << string(larguraTotal, '-') << "   "
         << string(larguraTotal, '-') << "   "
         << string(larguraTotal, '-') << "\n";

    cout << setw(larguraTotal / 2 + 1) << "A"
         << string(3 + larguraTotal - (larguraTotal / 2 + 1), ' ')
         << setw(larguraTotal / 2 + 1) << "B"
         << string(3 + larguraTotal - (larguraTotal / 2 + 1), ' ')
         << setw(larguraTotal / 2 + 1) << "C" << "\n\n";
}

// --------------------------------------------------
// Função para obter a referência da torre correta
// --------------------------------------------------
vector<int>& escolherTorre(vector<int>& A, vector<int>& B, vector<int>& C, char torre) {
    if (torre == 'A') return A;
    if (torre == 'B') return B;
    return C;
}

// --------------------------------------------------
// Verifica se o movimento é válido
// --------------------------------------------------
bool movimentoValido(const vector<int>& origem, const vector<int>& destino) {
    if (origem.empty()) return false;
    if (destino.empty()) return true;
    return origem.back() < destino.back();
}

// --------------------------------------------------
// Move um disco de uma torre para outra
// --------------------------------------------------
bool moverDisco(vector<int>& origem, vector<int>& destino) {
    if (!movimentoValido(origem, destino)) {
        return false;
    }

    int disco = origem.back();
    origem.pop_back();
    destino.push_back(disco);
    return true;
}

// --------------------------------------------------
// Verifica se o jogo terminou
// --------------------------------------------------
bool jogoConcluido(const vector<int>& B, const vector<int>& C, int n) {
    return ((int)B.size() == n || (int)C.size() == n);
}

// --------------------------------------------------
// Programa principal
// --------------------------------------------------
int main() {
    vector<int> A, B, C;
    int n;
    char origem, destino;
    int movimentos = 0;

    cout << "===== JOGO TORRE DE HANOI =====\n";
    cout << "Digite a quantidade de discos (3 a 10): ";
    cin >> n;

    while (n < 3 || n > 10) {
        cout << "Valor invalido. Digite um numero entre 3 e 10: ";
        cin >> n;
    }

    // Preenche a torre A com os discos do maior para o menor
    for (int i = n; i >= 1; i--) {
        A.push_back(i);
    }

    while (!jogoConcluido(B, C, n)) {
        mostrarTorres(A, B, C, n);

        cout << "Digite a torre de origem (A, B ou C): ";
        cin >> origem;
        origem = toupper(origem);

        cout << "Digite a torre de destino (A, B ou C): ";
        cin >> destino;
        destino = toupper(destino);

        if ((origem != 'A' && origem != 'B' && origem != 'C') ||
            (destino != 'A' && destino != 'B' && destino != 'C')) {
            cout << "\nTorre invalida. Use apenas A, B ou C.\n";
            continue;
        }

        if (origem == destino) {
            cout << "\nOrigem e destino nao podem ser iguais.\n";
            continue;
        }

        vector<int>& torreOrigem = escolherTorre(A, B, C, origem);
        vector<int>& torreDestino = escolherTorre(A, B, C, destino);

        if (moverDisco(torreOrigem, torreDestino)) {
            movimentos++;
            cout << "\nMovimento realizado com sucesso!\n";
        } else {
            cout << "\nMovimento invalido! Nao e permitido colocar um disco maior sobre um menor.\n";
        }
    }

    mostrarTorres(A, B, C, n);

    cout << "Parabens! Voce concluiu o jogo em " << movimentos << " movimentos.\n";
    cout << "Quantidade minima de movimentos: " << ( (1 << n) - 1 ) << "\n";

    return 0;
}
```

---

Zaion se aproximou.

Observando a tela.

Com atenção.

Mais do que o Leo imaginava.

---

O código rolava diante dos seus olhos.

Estrutura.

Funções.

Organização.

Lógica.

---

Silêncio.

---

Algo ali…

não era só um exercício.

---

Zahy observava.

Em silêncio.

---

> Esse brilho…
>
> eu já vi antes.
>
> Não no código…
>
> mas no olhar.

---

> A pressa de mostrar.
>
> O medo de não ser bom o suficiente.
>
> E, ao mesmo tempo…
>
> a esperança de ser visto.

---

> Eu era assim…

---

Por um instante…

não sabia se aquilo era memória…

ou apenas um eco.

---

Zaion permaneceu imóvel.

Por alguns segundos.

---

Em silêncio…

olhando para a tela.

---

Será que ele fez isso sozinho?

|[` < voltar `](06-no-quarto-de-ryo.md)| [` avançar > `](08-mais-uma-partida.md)|
|--------|-----|
