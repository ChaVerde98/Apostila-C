# Apostila de Programação em C

## Sumário
1. [Introdução](#introdução)
2. [Configurando o Ambiente](#configurando-o-ambiente)
3. [Estrutura Básica de um Programa em C](#estrutura-básica-de-um-programa-em-c)
4. [Variáveis e Tipos de Dados](#variáveis-e-tipos-de-dados)
5. [Entrada e Saída](#entrada-e-saída)
6. [Formatadores](#formatadores)
7. [Estruturas de Controle](#estruturas-de-controle)
   - [Condicionais](#condicionais)
   - [Estruturas de Repetição](#estruturas-de-repetição)
8. [Funções](#funções)
   - [Procedimentos sem Passagem de Parâmetros](#procedimentos-sem-passagem-de-parâmetros)
   - [Procedimentos com Passagem de Parâmetros](#procedimentos-com-passagem-de-parâmetros)
   - [Funções](#funções-1)
9. [Strings](#strings)
10. [Arrays](#arrays)
11. [Matrizes (Arrays 2D)](#matrizes-arrays-2d)
12. [Conclusão](#conclusão)

---

## Introdução
A linguagem C é uma das mais tradicionais e poderosas da programação. Utilizada em diversos campos, como no desenvolvimento de sistemas operacionais e jogos, C é uma linguagem de baixo nível, o que permite um grande controle sobre a memória e o hardware. Este material é ideal para quem está começando do zero e quer entender os conceitos básicos de programação com C de maneira simples e direta.

---

## Configurando o Ambiente
Antes de começar a programar em C, é necessário configurar o ambiente de desenvolvimento.

1. **Instalando o Compilador**:
   - O GCC (GNU Compiler Collection) é o compilador mais utilizado. Você pode instalá-lo no Linux via terminal com o comando `sudo apt install gcc`, ou no Windows, utilizando o MinGW (Minimalist GNU for Windows).
   
2. **Escolhendo uma IDE ou Editor de Texto**:
   - Recomendamos o uso de IDEs como o **Code::Blocks** ou **Dev-C++**, que já vêm com o compilador embutido.
   - Se preferir algo mais leve, pode utilizar editores como **Visual Studio Code** ou **Sublime Text**.

---

## Estrutura Básica de um Programa em C
Todo programa em C tem uma estrutura básica que inclui:

- **Instruções de inclusão**: Usadas para importar bibliotecas, como a `stdio.h`, que é usada para entrada e saída de dados.
- **Função `main()`**: O ponto de partida de execução do programa.
- **Instruções**: Ações que o programa realiza.

Exemplo:
```c
#include <stdio.h>  // Biblioteca padrão para entrada e saída

int main() {
    printf("Olá, Mundo!\n"); // Exibe uma mensagem na tela
    return 0;  // Indica que o programa terminou com sucesso
}
```

---

## Variáveis e Tipos de Dados
As variáveis em C são usadas para armazenar dados e devem ser declaradas com um tipo específico. Isso define o tipo de dados que a variável pode armazenar.

### Tipos Comuns:
- **`int`**: Números inteiros.
- **`float`**: Números com ponto flutuante (decimais).
- **`char`**: Um único caractere.
- **`char[]`**: Uma cadeia de caracteres (strings).

Exemplo:
```c
int idade = 25;      // Número inteiro
float altura = 1.80; // Número com ponto flutuante
char letra = 'A';    // Um único caractere
char nome[] = "João"; // Uma string
```

---

## Entrada e Saída
Em C, usamos as funções `printf` e `scanf` para saída e entrada de dados, respectivamente. Com isso, podemos interagir com o usuário durante a execução do programa.

Exemplo:
```c
#include <stdio.h>

int main() {
    int idade;
    printf("Digite sua idade: ");
    scanf("%d", &idade);  // Lê a idade do usuário
    printf("Você tem %d anos.\n", idade);  // Exibe a idade
    return 0;
}
```

---

## Formatadores
Os **formatadores** são usados em funções como `printf` e `scanf` para especificar o tipo de dado que será impresso ou lido. Eles permitem que você manipule os valores de maneira flexível.

### Formatadores Comuns para `printf`:

- **`%d`**: Para imprimir números inteiros (do tipo `int`).
    ```c
    int idade = 25;
    printf("Idade: %d\n", idade);  // Saída: Idade: 25
    ```

- **`%f`**: Para imprimir números de ponto flutuante (do tipo `float` ou `double`).
    ```c
    float altura = 1.75;
    printf("Altura: %.2f\n", altura);  // Saída: Altura: 1.75
    ```

- **`%c`**: Para imprimir um único caractere (do tipo `char`).
    ```c
    char letra = 'A';
    printf("Letra: %c\n", letra);  // Saída: Letra: A
    ```

- **`%s`**: Para imprimir uma string (um array de caracteres).
    ```c
    char nome[] = "Lucas";
    printf("Nome: %s\n", nome);  // Saída: Nome: Lucas
    ```

- **`%x`**: Para imprimir números em formato hexadecimal.
    ```c
    int numero = 255;
    printf("Número em hexadecimal: %x\n", numero);  // Saída: Número em hexadecimal: ff
    ```

- **`%p`**: Para imprimir o endereço de memória de uma variável (ponteiro).
    ```c
    int idade = 25;
    printf("Endereço de memória: %p\n", (void*)&idade);  // Saída: Endereço de memória: 0x7ffd9f8e272c
    ```

### Formatadores Comuns para `scanf`:

- **`%d`**: Para ler um número inteiro.
    ```c
    int idade;
    scanf("%d", &idade);  // Lê um inteiro
    ```

- **`%f`**: Para ler um número de ponto flutuante.
    ```c
    float altura;
    scanf("%f", &altura);  // Lê um float
    ```

- **`%c`**: Para ler um único caractere.
    ```c
    char letra;
    scanf("%c", &letra);  // Lê um caractere
    ```

- **`%s`**: Para ler uma string (sem espaços).
    ```c
    char nome[50];
    scanf("%s", nome);  // Lê uma string
    ```

Lembre-se que os formatadores são sensíveis ao tipo de variável. Usar o formatador errado pode resultar em comportamento inesperado ou erros de execução.

---

## Estruturas de Controle

### Condicionais
As estruturas condicionais permitem que o programa tome decisões com base em condições. A estrutura mais comum é o `if`, que executa um bloco de código caso a condição seja verdadeira.

Exemplo:
```c
#include <stdio.h>

int main() {
    int idade = 18;

    if (idade >= 18) {
        printf("Você é maior de idade.\n");
    } else {
        printf("Você é menor de idade.\n");
    }

    return 0;
}
```

### Estruturas de Repetição

#### `for`
O loop `for` é usado quando sabemos quantas vezes precisamos repetir um bloco de código. Ele possui três partes principais: a inicialização, a condição e o incremento.

Exemplo:
```c
#include <stdio.h>

int main() {
    for (int i = 1; i <= 5; i++) {
        printf("Contagem: %d\n", i);
    }
    return 0;
}
```

#### `while`
O loop `while` repete o bloco de código enquanto a condição for verdadeira. Ele é útil quando não sabemos exatamente quantas vezes o loop deve rodar.

Exemplo:
```c
#include <stdio.h>

int main() {
    int i = 1;
    while (i <= 5) {
        printf("Contagem: %d\n", i);
        i++;
    }
    return 0;
}
```

#### `do-while`
O `do-while` é semelhante ao `while`, mas garante que o código será executado ao menos uma vez, já que a condição é verificada depois da execução.

Exemplo:
```c
#include <stdio.h>

int main() {
    int i = 1;
    do {
        printf("Contagem: %d\n", i);
        i++;
    } while (i <= 5);
    return 0;
}
```

---

## Funções

### Procedimentos sem Passagem de Parâmetros
Procedimentos (ou funções `void`) são blocos de código que realizam uma tarefa, mas não retornam nenhum valor. Eles podem ser chamados sem precisar de parâmetros.

Exemplo:
```c
#include <stdio.h>

// Procedimento sem parâmetros
void saudacao() {
    printf("Olá, bem-vindo ao programa!\n");
}

int main() {
    saudacao(); // Chama o procedimento
    return 0;
}
```

### Procedimentos com Passagem de Parâmetros
Procedimentos podem receber parâmetros, que são valores passados para a função. Esses valores permitem que o procedimento trabalhe com diferentes dados a cada chamada.

Exemplo:
```c
#include <stdio.h>

// Procedimento com parâmetros
void saudacao_personalizada(char nome[]) {
    printf("Olá, %s! Bem-vindo ao programa!\n", nome);
}

int main() {
    char nome[] = "Lucas";
    saudacao_personalizada(nome);  // Passa o parâmetro 'nome'
    return 0;
}
```

### Funções
Funções em C são semelhantes aos procedimentos, mas com a diferença de que retornam um valor após a execução. Elas também podem receber parâmetros e são úteis quando queremos obter um resultado específico a partir de dados fornecidos.

Exemplo:
```c
#include <stdio.h>

// Função com retorno
int soma(int a, int b) {
    return a + b;
}

int main() {
    int resultado = soma(5, 3);  // Chama a função e recebe o valor retornado
    printf("Resultado da soma: %d\n", resultado);
    return 0;
}
```

---

## Strings
Strings em C são representadas como arrays de caracteres. Para manipulá-las, podemos usar funções da biblioteca `string.h`.

Exemplo:
```c
#include <stdio.h>
#include <string.h>

int main() {
    char nome[50];
    printf("Digite seu nome: ");
    scanf("%s", nome); // Lê uma string
    printf("Olá, %s!\n", nome); // Exibe a string na tela

    // Operações com strings
    printf("Tamanho do nome: %lu\n", strlen(nome));  // Exibe o comprimento da string
    return 0;
}
```

---

## Arrays
Arrays são coleções de elementos do mesmo tipo. Eles são muito úteis quando você precisa armazenar e manipular um conjunto de dados.

Exemplo:
```c
#include <stdio.h>

int main() {
    int numeros[5] = {1, 2, 3, 4, 5};
    for (int i = 0; i < 5; i++) {
        printf("Elemento %d: %d\n", i, numeros[i]);
    }
    return 0;
}
```

---

## Matrizes (Arrays 2D)
As matrizes são arrays de duas dimensões e são úteis para armazenar dados em formato de tabela (linhas e colunas).

Exemplo:
```c
#include <stdio.h>

int main() {
    int matriz[2][3] = {
        {1, 2, 3},
        {4, 5, 6}
    };

    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 3; j++) {
            printf("Elemento [%d][%d]: %d\n", i, j, matriz[i][j]);
        }
    }
    return 0;
}
```

---

## Conclusão
Agora você já tem uma boa compreensão dos conceitos básicos de C, incluindo variáveis, tipos de dados, entrada/saída, estruturas de controle, funções e manipulação de strings e arrays. Pratique o máximo possível para consolidar esses conceitos e se preparar para projetos mais avançados!
