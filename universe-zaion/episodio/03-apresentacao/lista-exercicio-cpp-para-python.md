# Lista de Exercícios — C++ para Conversão em Python

**Autora:** Kael Elodie Whitmore

**Objetivo:** Resolver em C++ usando `if` e `while`, testar o funcionamento e converter cada programa para Python.

**Entrega:** GitHub, com histórico de commits mostrando evolução da tarefa e colaboração.

---

## Orientações de Entrega

Cada exercício deve ter:

* Arquivo em C++ funcionando.
* Arquivo equivalente em Python.
* Comentários adaptados em cada linguagem.
* Cabeçalho informativo.
* Commits progressivos no GitHub.

Sugestão de estrutura:

```text
python-conversion/
├── cpp/
│   ├── ex01_numero_positivo.cpp
│   ├── ex02_maior_numero.cpp
│   └── ...
├── python/
│   ├── ex01_numero_positivo.py
│   ├── ex02_maior_numero.py
│   └── ...
└── README.md
```

---

# Nível Iniciante

---

## Exercício 01 — Número positivo, negativo ou zero

### Enunciado

Leia um número inteiro e informe se ele é positivo, negativo ou igual a zero.

### Interpretação lógica

* Ler um número.
* Se for maior que zero, mostrar "positivo".
* Se for menor que zero, mostrar "negativo".
* Caso contrário, mostrar "zero".

```cpp
/*
    Autor: Kael Elodie Whitmore
    Data: Junho/2026
    Descrição: Lê um número inteiro e informa se ele é positivo, negativo ou zero.
*/

#include <iostream>
using namespace std;

int main()
{
    int numero;

    cout << "Digite um numero inteiro: ";
    cin >> numero;

    if (numero > 0)
    {
        cout << "O numero e positivo." << endl;
    }
    else if (numero < 0)
    {
        cout << "O numero e negativo." << endl;
    }
    else
    {
        cout << "O numero e zero." << endl;
    }

    return 0;
}
```

---

## Exercício 02 — Maior entre dois números

### Enunciado

Leia dois números inteiros e informe qual deles é o maior. Caso sejam iguais, informe que os valores são iguais.

### Interpretação lógica

* Ler dois números.
* Comparar o primeiro com o segundo.
* Exibir o maior ou informar igualdade.

```cpp
/*
    Autor: Kael Elodie Whitmore
    Data: Junho/2026
    Descrição: Lê dois números inteiros e informa qual é o maior ou se são iguais.
*/

#include <iostream>
using namespace std;

int main()
{
    int numero1, numero2;

    cout << "Digite o primeiro numero: ";
    cin >> numero1;

    cout << "Digite o segundo numero: ";
    cin >> numero2;

    if (numero1 > numero2)
    {
        cout << "O maior numero e: " << numero1 << endl;
    }
    else if (numero2 > numero1)
    {
        cout << "O maior numero e: " << numero2 << endl;
    }
    else
    {
        cout << "Os numeros sao iguais." << endl;
    }

    return 0;
}
```

---

## Exercício 03 — Contagem de 1 até N

### Enunciado

Leia um número inteiro positivo e exiba todos os números de 1 até esse valor.

### Interpretação lógica

* Ler um número.
* Verificar se é positivo.
* Usar `while` para contar de 1 até o número informado.

```cpp
/*
    Autor: Kael Elodie Whitmore
    Data: Junho/2026
    Descrição: Lê um número inteiro positivo e exibe a contagem de 1 até esse número.
*/

#include <iostream>
using namespace std;

int main()
{
    int numero;
    int contador = 1;

    cout << "Digite um numero inteiro positivo: ";
    cin >> numero;

    if (numero > 0)
    {
        while (contador <= numero)
        {
            cout << contador << endl;
            contador++;
        }
    }
    else
    {
        cout << "Numero invalido. Digite um valor positivo." << endl;
    }

    return 0;
}
```

---

# Nível Médio

---

## Exercício 04 — Soma dos números pares

### Enunciado

Leia um número inteiro positivo e calcule a soma de todos os números pares de 1 até esse número.

### Interpretação lógica

* Ler um número.
* Verificar se é positivo.
* Percorrer os números usando `while`.
* Somar apenas os pares.

