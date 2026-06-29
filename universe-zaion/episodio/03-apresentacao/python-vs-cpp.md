## Python para quem já programa em C++

### Material de Apoio

**Preparado por: Kael**

---

## Introdução

Alin,

Você já conhece lógica de programação e sabe programar em C++.

Isso significa que você não precisa aprender programação novamente.

O objetivo deste material é apenas mostrar como escrever em Python aquilo que você já sabe fazer em C++.

Pense em Python como um novo idioma.

A lógica continua a mesma.

---

# 1. Primeiro Programa

## C++

```cpp
#include <iostream>

using namespace std;

int main()
{
    cout << "Olá Mundo!" << endl;

    return 0;
}
```

## Python

```python
print("Olá Mundo!")
```

### Observação

Python exige muito menos código.

Não existe função principal (`main()`).

O programa é executado de cima para baixo.

---

# 2. Variáveis

## C++

```cpp
string nome = "Alin";
int idade = 12;
float altura = 1.55;
```

## Python

```python
nome = "Alin"
idade = 12
altura = 1.55
```

### Diferença

Python identifica o tipo automaticamente.

Não é necessário declarar:

```cpp
int
float
string
```

---

# 3. Entrada de Dados

## C++

```cpp
string nome;
cout << "Nome: ";
cin >> nome;
```

## Python

```python
nome = input("Nome: ")
```

---

# 4. Exibindo Informações

## C++

```cpp
cout << "Olá " << nome;
```

## Python

```python
print("Olá", nome)
```

ou

```python
print(f"Olá {nome}")
```

---

# 5. Estruturas Condicionais

## C++

```cpp
if (idade >= 18)
{
    cout << "Maior";
}
else
{
    cout << "Menor";
}
```

## Python

```python
if idade >= 18:
    print("Maior")
else:
    print("Menor")
```

### Atenção

Python usa:

```python
:
```

e indentação.

Não utiliza:

```cpp
{
}
```

---

# 6. Repetição

## While

### C++

```cpp
while (x < 10)
{
    x++;
}
```

### Python

```python
while x < 10:
    x += 1
```

---

## For

### C++

```cpp
for(int i=0;i<10;i++)
{
    cout << i;
}
```

### Python

```python
for i in range(10):
    print(i)
```

---

# 7. Funções

## C++

```cpp
int soma(int a, int b)
{
    return a + b;
}
```

## Python

```python
def soma(a, b):
    return a + b
```

---

# 8. Listas

### C++

```cpp
vector<string> nomes;
```

### Python

```python
nomes = []
```

### Adicionar um elemento

```python
nomes.append("Alin")
nomes.append("Leo")
nomes.append("Zeta")
```

Resultado:

```text
['Alin', 'Leo', 'Zeta']
```

---

### Exibir todos os elementos

```python
print(nomes)
```

ou

```python
for nome in nomes:
    print(nome)
```

Saída:

```text
Alin
Leo
Zeta
```

---

### Exibir um elemento específico

```python
print(nomes[0])
print(nomes[1])
print(nomes[2])
```

Saída:

```text
Alin
Leo
Zeta
```

---

### Alterar um elemento

```python
nomes[1] = "Kael"
```

Resultado:

```text
['Alin', 'Kael', 'Zeta']
```

---

### Excluir um elemento pelo valor

```python
nomes.remove("Kael")
```

Resultado:

```text
['Alin', 'Zeta']
```

---

### Excluir pela posição

```python
del nomes[0]
```

Resultado:

```text
['Zeta']
```

---

### Limpar toda a lista

```python
nomes.clear()
```

Resultado:

```text
[]
```

---

### Total de elementos

```python
print(len(nomes))
```

Exemplo:

```python
nomes = ["Alin", "Leo", "Zeta"]
print(len(nomes))
```

Saída:

```text
3
```

---

### Verificar se existe um elemento

```python
if "Zeta" in nomes:
    print("Encontrado")
else:
    print("Não encontrado")
```

---

### Percorrer toda a lista

```python
for nome in nomes:
    print(nome)
```

ou, caso queira a posição:

```python
for indice, nome in enumerate(nomes):
    print(indice, nome)
```

Saída:

```text
0 Alin
1 Leo
2 Zeta
```

## Observação

> **Python oferece uma das implementações de listas mais completas entre as linguagens de programação modernas.**
>
> Com poucas instruções é possível adicionar, remover, pesquisar, ordenar e percorrer grandes quantidades de dados.
>
> Durante nossos estudos sobre Inteligência Artificial, utilizaremos listas para armazenar exemplos, resultados de processamento e conjuntos de treinamento. Elas serão uma das estruturas de dados mais importantes ao longo do curso.


