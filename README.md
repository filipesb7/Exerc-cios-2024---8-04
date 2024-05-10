#Lista de exercícios algoritmo 2024

1 - Verificador de Números Primos: Crie um programa que determine se um número fornecido
pelo usuário é primo ou não

#include <stdio.h>

int main() {
    int numero, primo = 1; // Assumimos que o número é primo inicialmente

    printf("Digite um número inteiro positivo para verificar se é primo: ");
    scanf("%d", &numero);

    if (numero <= 1)
        primo = 0; // Se o número for menor ou igual a 1, não é primo
    else {
        for (int i = 2; i <= numero / 2; i++) {
            if (numero % i == 0) {
                primo = 0; // Se o número for divisível por algum número de 2 até sua metade, não é primo
                break;
            }
        }
    }

    if (primo)
        printf("%d é um número primo.\n", numero);
    else
        printf("%d não é um número primo.\n", numero);

    return 0;
}

2 - Série de Fibonacci: Escreva um programa que gere os primeiros N termos da série de
Fibonacci, onde N é fornecido pelo usuário

#include <stdio.h>

int main() {
    int n, termo1 = 0, termo2 = 1, proximoTermo;

    printf("Digite o número de termos da série de Fibonacci que deseja gerar: ");
    scanf("%d", &n);

    printf("Os primeiros %d termos da série de Fibonacci são:\n", n);

    for (int i = 0; i < n; i++) {
        if (i <= 1)
            proximoTermo = i;
        else {
            proximoTermo = termo1 + termo2;
            termo1 = termo2;
            termo2 = proximoTermo;
        }
        printf("%d ", proximoTermo);
    }

    printf("\n");

    return 0;
}



3 - Conversor de Temperatura: Crie um programa que converta a temperatura de Celsius para
Fahrenheit ou vice-versa, dependendo da escolha do usuário.

#include <stdio.h>

int main() {
    int escolha;
    float temperatura, resultado;

    printf("Escolha a conversão desejada:\n");
    printf("1. Celsius para Fahrenheit\n");
    printf("2. Fahrenheit para Celsius\n");
    printf("Digite sua escolha: ");
    scanf("%d", &escolha);

    printf("Digite a temperatura: ");
    scanf("%f", &temperatura);

    if (escolha == 1) {
        resultado = (temperatura * 9 / 5) + 32; // Celsius para Fahrenheit
        printf("A temperatura em Fahrenheit é: %.2f\n", resultado);
    } else if (escolha == 2) {
        resultado = (temperatura - 32) * 5 / 9; // Fahrenheit para Celsius
        printf("A temperatura em Celsius é: %.2f\n", resultado);
    } else {
        printf("Escolha inválida. Por favor, selecione 1 ou 2.\n");
    }

    return 0;
}


4 - Jogo de Adivinhação: Implemente um jogo de adivinhação onde o programa gera um número
aleatório e o usuário tenta adivinhar. O programa deve dar dicas se o número fornecido pelo
usuário é maior ou menor do que o número gerado

#include <stdio.h>

int main() {
    printf("Bem-vindo ao jogo de adivinhação!\n");
    printf("Tente adivinhar o número entre 1 e 100.\n");

    int numeroAleatorio = 42; // número a ser adivinhado

    int palpite;
    while (1) {
        printf("Digite seu palpite: ");
        scanf("%d", &palpite);

        if (palpite == numeroAleatorio) {
            printf("Parabéns! Você acertou o número %d.\n", numeroAleatorio);
            break;
        } else if (palpite > numeroAleatorio) {
            printf("Palpite muito alto. Tente novamente.\n");
        } else {
            printf("Palpite muito baixo. Tente novamente.\n");
        }
    }

    return 0;
}



5 - Média de Números: Escreva um programa que solicite ao usuário quantos números ele deseja
inserir e depois calcule a média desses números.

#include <stdio.h>

int main() {
    int quantidadeNumeros;
    float soma = 0.0, numero;

    printf("Quantos números você deseja inserir? ");
    scanf("%d", &quantidadeNumeros);

    for (int i = 0; i < quantidadeNumeros; i++) {
        printf("Digite o número %d: ", i + 1);
        scanf("%f", &numero);
        soma += numero;
    }

    float media = soma / quantidadeNumeros;
    printf("A média dos números inseridos é: %.2f\n", media);

    return 0;
}


6 - Contador de Dígitos: Crie um programa que conte o número de dígitos em um número inteiro
fornecido pelo usuário.

#include <stdio.h>

int main() {
    int numero, contador = 0;

    printf("Digite um número inteiro: ");
    scanf("%d", &numero);

    // Conta o número de dígitos usando um loop while
    while (numero != 0) {
        numero /= 10; // Divide o número por 10 para remover o último dígito
        contador++;   // Incrementa o contador de dígitos
    }

    printf("O número fornecido possui %d dígitos.\n", contador);

    return 0;
}



7 - Calculadora de Potência: Peça ao usuário para inserir uma base e um expoente, e calcule a
potência correspondente

#include <stdio.h>

int main() {
    double base, expoente, resultado = 1;

    printf("Digite a base: ");
    scanf("%lf", &base);

    printf("Digite o expoente: ");
    scanf("%lf", &expoente);

    // Calcula a potência
    for (int i = 0; i < expoente; i++) {
        resultado *= base;
    }

    printf("O resultado de %.2lf elevado a %.2lf é: %.2lf\n", base, expoente, resultado);

    return 0;
}


