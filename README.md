#include <stdio.h>
#include <locale.h>
#include <math.h>

int main(void)
{
    printf("\n============================================================\n");
    printf("\nCALCULADORA JUROS COMPOSTOS AO MES L.A.N.C.E.R software v1.0\n");
    printf("\n============================================================\n");

    setlocale(LC_ALL, "Portuguese");

    int op;
    int periodo;

    float juros, capital, taxa, montante;

    printf("Digite o capital:\n");
    scanf("%f", &capital);
    fflush(stdin);

    printf("Digite a taxa:\n");
    scanf("%f", &taxa);
    fflush(stdin);

    printf("Digite o tempo em meses:\n");
    scanf("%d", &periodo);
    fflush(stdin);

    juros = capital * ((pow(1 + taxa/100, periodo)) - 1);

    montante = capital * pow(1 + taxa/100, periodo);

do{

    printf("Aperte 1 para saber os juros totais, 2 para saber o montante e 0 para sair:\n");
    scanf("%d", &op);

switch(op){

    case 1:
    printf("Juros compostos totais: %.2f\n", juros);
    break;

    case 2:
    printf("Montante: %.2f\n", montante);
    break;

    default:
    printf("Finalizando...");
    break;
}
}while(op != 0);
}
