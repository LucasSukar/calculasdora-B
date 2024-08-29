//Autor: Lucas Ferreira Sukar Wanderley (lfsw)
//https://github.com/LucasSukar/calculasdora-B.git
//Criaão: 21 de Agosto 2024
//commit 1: q1 A - 21/08/2024 10:30
//commit 2: q2 - 22/08/2024 10:25
//commit 3: q1 letras B e C - 22/08/2024 15:24
//commit 4: q1 letra D e correcao da funcao binario do q1 A- 22/08/2024 16:15
//commit 5: correcao de erro de modulo de 2 - 22/08/2024 16:50
//commit 6: q3 - 29/08/2024 08:43


#include <stdio.h>
#include <string.h>

void binario(int resultado){
  int resto, x, array[100], i=0,z=resultado;

  while(resultado != 0){
    resto = resultado%2;
    x = resultado/2;
    array[i] = resto;
    if(resto != 0){
      resultado = resultado-x-resto;
    } else{
      resultado = resultado-x;
    }
    i++;
  }
  if (z < 4) {
    for (int j = 0; j < 4 - z; j++) {
        printf("0");
    }
  }
  for(int j=i;j>0;j--){
    printf("%d",array[j-1]);
  }
}

void complementoa2(int resultado){
  int sinal = resultado;
  int resto, x, i=0;
  int array[16] = {0}; 
  while(resultado != 0){
    resto = resultado%2;
    x = resultado/2;
    array[i] = resto;
    if(resto != 0){
      resultado = resultado-x-resto;
    } else{
      resultado = resultado-x;
    }
    i++;
  }
  int array2[16];
  for(int j=0;j<i;j++){
    if(array[j] == 0){
      array2[j] = 1;
    }
    else{
      array2[j] = 0;
    }
  }  
  for(int j=0;j<i;j++){
    if (array2[j] == 0) {
      array2[j] = 1;
      break;
    } else {
      array2[j] = 0;
    }
  }
  if(sinal<0){
    array2[15] = 1;
  }
  for(int j=15;j>=0;j--){
    printf("%d",array2[j]);
  }
}

void base8(int resultado){
  int resto, x, array[100], i=0;
  while(resultado != 0){
    resto = resultado % 8;
    resultado = resultado / 8;
    array[i] = resto;
    i++;
  }  
  for(int j=i;j>0;j--){
    printf("%d",array[j-1]);
  }
}

void base16(int resultado){
  int resto, x, array[100], i=0;
  while(resultado != 0){
    resto = resultado % 16;
    resultado = resultado / 16;
    array[i] = resto;
    i++;
  }  
  for(int j=i;j>0;j--){
    printf("%d",array[j-1]);
  }
}

void bcd(int resultado){
  int resto, x, array[100],i=0;
  while(resultado != 0){
    resto = resultado % 10;
    resultado = resultado / 10;
    array[i] = resto;
    i++;
  } 
  for(int j = i-1; j>=0; j--){
    binario(array[j]);
    printf(" ");
  }
}

void numprabinario(unsigned long long value, int size) {
  for (int i = size - 1; i >= 0; i--) {
      printf("%llu", (value >> i) & 1);
  }
}  
void resultadofloat(float num) {
  unsigned int bits;
  memcpy(&bits, &num, sizeof(bits));
  int sinal = (bits >> 31) & 1;
  int exponent = (bits >> 23) & 0xFF;
  unsigned int fracao = bits & 0x7FFFFF;
  printf("Sinal: %d\n", sinal);
  printf("Expoente: %d (0x%X) em binário: ", exponent - 127, exponent);
  numprabinario(exponent, 8);
  printf("\nFração em binário: ");
  numprabinario(fracao, 23);
  printf("\n\n");
}
void resultadodouble(double num) {
  unsigned long long bits;
  memcpy(&bits, &num, sizeof(bits));
  int sign = (bits >> 63) & 1;
  int exponent = (bits >> 52) & 0x7FF;
  unsigned long long fraction = bits & 0xFFFFFFFFFFFFF;
  printf("Sinal: %d\n", sign);
  printf("Expoente: %d (0x%X) em binário: ", exponent - 1023, exponent);
  numprabinario(exponent, 11);
  printf("\nFração em binário: ");
  numprabinario(fraction, 52);
  printf("\n\n");
}

int main(void) {
  int x;
  printf("digite 1 para converter um decimal;\n");
  printf("digite 2 para converter de decimal para base com sinal com 16 bits;\n");
  printf("digite 3 para converter real em decimal para float e double,;\n");

  scanf("%d", &x);
  if(x==1){
    int escolha;
    printf("Digite 1 para binario; \n");
    printf("Digite 2 para octa; \n");
    printf("Digite 3 para hexa; \n");
    printf("Digite 4 para BCD; \n");
    scanf("%d", &escolha);

    int nDecimal;
    printf("Digite o numero para ser convertido; ");
    scanf("%d", &nDecimal);

    if(escolha == 1){
      binario(nDecimal);
    } else if(escolha == 2){
      base8(nDecimal);
    } else if(escolha == 3){
      base16(nDecimal);
    } else if(escolha == 4){
      bcd(nDecimal);
    }
  } else if(x==2){
    int nDecimal;
    printf("Digite o numero para ser convertido; ");
    scanf("%d", &nDecimal);
    complementoa2(nDecimal);
  } else if(x==3){
      float nreal;
      printf("Digite o numero para ser convertido; ");
      scanf("%f", &nreal);
      printf("\n");
      resultadofloat(nreal);
      resultadodouble(nreal);
  }
}