## Antes de Escrever Código

Programar exige apenas duas coisas:

1. Um editor de texto
2. Um interpretador Python

Não existe etapa de compilação.

Python interpreta o código diretamente.

---

Você pode testar seu código online.

|[` programiz.com `](https://www.programiz.com/python-programming/online-compiler)|
|---|

---

# Exercício 1

Crie um programa que:

1. Solicite o nome do usuário.
2. Solicite a idade.
3. Exiba:

```text
Olá Alin!
Você tem 12 anos.
```

---

# Exercício 2

Crie um programa que:

1. Leia dois números.
2. Exiba:

   * soma
   * subtração
   * multiplicação
   * divisão

---

# Exemplo

# C++

```cpp
#include <iostream>
#include <cmath>

using namespace std;

//--------------------------------------------------
// Função para ler um número inteiro
//--------------------------------------------------
int lerNumero(string mensagem)
{
    int valor;

    cout << mensagem;
    cin >> valor;

    return valor;
}

//--------------------------------------------------
// Função para exibir os resultados
//--------------------------------------------------
void exibirResultados(int a, int b)
{
    cout << "\n=== RESULTADOS ===\n";

    cout << "Soma: " << (a + b) << endl;
    cout << "Subtracao: " << (a - b) << endl;
    cout << "Multiplicacao: " << (a * b) << endl;

    if (b != 0)
    {
        cout << "Divisao: " << (float)a / b << endl;
    }
    else
    {
        cout << "Divisao: impossivel (divisao por zero)" << endl;
    }

    if (a >= 0)
    {
        cout << "Raiz quadrada de " << a
             << ": " << sqrt(a) << endl;
    }
    else
    {
        cout << "Raiz quadrada de " << a
             << ": numero negativo" << endl;
    }

    if (b >= 0)
    {
        cout << "Raiz quadrada de " << b
             << ": " << sqrt(b) << endl;
    }
    else
    {
        cout << "Raiz quadrada de " << b
             << ": numero negativo" << endl;
    }
}

//--------------------------------------------------
// Programa principal
//--------------------------------------------------
int main()
{
    int numero1;
    int numero2;

    numero1 = lerNumero("Digite o primeiro numero: ");
    numero2 = lerNumero("Digite o segundo numero: ");

    exibirResultados(numero1, numero2);

    return 0;
}
```

---

# Python

```python
import math

# -----------------------------------------
# Função para ler um número inteiro
# -----------------------------------------
def ler_numero(mensagem):
    return int(input(mensagem))


# -----------------------------------------
# Função para exibir os resultados
# -----------------------------------------
def exibir_resultados(a, b):

    print("\n=== RESULTADOS ===")

    print(f"Soma: {a + b}")
    print(f"Subtração: {a - b}")
    print(f"Multiplicação: {a * b}")

    if b != 0:
        print(f"Divisão: {a / b}")
    else:
        print("Divisão: impossível (divisão por zero)")

    if a >= 0:
        print(f"Raiz quadrada de {a}: {math.sqrt(a)}")
    else:
        print(f"Raiz quadrada de {a}: número negativo")

    if b >= 0:
        print(f"Raiz quadrada de {b}: {math.sqrt(b)}")
    else:
        print(f"Raiz quadrada de {b}: número negativo")


# -----------------------------------------
# Programa principal
# -----------------------------------------
numero1 = ler_numero("Digite o primeiro número: ")
numero2 = ler_numero("Digite o segundo número: ")

exibir_resultados(numero1, numero2)
```

---

### Observações

| Conceito              | C++                | Python             |
| --------------------- | ------------------ | ------------------ |
| Biblioteca matemática | `#include <cmath>` | `import math`      |
| Função                | `int lerNumero()`  | `def ler_numero()` |
| Leitura               | `cin >> valor`     | `input()`          |
| Saída                 | `cout <<`          | `print()`          |
| Blocos                | `{ }`              | Indentação         |
| Raiz quadrada         | `sqrt()`           | `math.sqrt()`      |

---

> **Perceba que a lógica é exatamente a mesma.**
>
> A principal diferença não está no algoritmo, mas na forma como cada linguagem escreve as instruções. Esse é o motivo pelo qual alguém que já programa em C++ costuma aprender Python muito rapidamente. — *Kael*

---

# Desafio

Pesquise:

```python
list
tuple
dictionary
```

Na próxima aula vamos utilizar essas estruturas para criar programas mais inteligentes.

---

### Mensagem da Kael

> Você já sabe programar.
>
> Não tenha medo do Python.
>
> A lógica continua sendo a mesma.
>
> O segredo não é decorar comandos.
>
> É aprender a resolver problemas.

---
