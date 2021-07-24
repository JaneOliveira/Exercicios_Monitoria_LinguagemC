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
        printf("\nO novo salario será de = %.2f ", salario * 1.37);

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

        novoSalario = (((salario * 1.1) * 1.1) * 1.1);

        printf("\nO novo salario será de = %.2f ", novoSalario);

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

        minutos = segundos / 60;
        segundos = segundos % 60;
        horas = minutos / 60;
        minutos = minutos % 60;
        dias = horas / 24;
        horas = horas % 24;

        printf("  %d dias,  %d horas, %d minutos e %d segundos", dias, horas, minutos, segundos);

        return 0;
    }

---------------------------------------------------------------------------------------------------------------------

### Construa um programa que receba o salário-base de um funcionário, calcule e mostre o seu salário a receber, sabendo-se que esse funcionário tem gratificação de R$50,00 e paga imposto de 10% sobre o salário-base.

Resolução: 

    #include <stdio.h>

    int main() {
    
        float salarioBase;
        float salarioFinal;

        printf("d\nDigite o salario base:");
        scanf("%f", & salarioBase);

        salarioFinal = (salarioBase * 0.9) + 50;

        printf("\n\nO novo salario = %.2f \n\n", salarioFinal);

        return 0;
    }


---------------------------------------------------------------------------------------------------------------------

### Faça um programa que receba o ano de nascimento de uma pessoa e o ano atual, calcule e mostre: 
### • A idade dessa pessoa; 
### • Quantos anos ela terá em 2028. 

Resolução:

    #include <stdio.h>

    int main() {

        int anoNascimento;
        int anoAtual;

        printf("\nDigite o ano de nascimento: ");
        scanf("%d", & anoNascimento);
        printf("\nDigite o ano atual: ");
        scanf("%d", & anoAtual);

        printf("\n\nA idade = %d \n\n", anoAtual - anoNascimento);

        return 0;
    }
    
    ---------------------------------------------------------------------------------------------------------------------

### Faça um programa que receba o valor de um depósito e o valor da taxa de juros, calcule e mostre o valor do rendimento e o valor total depois do rendimento.

Resolução:

    #include <stdio.h>

    int main() {

        float deposito;
        float taxa;
        float redimento;
        float totalPosRendimento;

        printf("\nDigite o valor do deposito: ");
        scanf("%f", & deposito);
        printf("\nDigite o valor da taxa: ");
        scanf("%f", & taxa);

        redimento = deposito * taxa;
        totalPosRendimento = deposito + redimento;

        printf("\n\nO redimento = %.2f \n", redimento);
        printf("\nO total do valor pos rendimento = %.2f \n\n", totalPosRendimento);

        return 0;
    }

    ---------------------------------------------------------------------------------------------------------------------
    
### Cada degrau de uma escada tem uma altura X. Faça um programa que receba  essa altura e a altura que o usuário deseja alcançar subindo a escada. Calcule e mostre quantos degraus o usuário deverá subir para atingir seu objetivo. 

Resolução:

    #include <stdio.h>

    int main() {

        int alturaEscada;
        int degrau;
        int qtdeDegraus;

        printf("\ndigite os dados em centimetros\n\n");
        printf("\nDigite a altura que deseja subir da escada: ");
        scanf("%d",& alturaEscada);

        printf("\ndigite a altura do degrau: ");
        scanf("%d",& degrau);

        qtdeDegraus = (alturaEscada/degrau) + (alturaEscada % degrau != 0);
        printf("\nquantidade de degraus que precisa subir: %d \n\n", qtdeDegraus);


        return 0;
    }
    
   
   ---------------------------------------------------------------------------------------------------------------------
   
   
### Faça um programa que receba o peso e a altura de uma pessoa e calcule o índice de massa corpórea. Ele mede a relação entre peso e altura (peso em Kg, dividido pelo quadrado da altura em metros). 

Resolução:

    #include <stdio.h>
    #include <math.h>

    int main() {

        float peso;
        float altura;
        float imc;

        printf("\ndigite o peso da pessoa em Kg : ");
        scanf("%f",& peso);

        printf("\ndigite a altura da pessoa em metros: ");
        scanf("%f",& altura);

        imc = peso / pow(altura,2);

        printf("\n\nO imc da pessoa = %.2f \n\n", imc);


        return 0;
    }

   ---------------------------------------------------------------------------------------------------------------------
   
### Construa um programa que solicite a entrada de dois números inteiros e calcule e mostre a potência do primeiro número pelo segundo (X elevado a Y). 
Obs: Existe uma biblioteca em C chamada “math.h”, esta biblioteca disponibiliza um conjunto de funções matemáticas como por exemplo a função pow(). Esta função 
recebe dois valores do tipo float e retorna o resultado da potência entre eles, também do tipo float.

    #include <stdio.h>
    #include <math.h>

    int main() {

        int x, y;

        printf("\ndigite um numero inteiro para X: ");
        scanf("%d",& x);

        printf("\ndigite um numero inteiro para Y: ");
        scanf("%d",& y);

        printf("\n\nX elevado a Y = %.2f \n\n", pow(x,y));

        return 0;
    }


   ---------------------------------------------------------------------------------------------------------------------
   

###  Um hotel deseja fazer uma promoção especial de final de semana, concedendo um desconto de 25% na diária. Sendo informados, através do teclado, o número de apartamentos do hotel e o valor da diária por apartamento para o final de semana completo, elabore um programa para calcular: 
### • Valor promocional da diária; 
### • Valor total a ser arrecadado caso a ocupação neste final de semana atinja 100%; 
### • Valor total a ser arrecadado caso a ocupação neste final de semana atinja 70%; 
### • Valor que o hotel deixará de arrecadar em virtude da promoção, caso a ocupação atinja 100%. 

    #include <stdio.h>
    int main(){

        int nApto;
        float valorDiaria;
        float valorPromDiaria;
        float valorTotalArrecado100;
        float valorTotalArrecado70;
        float valorDeixaraRecebe;

        printf("\nDigite o numero de apartamentos do hotel:");
        scanf("%d",& nApto);

        printf("\nDigite o valor da diaria:");
        scanf("%f",& valorDiaria);

        valorPromDiaria = valorDiaria * 0.75;
        valorTotalArrecado100 = (valorPromDiaria*nApto)*2;
        valorTotalArrecado70 = (valorPromDiaria*(nApto*0.7))*2;
        valorDeixaraRecebe = ((valorDiaria*nApto)*2) - (valorTotalArrecado100);

        printf("\nO valor promocional da diaria = %.2f",valorPromDiaria);
        printf("\nValor total arrecado com 100 lotacao = %.2f",valorTotalArrecado100);
        printf("\nValor total arrecado com 70 lotacao = %.2f",valorTotalArrecado70);
        printf("\nValor que deixara de receber devido ao desconto = %.2f \n\n",valorDeixaraRecebe);
        return 0;
    }
    
    
   ---------------------------------------------------------------------------------------------------------------------
   
   
    
