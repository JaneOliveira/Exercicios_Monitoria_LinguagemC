# Exercicios de Monitoria em linguagem C
### Exercicios iniciais da disciplina Linguagem e Programação, do curso ciência e tecnologia da UFVJM, exercicios elaborados em linguagem C.

##### Lista 1 - Introduzindo o aluno a linguagem C

obs. serão adicionado mais exercicios e listas no decorrer do andamento da disciplina.

### lembre-se a várias maneiras de resolver um problema, logo, não se preucupe com codigos difentes, o importante é a logica está certa.

#### Resolução: Jane T. S. OLiveira
---------------------------------------------------------------------------------------------------------------------

### Elabore um programa em linguagem C que leia o tamanho do lado de um quadrado e informe a área e o perímetro do quadrado. (Perímetro = 4 * L; área = L ^ 2).

Resolução:

    #include <stdio.h>

    #include <math.h>

    int main() {

        float ladoQuadrado;
        float perimetro, area;

        printf("Digite o comprimento do lado de uma quadrado: ");
        scanf("%f",&ladoQuadrado);

        perimetro = 4*ladoQuadrado;
        area = pow(ladoQuadrado, 2); // outra forma de fazer a conta ->  ladoQuadrado * ladoQuadrado;

        printf("\nO perimetro = %.2f",perimetro);
        printf("\nA area = %2.f",area);

        return 0;
    }

---------------------------------------------------------------------------------------------------------------------

### Escreva um programa que solicite ao usuário que entre com um valor qualquer em Reais. O algoritmo deverá converter este valor em Reais para Dólar Americano. O valor do Dólar Americano deverá ter o preço fixo de R$2,32.

Resolução:

#include <stdio.h>

int main() {
    
    float valorReais;
    const float valorDolar = 2.32;
    
    printf("\nDigite o valor em reais: ");
    scanf("%f",& valorReais);
    printf("\nO valor convertido = %.2f",valorReais*valorDolar);

    return 0;
}


---------------------------------------------------------------------------------------------------------------------

### Reescreva o exercício anterior, alterando o programa para que a cotação do dólar passe a ser informada pelo usuário, de acordo com a cotação da data em que o programa está sendo executado. 

Resolução:

#include <stdio.h>

int main() {
    
    float valorReais;
    float valorDolar;
    
    printf("\nDigite o valor em reais: ");
    scanf("%f",& valorReais);
    
    printf("\nDigite a cotação atual do dolar: ");
    scanf("%f",& valorDolar);
    
    printf("\nO valor convertido = %.2f",valorReais*valorDolar);

    return 0;
}


---------------------------------------------------------------------------------------------------------------------

### Faça um programa que receba três notas e seus respectivos pesos, calcule e mostre a média ponderada dessas notas. Fórmula do cálculo da média ponderada: 

### Xp = (x1 * w1 + x2  * w2 + x3 * w3 + ... + xn * wn)/(w1 + w2 + w3 + ... + wn)   onde x é nota e w o peso.

Resolução: 

#include <stdio.h>

int main() {
    
    float x1, x2, x3;
    float w1, w2, w3;
    float resul;
    
    printf("\nDigite a nota 1 e seu respectivo peso: ");
    scanf("%f %f",& x1, & w1);
    printf("\nDigite a nota 2 e seu respectivo peso: ");
    scanf("%f %f",& x2, & w2);
    
    printf("\nDigite a nota 3 e seu respectivo peso: ");
    scanf("%f %f",& x3, & w3);
    
    resul = ((x1*w1)+(x2*w2)+(x3*w3))/(w1 + w2 + w3);
    
    printf("\nA media ponderada = %.2f", resul);

    return 0;
}

---------------------------------------------------------------------------------------------------------------------

### Faça um programa que apresente, para um salário informado pelo usuário, um novo salário com aumento de 37%.

Resolução:

#include <stdio.h>

int main() {
    
    float salario;
    
    printf("\nDigite o salario: ");
    scanf("%f",& salario);
    printf("\nO novo salario será de = %.2f ", salario*1.37);

    return 0;
}

---------------------------------------------------------------------------------------------------------------------

### Altere o programa anterior para que um aumento de 10% seja aplicado três vezes consecutivas sobre o salário digitado. (Lembre-se: aplicar um aumento de 10% por três vezes seguidas é diferente de aplicar um aumento de 30%). 

Resolução:

#include <stdio.h>

int main() {
    
    float salario;
    float novoSalario;
    
    printf("\nDigite o salario: ");
    scanf("%f",& salario);
    
    novoSalario = (((salario*1.1)*1.1)*1.1);
    
    printf("\nO novo salario será de = %.2f ",novoSalario);

    return 0;
}

---------------------------------------------------------------------------------------------------------------------


###  Faça um programa que receba o valor do salário do funcionário e também o valor do percentual a ser aplicado como aumento no salário digitado. Calcule e mostre o novo valor do salário. 

Resolução:

#include <stdio.h>

int main() {
    
    float salario, salarioNovo;
    float percentualAumSalario;
    
    printf("\nDigite o salario: ");
    scanf("%f",& salario);
    
    printf("\nDigite o percentual de aumento do salario: ");
    scanf("%f",& percentualAumSalario);
    
    salarioNovo = salario * ( 1 + percentualAumSalario);    /// outra forma de fazer a conta ->  salario + (salario * percentualAumSalario);
    
    printf("\nO novo salario será de = %.2f ",salarioNovo);

    return 0;
}


---------------------------------------------------------------------------------------------------------------------

### Elabore um programa que leia do teclado uma quantidade de segundos e transforme este tempo em dias, horas e minutos. 

Resolução:

#include <stdio.h>

int main() { 
    
    int segundos;
    int minutos;
    int horas;
    int dias;

    printf("\nDigite um valor de segundos: ");
    scanf("%d",& segundos);

    minutos = segundos/60;
    segundos = segundos % 60;
    horas = minutos /60;
    minutos = minutos%60;
    dias = horas/24;
    horas = horas%24;

    printf("  %d dias,  %d horas, %d minutos e %d segundos", dias, horas, minutos, segundos);

    return 0;
}

---------------------------------------------------------------------------------------------------------------------

### Construa um programa que receba o salário-base de um funcionário, calcule e mostre o seu salário a receber, sabendo-se que esse funcionário tem gratificação de R$50,00 e paga imposto de 10% sobre o salário-base.