8 - Conversor de Moeda: Crie um programa que converta um valor em uma moeda para outra
moeda, com base em taxas de conversão fornecidas pelo usuário.

#include <stdio.h>

int main() {
    double valorOriginal, taxaConversao, valorConvertido;

    // Solicita o valor original e a taxa de conversão ao usuário
    printf("Digite o valor original: ");
    scanf("%lf", &valorOriginal);

    printf("Digite a taxa de conversão: ");
    scanf("%lf", &taxaConversao);

    // Calcula o valor convertido
    valorConvertido = valorOriginal * taxaConversao;

    // Exibe o valor convertido na tela
    printf("O valor convertido é: %.2lf\n", valorConvertido);

    return 0;
}


#include <stdio.h>

int main() {
    int quantidadeNotas;
    double nota, peso, somaNotas = 0, somaPesos = 0;

    // Solicita ao usuário a quantidade de notas
    printf("Digite a quantidade de notas: ");
    scanf("%d", &quantidadeNotas);

    // Loop para ler as notas e os pesos correspondentes
    for (int i = 0; i < quantidadeNotas; i++) {
        printf("Digite a nota %d: ", i + 1);
        scanf("%lf", &nota);

        printf("Digite o peso da nota %d: ", i + 1);
        scanf("%lf", &peso);

        // Soma das notas ponderadas
        somaNotas += nota * peso;

        // Soma dos pesos
        somaPesos += peso;
    }

    // Calcula a média ponderada
    double mediaPonderada = somaNotas / somaPesos;

    // Exibe a média ponderada na tela
    printf("A média ponderada é: %.2lf\n", mediaPonderada);

    return 0;
}









EXERCÍCIOS VETORES/ARRAYS - 2024


1 - Soma de elementos em um vetor:
// Escreva um programa que calcula a soma de todos os
// elementos em um vetor


#include <stdio.h>

int main() {
    int tamanho;

    // Solicita ao usuário o tamanho do vetor
    printf("Digite o tamanho do vetor: ");
    scanf("%d", &tamanho);

    // Declara o vetor com o tamanho fornecido pelo usuário
    int vetor[tamanho];

    // Solicita ao usuário que insira os elementos do vetor
    printf("Digite os elementos do vetor:\n");
    for (int i = 0; i < tamanho; i++) {
        printf("Elemento %d: ", i + 1);
        scanf("%d", &vetor[i]);
    }

    // Calcula a soma de todos os elementos do vetor
    int soma = 0;
    for (int i = 0; i < tamanho; i++) {
        soma += vetor[i];
    }

    // Exibe a soma na tela
    printf("A soma de todos os elementos do vetor é: %d\n", soma);

    return 0;
}



2 - Maior elemento em um vetor:
// Escreva um programa que encontre o
// maior elemento em um vetor.

#include <stdio.h>

int main() {
    int tamanho;

    // Solicita ao usuário o tamanho do vetor
    printf("Digite o tamanho do vetor: ");
    scanf("%d", &tamanho);

    // Declara o vetor com o tamanho fornecido pelo usuário
    int vetor[tamanho];

    // Solicita ao usuário que insira os elementos do vetor
    printf("Digite os elementos do vetor:\n");
    for (int i = 0; i < tamanho; i++) {
        printf("Elemento %d: ", i + 1);
        scanf("%d", &vetor[i]);
    }

    // Inicializa a variável para armazenar o maior elemento
    int maior = vetor[0];

    // Encontra o maior elemento no vetor
    for (int i = 1; i < tamanho; i++) {
        if (vetor[i] > maior) {
            maior = vetor[i];
        }
    }

    // Exibe o maior elemento na tela
    printf("O maior elemento no vetor é: %d\n", maior);

    return 0;
}



3 - Média dos elementos em um vetor:
// Escreva um programa que calcule a média
// dos elementos em um vetor.

#include <stdio.h>

int main() {
    int tamanho;

    // Solicita ao usuário o tamanho do vetor
    printf("Digite o tamanho do vetor: ");
    scanf("%d", &tamanho);

    // Declara o vetor com o tamanho fornecido pelo usuário
    int vetor[tamanho];

    // Solicita ao usuário que insira os elementos do vetor
    printf("Digite os elementos do vetor:\n");
    for (int i = 0; i < tamanho; i++) {
        printf("Elemento %d: ", i + 1);
        scanf("%d", &vetor[i]);
    }

    // Calcula a soma de todos os elementos do vetor
    int soma = 0;
    for (int i = 0; i < tamanho; i++) {
        soma += vetor[i];
    }

    // Calcula a média dos elementos do vetor
    double media = (double) soma / tamanho;

    // Exibe a média na tela
    printf("A média dos elementos do vetor é: %.2lf\n", media);

    return 0;
}


4 - Inversão de vetor:
// Escreva um programa que inverta a
// ordem dos elementos em um vetor.

#include <stdio.h>

int main() {
    int vetor[] = {1, 2, 3, 4, 5};
    int tamanho = sizeof(vetor) / sizeof(vetor[0]);

    printf("Vetor original:\n");
    for (int i = 0; i < tamanho; i++) {
        printf("%d ", vetor[i]);
    }
    printf("\n");

    printf("Vetor invertido:\n");
    for (int i = tamanho - 1; i >= 0; i--) {
        printf("%d ", vetor[i]);
    }
    printf("\n");

    return 0;
}






Revisão for

