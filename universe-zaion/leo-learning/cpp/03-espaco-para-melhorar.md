# Ainda tem espaço para melhorar

— Zaion, o programa de adivinhar números ficou legal!

Leo falou isso com um certo orgulho, mas logo voltou a ficar pensativo.

— Só mais uma coisa… a Alin me disse que eu deveria usar variáveis indexadas, porque elas ajudam a organizar melhor o programa. O que é isso? E como eu uso?

Zaion sorriu, animado com a curiosidade do irmão.

— Ótima pergunta, Leo. Variáveis indexadas são o que chamamos de **vetores** em C++.

— Vetores? — repetiu Leo.

— Isso mesmo. Pensa em uma caixa com vários compartimentos, todos organizados em sequência. Em vez de criar várias variáveis separadas, como `nota1`, `nota2`, `nota3`… a gente cria um vetor. Assim, cada posição guarda um valor.

Leo arregalou os olhos.

— Então é tipo uma lista organizada?

— Exatamente. Olha este exemplo:

```cpp
#include <iostream>

using std::cout;
using std::endl;

int main() {
    int numeros[5] = {10, 20, 30, 40, 50};

    cout << "Primeiro elemento: " << numeros[0] << endl;
    cout << "Terceiro elemento: " << numeros[2] << endl;

    char vogais[5] = {'a', 'e', 'i', 'o', 'u'};

    cout << "Vogal na posicao 4: " << vogais[3] << endl;

    return 0;
}
````

— Repara que usamos colchetes `[]` para acessar uma posição do vetor — explicou Zaion, apontando para a tela.

— E a contagem começa do zero, né?

— Isso mesmo.

Leo pensou por alguns segundos.

— Então `numeros[0]` vale 10, `numeros[1]` vale 20… e assim por diante.

— Perfeito. E com `char`, a gente pode guardar letras.

— Então vetor não é um tipo… é uma forma de organizar vários valores do mesmo tipo?

Zaion sorriu.

— Exatamente. Essa foi uma ótima definição.

— E para que isso ajuda na prática?

— Ajuda muito quando você tem vários dados parecidos e quer usar repetição. Em vez de escrever muitas variáveis separadas, você organiza tudo em um vetor e percorre com um laço.

Leo assentiu devagar.

— Agora eu entendi o que a Alin quis dizer com variáveis indexadas.

— Ótimo. Então vou te deixar um desafio.

— Qual?

— Criar o jogo da forca.

— Sério?

— Sim. E quero que você use vetores para armazenar as palavras do jogo.

Leo ficou animado, mas logo franziu a testa.

— Tá… mas aí entra aquele problema de texto, né?

— Exatamente — respondeu Zaion. — Se você usar arranjos de `char`, entra no mundo das **C-strings**. E aí existem algumas regras específicas.

— Tipo o quê?

— Por exemplo: se você já criou um array de `char`, não pode simplesmente fazer isso:

```cpp
palavra[0] = "Zaion";
```

— E por que não?

— Porque, nesse caso, `palavra[0]` não é uma string inteira. Para copiar texto dentro de um arranjo de `char`, você precisa usar uma função própria.

— Tipo qual?

— `strcpy`.

— E para comparar uma resposta, como `"sim"`?

— Aí você usa `strcmp`.

— E para contar quantos caracteres tem uma palavra?

— `strlen`.

Leo respirou fundo.

— Então agora ficou mais sério…

— Ficou mais interessante — corrigiu Zaion, com um sorriso leve.

— Mas calma. O mais importante de hoje era entender o vetor. Essas funções extras você pode consultar como apoio enquanto monta o jogo.

— Ah… então eu não preciso decorar tudo agora?

— Não. Primeiro entende a ideia. Depois pratica.

— Isso ajuda.

— E ajuda mesmo. Vou te deixar um guia rápido.

---

## 🧰 Guia rápido: `strcpy`, `strcmp` e `strlen`

Inclua o cabeçalho abaixo para usar essas funções em C++:

```cpp
#include <cstring>
```

### 1) `strcpy(destino, origem)`

**O que faz:** copia a string da origem para o destino.

```cpp
#include <cstring>

char palavras[5][32];

std::strcpy(palavras[0], "zaion");
std::strcpy(palavras[1], "androides");
```

### 2) `strcmp(a, b)`

**O que faz:** compara duas C-strings.

```cpp
char resp[8];

if (std::strcmp(resp, "sim") == 0) {
    // as strings são iguais
}
```

### 3) `strlen(s)`

**O que faz:** devolve o tamanho da string.

```cpp
size_t tamanho = std::strlen(palavras[0]);
```

---

## 🧪 Exemplo mínimo

```cpp
#include <iostream>
#include <cstring>

using std::cout;
using std::cin;
using std::endl;

int main() {
    char palavras[5][32];

    std::strcpy(palavras[0], "zaion");
    std::strcpy(palavras[1], "androides");
    std::strcpy(palavras[2], "laboratorio");
    std::strcpy(palavras[3], "minhoca");
    std::strcpy(palavras[4], "zeta");

    char resp[8];

    cout << "Quer jogar? (sim/nao): ";
    cin >> resp;

    if (std::strcmp(resp, "sim") == 0) {
        cout << "Otimo! Tamanho da primeira palavra: "
             << std::strlen(palavras[0]) << endl;
    } else {
        cout << "Tudo bem. Ate a proxima!" << endl;
    }

    return 0;
}
```

---

## ✅ Dicas para o jogo da forca

* Use um vetor para armazenar o banco de palavras
* Escolha uma palavra secreta
* Crie outro vetor para mostrar o progresso do jogador
* Leia uma letra por vez
* Percorra a palavra e revele as letras corretas
* Termine quando não houver mais `_` ou quando acabarem as tentativas

---

— Tenho certeza de que você vai dar o seu melhor, Leo.

— Boa noite, mano. Muito obrigado por me ajudar.

Leo abraçou o irmão com força.