```cpp
/*
    Autor: Kael Elodie Whitmore
    Data: Junho/2026
    Descrição: Calcula a soma dos números pares de 1 até um número informado.
*/

#include <iostream>
using namespace std;

int main()
{
    int numero;
    int contador = 1;
    int soma = 0;

    cout << "Digite um numero inteiro positivo: ";
    cin >> numero;

    if (numero > 0)
    {
        while (contador <= numero)
        {
            if (contador % 2 == 0)
            {
                soma = soma + contador;
            }

            contador++;
        }

        cout << "Soma dos pares: " << soma << endl;
    }
    else
    {
        cout << "Numero invalido." << endl;
    }

    return 0;
}
```

---

## Exercício 05 — Tabuada com validação

### Enunciado

Leia um número inteiro de 1 a 10 e exiba sua tabuada. Caso o número esteja fora do intervalo, solicite novamente até que o valor seja válido.

### Interpretação lógica

* Ler um número.
* Enquanto o número for inválido, pedir novamente.
* Usar `while` para exibir a tabuada.

```cpp
/*
    Autor: Kael Elodie Whitmore
    Data: Junho/2026
    Descrição: Lê um número de 1 a 10 e exibe sua tabuada, validando a entrada.
*/

#include <iostream>
using namespace std;

int main()
{
    int numero;
    int contador = 1;

    cout << "Digite um numero de 1 a 10: ";
    cin >> numero;

    while (numero < 1 || numero > 10)
    {
        cout << "Valor invalido. Digite novamente: ";
        cin >> numero;
    }

    while (contador <= 10)
    {
        cout << numero << " x " << contador << " = " << numero * contador << endl;
        contador++;
    }

    return 0;
}
```

---

## Exercício 06 — Média de notas

### Enunciado

Leia várias notas de alunos. O programa deve continuar lendo notas enquanto o usuário digitar valores válidos entre 0 e 10. Quando for digitado um valor inválido, o programa deve parar e exibir a média das notas válidas.

### Interpretação lógica

* Ler notas.
* Enquanto a nota estiver entre 0 e 10, somar e contar.
* Ao final, calcular a média se houver notas válidas.

```cpp
/*
    Autor: Kael Elodie Whitmore
    Data: Junho/2026
    Descrição: Calcula a média de notas válidas entre 0 e 10 usando while.
*/

#include <iostream>
using namespace std;

int main()
{
    float nota;
    float soma = 0;
    int quantidade = 0;

    cout << "Digite uma nota entre 0 e 10: ";
    cin >> nota;

    while (nota >= 0 && nota <= 10)
    {
        soma = soma + nota;
        quantidade++;

        cout << "Digite outra nota entre 0 e 10: ";
        cin >> nota;
    }

    if (quantidade > 0)
    {
        cout << "Media das notas: " << soma / quantidade << endl;
    }
    else
    {
        cout << "Nenhuma nota valida foi digitada." << endl;
    }

    return 0;
}
```

---

## Exercício 07 — Contador de positivos, negativos e zeros

### Enunciado

Leia 10 números inteiros e informe quantos são positivos, quantos são negativos e quantos são iguais a zero.

### Interpretação lógica

* Repetir a leitura 10 vezes.
* Para cada número, verificar sua classificação.
* Somar nos contadores correspondentes.

```cpp
/*
    Autor: Kael Elodie Whitmore
    Data: Junho/2026
    Descrição: Lê 10 números e conta quantos são positivos, negativos e zeros.
*/

#include <iostream>
using namespace std;

int main()
{
    int numero;
    int contador = 1;
    int positivos = 0;
    int negativos = 0;
    int zeros = 0;

    while (contador <= 10)
    {
        cout << "Digite o " << contador << "o numero: ";
        cin >> numero;

        if (numero > 0)
        {
            positivos++;
        }
        else if (numero < 0)
        {
            negativos++;
        }
        else
        {
            zeros++;
        }

        contador++;
    }

    cout << "Positivos: " << positivos << endl;
    cout << "Negativos: " << negativos << endl;
    cout << "Zeros: " << zeros << endl;

    return 0;
}
```

---

## Exercício 08 — Número primo

### Enunciado

Leia um número inteiro positivo e informe se ele é primo.

### Interpretação lógica

* Um número primo é divisível apenas por 1 e por ele mesmo.
* Testar divisores de 1 até o número.
* Contar quantas divisões exatas existem.
* Se houver exatamente 2 divisores, o número é primo.