Questão 1
printf("\nQuestão 1: Qual é a sintaxe correta para
declarar uma variável inteira em C?\n");
printf("a) int x;\n");
printf("b) var x;\n");
printf("c) integer x;\n");
printf("d) número x;\n”);

#include <stdio.h>

int main() {
    char resposta;

    // Exibe a pergunta
    printf("Questão 1: Qual é a sintaxe correta para declarar uma variável inteira em C?\n");
    printf("a) int x;\n");
    printf("b) var x;\n");
    printf("c) integer x;\n");
    printf("d) número x;\n");

    // Solicita a resposta ao usuário
    printf("Digite sua resposta (a, b, c ou d): ");
    scanf(" %c", &resposta);

    // Verifica se a resposta está correta e exibe o resultado
    if (resposta == 'a' || resposta == 'A') {
        printf("Resposta correta! Parabéns!\n");
    } else {
        printf("Resposta incorreta! A resposta correta é 'a'.\n");
    }

    return 0;
}



Questão 2
printf("\nQuestão 2: Qual é a função usada para
imprimir no console em C?\n");
printf("a) print();\n");
printf("b) console.log();\n");
printf("c) printtext();\n");
printf("d) printf();\n”);


#include <stdio.h>

int main() {
    char resposta;

    // Exibe a pergunta
    printf("Questão 2: Qual é a função usada para imprimir no console em C?\n");
    printf("a) print();\n");
    printf("b) console.log();\n");
    printf("c) printtext();\n");
    printf("d) printf();\n");

    // Solicita a resposta ao usuário
    printf("Digite sua resposta (a, b, c ou d): ");
    scanf(" %c", &resposta);

    // Verifica se a resposta está correta e exibe o resultado
    if (resposta == 'd' || resposta == 'D') {
        printf("Resposta correta! Parabéns!\n");
    } else {
        printf("Resposta incorreta! A resposta correta é 'd'.\n");
    }

    return 0;
}



Questão 3
printf("\nQuestão 3: O que o operador '==' faz em C?
\n");
printf("a) Atribui um valor a uma variável.\n");
printf("b) Compara dois valores.\n");
printf("c) Divide dois valores.\n");
printf("d) Multiplica dois valores.\n”);


#include <stdio.h>

int main() {
    char resposta;

    // Exibe a pergunta
    printf("Questão 3: O que o operador '==' faz em C?\n");
    printf("a) Atribui um valor a uma variável.\n");
    printf("b) Compara dois valores.\n");
    printf("c) Divide dois valores.\n");
    printf("d) Multiplica dois valores.\n");

    // Solicita a resposta ao usuário
    printf("Digite sua resposta (a, b, c ou d): ");
    scanf(" %c", &resposta);

    // Verifica se a resposta está correta e exibe o resultado
    if (resposta == 'b' || resposta == 'B') {
        printf("Resposta correta! Parabéns!\n");
    } else {
        printf("Resposta incorreta! A resposta correta é 'b'.\n");
    }

    return 0;
}



Questão 4
printf("\nQuestão 4: Qual é o operador lógico para
'OU' em C?\n");
printf("a) &&\n");
printf("b) ||\n");
printf("c) !\n");
printf("d) <>\n");

#include <stdio.h>

int main() {
    char resposta;

    // Exibe a pergunta
    printf("Questão 4: Qual é o operador lógico para 'OU' em C?\n");
    printf("a) &&\n");
    printf("b) ||\n");
    printf("c) !\n");
    printf("d) <>\n");

    // Solicita a resposta ao usuário
    printf("Digite sua resposta (a, b, c ou d): ");
    scanf(" %c", &resposta);

    // Verifica se a resposta está correta e exibe o resultado
    if (resposta == 'b' || resposta == 'B') {
        printf("Resposta correta! Parabéns!\n");
    } else {
        printf("Resposta incorreta! A resposta correta é 'b'.\n");
    }

    return 0;
}



Questão 5
printf("\nQuestão 5: Qual é a estrutura de controle
usada para repetição em C?\n");
printf("a) if\n");
printf("b) switch\n");
printf("c) for\n");
printf("d) else\n”);


#include <stdio.h>

int main() {
    char resposta;

    // Exibe a pergunta
    printf("Questão 5: Qual é a estrutura de controle usada para repetição em C?\n");
    printf("a) if\n");
    printf("b) switch\n");
    printf("c) for\n");
    printf("d) else\n");

    // Solicita a resposta ao usuário
    printf("Digite sua resposta (a, b, c ou d): ");
    scanf(" %c", &resposta);

    // Verifica se a resposta está correta e exibe o resultado
    if (resposta == 'c' || resposta == 'C') {
        printf("Resposta correta! Parabéns!\n");
    } else {
        printf("Resposta incorreta! A resposta correta é 'c'.\n");
    }

    return 0;
}


Questão 6
printf("\nQuestão 6: Qual é a função usada para ler um
número inteiro do teclado em C?\n");
printf("a) read_integer();\n");
printf("b) input_int();\n");
printf("c) scanf();\n");
printf("d) get_int();\n”);


#include <stdio.h>

int main() {
    char resposta;

    // Exibe a pergunta
    printf("Questão 6: Qual é a função usada para ler um número inteiro do teclado em C?\n");
    printf("a) read_integer();\n");
    printf("b) input_int();\n");
    printf("c) scanf();\n");
    printf("d) get_int();\n");

    // Solicita a resposta ao usuário
    printf("Digite sua resposta (a, b, c ou d): ");
    scanf(" %c", &resposta);

    // Verifica se a resposta está correta e exibe o resultado
    if (resposta == 'c' || resposta == 'C') {
        printf("Resposta correta! Parabéns!\n");
    } else {
        printf("Resposta incorreta! A resposta correta é 'c'.\n");
    }

    return 0;
}



Questão 7 printf("\nQuestão 10: Qual é o valor da
expressão 5 +
3 * 2 em C?\n");
printf("a) 16\n");
printf("b) 11\n");
printf("c) 13\n");
printf("d) 10\n");



#include <stdio.h>

int main() {
    char resposta;

    // Exibe a pergunta
    printf("Questão 10: Qual é o valor da expressão 5 + 3 * 2 em C?\n");
    printf("a) 16\n");
    printf("b) 11\n");
    printf("c) 13\n");
    printf("d) 10\n");

    // Solicita a resposta ao usuário
    printf("Digite sua resposta (a, b, c ou d): ");
    scanf(" %c", &resposta);

    // Verifica se a resposta está correta e exibe o resultado
    if (resposta == 'c' || resposta == 'C') {
        printf("Resposta correta! Parabéns!\n");
    } else {
        printf("Resposta incorreta! A resposta correta é 'c'.\n");
    }

    return 0;
}







Questionario 2 

1. **Soma de elementos em um array**: dado o int array[5] =
{1,2,3,4,5}, Escreva um programa que calcule a soma de todos
os elementos em um array de inteiros.


#include <stdio.h>

int main() {
    int array[5] = {1, 2, 3, 4, 5};
    int tamanho = sizeof(array) / sizeof(array[0]); // Calcula o tamanho do array
    int soma = 0;

    // Itera sobre o array e calcula a soma dos elementos
    for (int i = 0; i < tamanho; i++) {
        soma += array[i];
    }

    printf("A soma de todos os elementos do array é: %d\n", soma);

    return 0;
}



2. **Média de elementos em um array**:dado o float array[] =
{1.5, 2.5, 3.5, 4.5, 5.5} Escreva um programa que calcule a
média dos elementos em um array de ponto flutuante.

#include <stdio.h>

int main() {
    float array[] = {1.5, 2.5, 3.5, 4.5, 5.5};
    int tamanho = sizeof(array) / sizeof(array[0]); // Calcula o tamanho do array
    float soma = 0;

    // Calcula a soma de todos os elementos do array
    for (int i = 0; i < tamanho; i++) {
        soma += array[i];
    }

    // Calcula a média
    float media = soma / tamanho;

    printf("A média dos elementos do array é: %.2f\n", media);

    return 0;
}



3. **Contagem de caracteres em uma string**:
Escreva um programa que leia uma string do usuário e conte
quantos caracteres a string possui, excluindo o caractere nulo
de terminação '\0'. Em seguida, exiba o resultado.


#include <stdio.h>
#include <string.h>

int main() {
    char string[100];
    int tamanho;

    // Solicita ao usuário que insira a string
    printf("Digite uma string: ");
    fgets(string, sizeof(string), stdin);

    // Calcula o tamanho da string, excluindo o caractere nulo de terminação '\0'
    tamanho = strlen(string) - 1;

    printf("A string \"%s\" possui %d caracteres.\n", string, tamanho);

    return 0;
}



4. **Concatenação de strings**:
Escreva um programa que leia duas strings do usuário e
concatene-as em uma terceira string. Em seguida, exiba a
string resultante.


#include <stdio.h>
#include <string.h>

int main() {
    char string1[100];
    char string2[100];
    char resultado[200]; // Tamanho total deve ser suficiente para conter ambas as strings e o caractere nulo de terminação

    // Solicita ao usuário que insira as duas strings
    printf("Digite a primeira string: ");
    fgets(string1, sizeof(string1), stdin);

    printf("Digite a segunda string: ");
    fgets(string2, sizeof(string2), stdin);

    // Remove o caractere de nova linha do final de cada string
    string1[strcspn(string1, "\n")] = '\0';
    string2[strcspn(string2, "\n")] = '\0';

    // Concatena as duas strings
    strcpy(resultado, string1);
    strcat(resultado, string2);

    printf("A string resultante da concatenação é: %s\n", resultado);

    return 0;
}



5. **Comparação de strings**:
Escreva um programa que leia duas strings do usuário e
compare-as para determinar se são iguais ou diferentes. Exiba
o resultado da comparação.

#include <stdio.h>
#include <string.h>

int main() {
    char string1[100];
    char string2[100];

    // Solicita ao usuário que insira as duas strings
    printf("Digite a primeira string: ");
    scanf("%s", string1);

    printf("Digite a segunda string: ");
    scanf("%s", string2);

    // Compara as duas strings
    int comparacao = strcmp(string1, string2);

    // Exibe o resultado da comparação
    if (comparacao == 0) {
        printf("As strings são iguais.\n");
    } else {
        printf("As strings são diferentes.\n");
    }

    return 0;
}



6. **Cópia de strings**:
Escreva um programa que leia uma string do usuário e copie-
a para outra string. Em seguida, exiba a string copiada.


#include <stdio.h>
#include <string.h>

int main() {
    char original[100];
    char copia[100];

    // Solicita ao usuário que insira a string
    printf("Digite uma string: ");
    scanf("%s", original);

    // Copia a string original para a string de cópia
    strcpy(copia, original);

    // Exibe a string copiada
    printf("A string copiada é: %s\n", copia);

    return 0;
}



7. **Inversão de uma string**:
Escreva um programa que leia uma string do usuário e
inverta os caracteres na string. Em seguida, exiba a string
invertida.


#include <stdio.h>
#include <string.h>

int main() {
    char string[100];

    // Solicita ao usuário que insira a string
    printf("Digite uma string: ");
    scanf("%s", string);

    // Obtém o tamanho da string
    int tamanho = strlen(string);

    // Inverte os caracteres na string
    for (int i = 0; i < tamanho / 2; i++) {
        char temp = string[i];
        string[i] = string[tamanho - i - 1];
        string[tamanho - i - 1] = temp;
    }

    // Exibe a string invertida
    printf("A string invertida é: %s\n", string);

    return 0;
}



8. **Contagem de ocorrências de uma letra em uma string**:
Escreva um programa que leia uma string e uma letra do
usuário e conte quantas vezes a letra aparece na string. Exiba
o resultado.


#include <stdio.h>
#include <string.h>

int main() {
    char string[100];
    char letra;
    int contador = 0;

    // Solicita ao usuário que insira a string
    printf("Digite uma string: ");
    fgets(string, sizeof(string), stdin);

    // Remove o caractere de nova linha do final da string
    string[strcspn(string, "\n")] = '\0';

    // Solicita ao usuário que insira a letra a ser contada
    printf("Digite uma letra: ");
    scanf(" %c", &letra);

    // Conta quantas vezes a letra aparece na string
    int tamanho = strlen(string);
    for (int i = 0; i < tamanho; i++) {
        if (string[i] == letra) {
            contador++;
        }
    }

    // Exibe o resultado
    printf("A letra '%c' aparece %d vezes na string.\n", letra, contador);

    return 0;
}








Questionario Matrizes 


**Exercício 1:**
Crie uma matriz 3x3 para armazenar números inteiros. Preencha
a matriz com valores fornecidos pelo usuário e depois exiba a
matriz na tela.

#include <stdio.h>

int main() {
    int matriz[3][3];

    // Preenche a matriz com valores fornecidos pelo usuário
    printf("Digite os valores para preencher a matriz 3x3:\n");
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            scanf("%d", &matriz[i][j]);
        }
    }

    // Exibe a matriz na tela
    printf("\nMatriz 3x3:\n");
    for (int i = 0; i < 3; i++) {
        printf("%d %d %d\n", matriz[i][0], matriz[i][1], matriz[i][2]);
    }

    return 0;
}



**Exercício 2:**
Crie duas matrizes 2x2 e realize a soma entre elas. Armazene o
resultado em uma terceira matriz e exiba o resultado na tela.


#include <stdio.h>

int main() {
    int resultado[2][2];

    // Solicita ao usuário que insira os valores para preencher as duas matrizes e realiza a soma
    printf("Digite os valores para preencher as duas matrizes 2x2 e realizar a soma:\n");
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            int valor1, valor2;
            printf("Digite o valor para a posição [%d][%d] da primeira matriz: ", i, j);
            scanf("%d", &valor1);
            printf("Digite o valor para a posição [%d][%d] da segunda matriz: ", i, j);
            scanf("%d", &valor2);
            resultado[i][j] = valor1 + valor2;
        }
    }

    // Exibe o resultado na tela
    printf("\nMatriz resultante da soma:\n");
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            printf("%d ", resultado[i][j]);
        }
        printf("\n");
    }

    return 0;
}



**Exercício 3:**
Crie uma matriz 4x4 e preencha-a com números aleatórios. Em
seguida, calcule e imprima a soma de cada linha e de cada
coluna.


#include <stdio.h>

int main() {
    int matriz[4][4];

    // Preenche a matriz com números aleatórios e calcula as somas de linhas e colunas
    printf("Matriz 4x4 preenchida com números aleatórios:\n");
    for (int i = 0; i < 4; i++) {
        int soma_linha = 0;
        int soma_coluna = 0;
        for (int j = 0; j < 4; j++) {
            matriz[i][j] = rand() % 100; // Gera um número aleatório entre 0 e 99
            printf("%d ", matriz[i][j]);
            soma_linha += matriz[i][j];
            soma_coluna += matriz[j][i];
        }
        printf(" | Soma linha %d: %d\n", i + 1, soma_linha);
        printf("\n");
    }
    printf("\nSoma de cada coluna:\n");
    for (int j = 0; j < 4; j++) {
        printf("Soma coluna %d: %d\n", j + 1, soma_coluna);
    }

    return 0;
}



**Exercício 4:**
Crie uma matriz 3x3 e realize a multiplicação de todos os seus
elementos por um valor fornecido pelo usuário. Exiba a matriz
resultante


#include <stdio.h>

int main() {
    int matriz[3][3];
    int multiplicador;

    // Solicita ao usuário que insira o valor para multiplicação
    printf("Digite o valor para multiplicação: ");
    scanf("%d", &multiplicador);

    // Preenche a matriz e realiza a multiplicação simultaneamente
    printf("Matriz resultante:\n");
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            printf("%d ", (scanf("%d", &matriz[i][j]), matriz[i][j] * multiplicador));
        }
        printf("\n");
    }

    return 0;
}



**Exercícios sobre Structs em C:**


**Exercício 1:**
Crie uma `struct` chamada `Livro` que armazene as seguintes
informações sobre um livro: título, autor e ano de publicação.
Em seguida, escreva um programa que cria uma instância dessa
`struct` e imprime as informações do livro.


#include <stdio.h>

// Definição da estrutura Livro
struct Livro {
    char titulo[100];
    char autor[100];
    int anoPublicacao;
};

int main() {
    // Criação de uma instância da estrutura Livro
    struct Livro livro;

    // Atribuição de valores aos membros da estrutura Livro
    printf("Digite o título do livro: ");
    scanf("%99[^\n]", livro.titulo); // Lê a entrada do usuário até encontrar uma quebra de linha
    printf("Digite o autor do livro: ");
    scanf(" %99[^\n]", livro.autor); // Lê a entrada do usuário até encontrar uma quebra de linha
    printf("Digite o ano de publicacao do livro: ");
    scanf("%d", &livro.anoPublicacao);

    // Imprime as informações do livro
    printf("\nInformacoes do livro:\n");
    printf("Título: %s\n", livro.titulo);
    printf("Autor: %s\n", livro.autor);
    printf("Ano de Publicacao: %d\n", livro.anoPublicacao);

    return 0;
}



**Exercício 2:**
Crie uma `struct` chamada `Retângulo` que represente um
retângulo com membros para largura e altura. escreva um
programa que cria uma instância dessa `struct` e imprime as
informação: área do retângulo.


#include <stdio.h>

// Definição da estrutura Retângulo
struct Retangulo {
    float largura;
    float altura;
};

int main() {
    // Criação de uma instância da estrutura Retângulo
    struct Retangulo retangulo;

    // Atribuição de valores aos membros da estrutura Retângulo
    printf("Digite a largura do retangulo: ");
    scanf("%f", &retangulo.largura);
    printf("Digite a altura do retangulo: ");
    scanf("%f", &retangulo.altura);

    // Calcula a área do retângulo
    float area = retangulo.largura * retangulo.altura;

    // Imprime a área do retângulo
    printf("\nArea do retangulo: %.2f\n", area);

    return 0;
}



**Exercício 3:**
Crie uma `struct` chamada `Pessoa` para armazenar informações
sobre uma pessoa, incluindo nome, idade e altura. escreva um
programa que cria uma instância dessa `struct` e imprime as
informações: média de idade e altura.


#include <stdio.h>

// Definição da estrutura Pessoa
struct Pessoa {
    char nome[100];
    int idade;
    float altura;
};

int main() {
    // Criação de uma instância da estrutura Pessoa
    struct Pessoa pessoa1, pessoa2;

    // Atribuição de valores aos membros da estrutura Pessoa
    printf("Digite o nome da pessoa 1: ");
    scanf("%99[^\n]", pessoa1.nome);
    printf("Digite a idade da pessoa 1: ");
    scanf("%d", &pessoa1.idade);
    printf("Digite a altura da pessoa 1: ");
    scanf("%f", &pessoa1.altura);

    printf("Digite o nome da pessoa 2: ");
    scanf(" %99[^\n]", pessoa2.nome);
    printf("Digite a idade da pessoa 2: ");
    scanf("%d", &pessoa2.idade);
    printf("Digite a altura da pessoa 2: ");
    scanf("%f", &pessoa2.altura);

    // Calcula a média de idade e altura
    float media_idade = (pessoa1.idade + pessoa2.idade) / 2.0;
    float media_altura = (pessoa1.altura + pessoa2.altura) / 2.0;

    // Imprime a média de idade e altura
    printf("\nMedia de idade: %.2f\n", media_idade);
    printf("Media de altura: %.2f\n", media_altura);

    return 0;
}



**Exercício 4:**
Crie uma `struct` chamada `Estudante` que represente um
estudante com membros para nome, idade e uma array de notas.
escreva um programa que cria uma instância dessa `struct` e
imprime as informação: média das notas do estudante.


#include <stdio.h>

#define TAMANHO_NOTAS 5

// Definição da estrutura Estudante
struct Estudante {
    char nome[100];
    int idade;
    float notas[TAMANHO_NOTAS];
};

int main() {
    // Criação de uma instância da estrutura Estudante
    struct Estudante estudante;

    // Atribuição de valores aos membros da estrutura Estudante
    printf("Digite o nome do estudante: ");
    scanf("%99[^\n]", estudante.nome);
    printf("Digite a idade do estudante: ");
    scanf("%d", &estudante.idade);

    // Solicita ao usuário que insira as notas do estudante
    printf("Digite as %d notas do estudante:\n", TAMANHO_NOTAS);
    for (int i = 0; i < TAMANHO_NOTAS; i++) {
        printf("Nota %d: ", i + 1);
        scanf("%f", &estudante.notas[i]);
    }

    // Calcula a média das notas do estudante
    float soma_notas = 0;
    for (int i = 0; i < TAMANHO_NOTAS; i++) {
        soma_notas += estudante.notas[i];
    }
    float media_notas = soma_notas / TAMANHO_NOTAS;

    // Imprime a média das notas do estudante
    printf("\nMedia das notas do estudante: %.2f\n", media_notas);

    return 0;
}



Exercicios de revisao 07_05

Operadores de entrada e saída de dados Escreva um programa que leia dois
números inteiros e imprima a soma deles.

#include <stdio.h>

int main() {
    int num1, num2, soma;

    // Solicita ao usuário para inserir o primeiro número
    printf("Digite o primeiro número inteiro: ");
    scanf("%d", &num1);

    // Solicita ao usuário para inserir o segundo número
    printf("Digite o segundo número inteiro: ");
    scanf("%d", &num2);

    // Calcula a soma dos dois números
    soma = num1 + num2;

    // Imprime a soma
    printf("A soma de %d e %d é: %d\n", num1, num2, soma);

    return 0;
}


Variáveis e Operadores aritméticos Crie um programa que calcule a média aritmética
de três notas e determine se o aluno está aprovado (média >= 6).

#include <stdio.h>

int main() {
    float nota1, nota2, nota3, media;

    // Solicita ao usuário para inserir as três notas
    printf("Digite a primeira nota: ");
    scanf("%f", &nota1);

    printf("Digite a segunda nota: ");
    scanf("%f", &nota2);

    printf("Digite a terceira nota: ");
    scanf("%f", &nota3);

    // Calcula a média aritmética
    media = (nota1 + nota2 + nota3) / 3;

    // Verifica se a média é maior ou igual a 6
    if (media >= 6) {
        printf("Parabéns! Você está aprovado com média %.2f.\n", media);
    } else {
        printf("Infelizmente, sua média é %.2f e você está reprovado.\n", media);
    }

    return 0;
}


Estruturas de decisão e Operadores lógicos Escreva um programa que leia um
número e informe se ele é positivo, negativo ou zero.

#include <stdio.h>

int main() {
    int numero;

    // Solicita ao usuário para inserir um número
    printf("Digite um número: ");
    scanf("%d", &numero);

    // Verifica se o número é positivo, negativo ou zero
    if (numero > 0) {
        printf("O número %d é positivo.\n", numero);
    } else if (numero < 0) {
        printf("O número %d é negativo.\n", numero);
    } else {
        printf("O número é zero.\n");
    }

    return 0;
}


Switch case, While, do while, if, if else, For, Comando de controle de desvio e
Vetores Desenvolva um programa que utilize um menu para realizar operações em um
vetor de inteiros. As operações devem incluir inserção, remoção, exibição e busca de
elementos.

#include <stdio.h>

#define MAX_SIZE 100

int main() {
    int vetor[MAX_SIZE];
    int tamanho = 0;
    int escolha, elemento, i, posicao;

    do {
        printf("\nMenu:\n");
        printf("1. Inserir elemento\n");
        printf("2. Remover elemento\n");
        printf("3. Exibir vetor\n");
        printf("4. Buscar elemento\n");
        printf("5. Sair\n");
        printf("Escolha uma opção: ");
        scanf("%d", &escolha);

        switch (escolha) {
            case 1:
                if (tamanho < MAX_SIZE) {
                    printf("Digite o elemento a ser inserido: ");
                    scanf("%d", &vetor[tamanho]);
                    tamanho++;
                } else {
                    printf("O vetor está cheio.\n");
                }
                break;

            case 2:
                if (tamanho > 0) {
                    printf("Digite a posição do elemento a ser removido (de 1 a %d): ", tamanho);
                    scanf("%d", &posicao);
                    if (posicao >= 1 && posicao <= tamanho) {
                        for (i = posicao - 1; i < tamanho - 1; i++) {
                            vetor[i] = vetor[i + 1];
                        }
                        tamanho--;
                    } else {
                        printf("Posição inválida.\n");
                    }
                } else {
                    printf("O vetor está vazio.\n");
                }
                break;

            case 3:
                if (tamanho > 0) {
                    printf("Vetor: ");
                    for (i = 0; i < tamanho; i++) {
                        printf("%d ", vetor[i]);
                    }
                    printf("\n");
                } else {
                    printf("O vetor está vazio.\n");
                }
                break;

            case 4:
                if (tamanho > 0) {
                    printf("Digite o elemento a ser buscado: ");
                    scanf("%d", &elemento);
                    for (i = 0; i < tamanho; i++) {
                        if (vetor[i] == elemento) {
                            printf("Elemento encontrado na posição %d.\n", i + 1);
                            break;
                        }
                    }
                    if (i == tamanho) {
                        printf("Elemento não encontrado no vetor.\n");
                    }
                } else {
                    printf("O vetor está vazio.\n");
                }
                break;

            case 5:
                printf("Encerrando o programa.\n");
                break;

            default:
                printf("Opção inválida. Escolha novamente.\n");
                break;
        }
    } while (escolha != 5);

    return 0;
}


Matrizes (Arrays Bidimensionais) Crie um programa que leia uma matriz quadrada de
ordem n (onde n é lido pelo usuário) e calcule a soma dos elementos da diagonal
principal

#include <stdio.h>

#define MAX_SIZE 100

int main() {
    int matriz[MAX_SIZE][MAX_SIZE];
    int n, i, j, soma = 0;

    // Solicita ao usuário a ordem da matriz quadrada
    printf("Digite a ordem da matriz quadrada: ");
    scanf("%d", &n);

    // Solicita ao usuário para inserir os elementos da matriz
    printf("Digite os elementos da matriz:\n");
    for (i = 0; i < n; i++) {
        for (j = 0; j < n; j++) {
            printf("Elemento [%d][%d]: ", i, j);
            scanf("%d", &matriz[i][j]);
        }
    }

    // Calcula a soma dos elementos da diagonal principal
    for (i = 0; i < n; i++) {
        soma += matriz[i][i];
    }

    // Imprime a soma dos elementos da diagonal principal
    printf("A soma dos elementos da diagonal principal é: %d\n", soma);

    return 0;
}


Strings e Funções de Biblioteca Implemente um programa que leia uma string (nome)
e exiba o comprimento da string (número de caracteres).

#include <stdio.h>
#include <string.h>

#define MAX_LENGTH 100

int main() {
    char nome[MAX_LENGTH];

    // Solicita ao usuário que insira uma string
    printf("Digite uma string (nome): ");
    scanf("%s", nome);

    // Calcula o comprimento da string usando a função strlen da biblioteca string.h
    int comprimento = strlen(nome);

    // Exibe o comprimento da string
    printf("O comprimento da string '%s' é: %d\n", nome, comprimento);

    return 0;
}


Operadores de Entrada e Saída de Dados Escreva um programa que leia o nome e a
idade de uma pessoa e depois imprima esses dados.

#include <stdio.h>

int main() {
    char nome[100];
    int idade;

    // Solicita ao usuário que insira o nome
    printf("Digite o seu nome: ");
    fgets(nome, sizeof(nome), stdin);

    // Solicita ao usuário que insira a idade
    printf("Digite a sua idade: ");
    scanf("%d", &idade);

    // Imprime os dados lidos
    printf("Nome: %s", nome);
    printf("Idade: %d\n", idade);

    return 0;
}


Variáveis e Operadores Aritméticos Crie um programa que leia dois números e
imprima o resultado da multiplicação entre eles.

#include <stdio.h>

int main() {
    int num1, num2, resultado;

    // Solicita ao usuário que insira os dois números
    printf("Digite o primeiro número: ");
    scanf("%d", &num1);

    printf("Digite o segundo número: ");
    scanf("%d", &num2);

    // Calcula o resultado da multiplicação
    resultado = num1 * num2;

    // Imprime o resultado da multiplicação
    printf("O resultado da multiplicação é: %d\n", resultado);

    return 0;
}


Atribuições Aritméticas Escreva um programa que calcule o quadrado de um número
usando atribuição aritmética

#include <stdio.h>

int main() {
    int numero, quadrado;

    // Solicita ao usuário que insira o número
    printf("Digite um número: ");
    scanf("%d", &numero);

    // Calcula o quadrado do número usando atribuição aritmética
    quadrado = numero * numero;

    // Imprime o resultado
    printf("O quadrado de %d é: %d\n", numero, quadrado);

    return 0;
}


Estruturas de Decisão e Operadores Lógicos Implemente um programa que
determine se um ano é bissexto ou não

#include <stdio.h>

int main() {
    int ano;

    // Solicita ao usuário que insira o ano
    printf("Digite um ano: ");
    scanf("%d", &ano);

    // Verifica se o ano é bissexto
    if ((ano % 4 == 0 && ano % 100 != 0) || (ano % 400 == 0)) {
        printf("%d é um ano bissexto.\n", ano);
    } else {
        printf("%d não é um ano bissexto.\n", ano);
    }

    return 0;
}


Switch Case Desenvolva um programa que leia um número de 1 a 7 e imprima o dia
da semana correspondente, sendo 1 para Domingo

#include <stdio.h>

int main() {
    int numero;

    // Solicita ao usuário que insira um número de 1 a 7
    printf("Digite um número de 1 a 7: ");
    scanf("%d", &numero);

    // Verifica o número e imprime o dia da semana correspondente
    switch (numero) {
        case 1:
            printf("Domingo\n");
            break;
        case 2:
            printf("Segunda-feira\n");
            break;
        case 3:
            printf("Terça-feira\n");
            break;
        case 4:
            printf("Quarta-feira\n");
            break;
        case 5:
            printf("Quinta-feira\n");
            break;
        case 6:
            printf("Sexta-feira\n");
            break;
        case 7:
            printf("Sábado\n");
            break;
        default:
            printf("Número inválido! Por favor, insira um número de 1 a 7.\n");
            break;
    }

    return 0;
}


While Escreva um programa que imprima todos os números pares de 0 até 100

#include <stdio.h>

int main() {
    int numero = 0;

    // Imprime todos os números pares de 0 até 100
    while (numero <= 100) {
        printf("%d\n", numero);
        numero += 2; // Incrementa o número em 2 para obter o próximo número par
    }

    return 0;
}


Do While Implemente um programa que leia números do usuário até que ele digite 0, e
então imprima a soma de todos os números digitados.

#include <stdio.h>

int main() {
    int numero, soma = 0;

    // Loop para ler números do usuário
    do {
        // Solicita ao usuário que insira um número
        printf("Digite um número (digite 0 para encerrar): ");
        scanf("%d", &numero);
        
        // Adiciona o número à soma
        soma += numero;
    } while (numero != 0);

    // Imprime a soma dos números digitados
    printf("A soma dos números digitados é: %d\n", soma);

    return 0;
}


For Crie um programa que leia um número inteiro e imprima a tabuada desse número.

#include <stdio.h>

int main() {
    int numero, i;

    // Solicita ao usuário que insira um número
    printf("Digite um número inteiro: ");
    scanf("%d", &numero);

    // Imprime a tabuada do número fornecido
    printf("Tabuada do %d:\n", numero);
    for (i = 1; i <= 10; i++) {
        printf("%d x %d = %d\n", numero, i, numero * i);
    }

    return 0;
}


Comando de Controle de Desvio e Vetores Escreva um programa que preencha um
vetor com 10 números inteiros e depois imprima apenas os números positivos.


#include <stdio.h>

int main() {
    int vetor[10];
    int i;

    // Preenche o vetor com números fornecidos pelo usuário
    printf("Digite 10 números inteiros:\n");
    for (i = 0; i < 10; i++) {
        printf("Número %d: ", i + 1);
        scanf("%d", &vetor[i]);
    }

    // Imprime apenas os números positivos do vetor
    printf("Números positivos:\n");
    for (i = 0; i < 10; i++) {
        if (vetor[i] > 0) {
            printf("%d\n", vetor[i]);
        }
    }

    return 0;
}
