# Exemplos em linguagem C++

##Exemplo1 -> Média de 8 números
```cpp
#include <iostream>

int main()
{
    int N = 8;
    int vetor[N];
    
    vetor[0] = 3;
    vetor[1] = 5;
    vetor[2] = 4;
    vetor[3] = 1;
    vetor[4] = 7;
    vetor[5] = 7;
    vetor[6] = 8;
    vetor[7] = 5;
    
    int soma = 0;
    
    for (int i=0 ; i < N ; i++){
        soma += vetor[i];
    }
    
    std::cout << "Media = " << soma / N << std::endl;

    return 0;
}
```

##Exemplo2 -> Condição menor que 
```cpp
#include <iostream>

int main() {
    int a = 10; 
    int b = 5;
    int resultado;

    if(a < b){
        resultado = a * b;
    }
    else{
        resultado = a - b;
    }
    
    std::cout << "A soma é: " << resultado << std::endl;
    
    return 0;
}