```cpp
/*
    Autor: Kael Elodie Whitmore
    Data: Junho/2026
    Descrição: Verifica se um número inteiro positivo é primo.
*/

#include <iostream>
using namespace std;

int main()
{
    int numero;
    int divisor = 1;
    int quantidadeDivisores = 0;

    cout << "Digite um numero inteiro positivo: ";
    cin >> numero;

    if (numero > 0)
    {
        while (divisor <= numero)
        {
            if (numero % divisor == 0)
            {
                quantidadeDivisores++;
            }

            divisor++;
        }

        if (quantidadeDivisores == 2)
        {
            cout << "O numero e primo." << endl;
        }
        else
        {
            cout << "O numero nao e primo." << endl;
        }
    }
    else
    {
        cout << "Numero invalido." << endl;
    }

    return 0;
}
```

---

## Exercício 09 — Fatorial

### Enunciado

Leia um número inteiro positivo e calcule seu fatorial.

Exemplo:

```text
5! = 5 × 4 × 3 × 2 × 1 = 120
```

### Interpretação lógica

* Ler um número.
* Verificar se é positivo ou zero.
* Multiplicar os valores de 1 até o número usando `while`.

```cpp
/*
    Autor: Kael Elodie Whitmore
    Data: Junho/2026
    Descrição: Calcula o fatorial de um número inteiro positivo.
*/

#include <iostream>
using namespace std;

int main()
{
    int numero;
    int contador = 1;
    int fatorial = 1;

    cout << "Digite um numero inteiro positivo: ";
    cin >> numero;

    if (numero >= 0)
    {
        while (contador <= numero)
        {
            fatorial = fatorial * contador;
            contador++;
        }

        cout << "Fatorial: " << fatorial << endl;
    }
    else
    {
        cout << "Numero invalido." << endl;
    }

    return 0;
}
```

---

## Exercício 10 — Sistema simples de senha

### Enunciado

Crie um programa que solicite uma senha numérica. O usuário terá até 3 tentativas para acertar a senha. A senha correta é `1234`.

### Interpretação lógica

* Definir a senha correta.
* Ler a senha do usuário.
* Enquanto a senha estiver errada e houver tentativas, pedir novamente.
* Informar se o acesso foi liberado ou bloqueado.

```cpp
/*
    Autor: Kael Elodie Whitmore
    Data: Junho/2026
    Descrição: Simula um sistema simples de senha com até 3 tentativas.
*/

#include <iostream>
using namespace std;

int main()
{
    int senha;
    int senhaCorreta = 1234;
    int tentativas = 1;
    int limiteTentativas = 3;

    cout << "Digite a senha: ";
    cin >> senha;

    while (senha != senhaCorreta && tentativas < limiteTentativas)
    {
        cout << "Senha incorreta. Tente novamente: ";
        cin >> senha;

        tentativas++;
    }

    if (senha == senhaCorreta)
    {
        cout << "Acesso liberado." << endl;
    }
    else
    {
        cout << "Acesso bloqueado." << endl;
    }

    return 0;
}
```

---

# Instruções para Conversão em Python

Para cada exercício:

1. Ler o enunciado.
2. Entender a lógica.
3. Testar o programa em C++.
4. Criar a versão em Python.
5. Adaptar comentários e cabeçalho.
6. Fazer commit no GitHub.

---

## Exemplo de cabeçalho em Python

```python
"""
Autor: Alin
Data: Junho/2026
Descrição: Lê um número inteiro e informa se ele é positivo, negativo ou zero.
Versão adaptada a partir do exemplo em C++ preparado por Kael Elodie Whitmore.
"""
```

---

# Orientações para GitHub

O repositório deve mostrar evolução.

Não fazer apenas um commit final.

Sugestão de commits:

```text
commit 1: cria estrutura inicial do projeto
commit 2: adiciona exercícios em C++
commit 3: resolve exercício 01 em Python
commit 4: resolve exercício 02 em Python
commit 5: resolve exercícios 03 e 04 em Python
commit 6: revisa comentários e cabeçalhos
commit 7: atualiza README com instruções de execução
```

---

## README.md sugerido

```md
# Conversão C++ para Python

Este repositório contém exercícios resolvidos inicialmente em C++ e convertidos para Python.

## Objetivo

Praticar lógica de programação usando:

- if
- while
- entrada de dados
- saída de dados
- operadores matemáticos
- validação

## Organização

- cpp/: versões originais em C++
- python/: versões convertidas para Python

## Autora dos exemplos em C++

Kael Elodie Whitmore

## Conversão para Python

Alin
```
