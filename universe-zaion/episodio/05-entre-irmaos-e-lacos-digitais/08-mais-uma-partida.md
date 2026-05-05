# Mais uma partida

Zaion rompe o silêncio.

— Pode me explicar como o programa funciona?

Leo sorri, animado.

— Zaion, eu fiz o jogo da Torre de Hanói em C++ usando vetores e funções, como foi pedido.

---

## 1. Ideia do jogo

— O jogo tem três torres: **A**, **B** e **C**.

— No começo, todos os discos ficam na torre **A**, do maior embaixo para o menor em cima.

— O jogador escolhe:
- a torre de **origem**
- a torre de **destino**

— O programa verifica:
- se a torre existe
- se a origem não está vazia
- se o movimento é permitido

— A regra principal é:

**Nunca colocar um disco maior sobre um menor.**

---

## 2. Representação das torres

— Cada torre é um vetor de inteiros:

```cpp
vector<int> A, B, C;
````

— Cada número representa um disco:

* 1 → menor
* 2 → médio
* 3 → maior

— Exemplo com 3 discos:

```cpp
A = {3, 2, 1};
```

— O topo da torre é o último elemento:

* `back()` → pega o topo
* `pop_back()` → remove
* `push_back()` → adiciona

---

## 3. Inicialização

— Primeiro peço a quantidade de discos:

```cpp
cin >> n;
```

— Depois preencho a torre A:

```cpp
for (int i = n; i >= 1; i--) {
    A.push_back(i);
}
```

---

## 4. Funções principais

— Separei o programa em funções:

* desenhar disco
* mostrar torres
* escolher torre
* validar movimento
* mover disco
* verificar vitória

— Isso deixa o código mais organizado.

---

## 5. Validação e lógica

— Antes de mover, o programa verifica:

* origem vazia → inválido
* destino vazio → válido
* disco menor sobre maior → válido

---

## 6. Vitória

— O jogo termina quando todos os discos vão para B ou C.

---

## 7. Movimentos

— A cada jogada válida:

```cpp
movimentos++;
```

— No final, comparo com o mínimo:

```cpp
(1 << n) - 1
```

---

## 🧠 Resumo do Leo

— Resumindo, Zaion:

* usei **vetores** para representar as torres
* usei **funções** para dividir o problema
* usei validações para manter as regras

— Assim o programa ficou mais organizado e fácil de entender.

---

Zaion permanece em silêncio.

Observando.

Atentamente.

---

Orgulho.

Mas também…

dúvida.

---

> Uma semana atrás…
>
> ele não sabia nada.

---

> Foi rápido demais.

---

Sem perceber…

a porta estava aberta.

---

Darian estava ali.

Parado.

Com o controle na mão.

Observando.

Em silêncio.

---

Ninguém tinha notado sua presença.

---

Zaion aponta para a tela.

— Essa linha… para que ela serve?

---

## 🧠 Linha do código

```cpp
vector<int> A, B, C;
```

---

— Mano… essa é uma das partes mais importantes do programa — respondeu Leo.

---

## 📦 O que é vector

— O `vector` é um tipo que funciona como um array dinâmico.

— Ele:

* guarda vários valores
* cresce automaticamente
* é mais flexível que array comum

— O `<int>` indica que ele guarda números inteiros.

---

## 🗼 As torres

— Aqui eu criei três vetores:

```cpp
vector<int> A, B, C;
```

— Cada um representa uma torre:

* A → inicial
* B → auxiliar
* C → destino

---

## 🎯 Representação dos discos

— Cada número é um disco:

```cpp
A = {3, 2, 1};
```

---

## ⬆️ Topo da torre

— O topo é o último elemento:

```cpp
A.back();
```

---

## 🔄 Movimentação

— Para mover:

```cpp
origem.pop_back();
destino.push_back(disco);
```

---

## 📊 Exemplo

Antes:

```cpp
A = {3, 2, 1}
C = {}
```

Depois:

```cpp
A = {3, 2}
C = {1}
```

---

Enquanto Leo explicava…

Zaion observava.

Impressionado.

---

E Darian…

sentia outra coisa.

---

Silêncio.

Deslocamento.

---

> Ninguém me vê.

---

— Zaion… vamos jogar uma partida? — perguntou Ryo.

---

Zaion se vira.

— Oi, Ryo! Entra. Olha o que o Leo fez.

---

Ryo se aproxima.

Observa.

Finge interesse.

---

— É… ficou legal.

Pausa.

---

— Então… você joga comigo?

A voz baixa.

Quase esperando um “não”.

---

Zaion responde sem hesitar:

— Claro.

---

— Mas tem uma condição…

---

— Qual? — perguntou Ryo, tenso.

---

— Se eu ganhar… você me dá seu lanche amanhã.

---

— Tá… mas e se eu ganhar?

---

— Eu compro aquele jogo que você comentou.

---

Silêncio.

---

O rosto do Ryo muda.

---

— Fechado.

---

Um sorriso leve.

Quase inesperado.

---

— Já pode ir preparando o dinheiro… isso já está no papo.

— Vamos logo, bro!

---

Zaion trava por um instante.

---

“Bro”?

|[` < voltar `](07-duvida-de-zaion.md)| [` avançar > `](../06-vida-corrida/01-pedido-do-zaion.md)|
|--------|-----|
