# Processador-MIPS-18-bits
Desenvolvimento de um processador MIPS de 18-bits

## 💻 Sobre o projeto
Esse projeto consiste em desenvolver e entender o funcionamento de um processador MIPS de 18-bits utilizando o simulador Logisim Evolution


## 🛠 Visão Geral
O processador consiste em 6 blocos sendo eles PC, Memoria de Instrução, UC, Registradores, ULA e Memoria de Dados. Cada bloco possui uma função especifica e essencial para o funcionamento correto do processador.
><img width="1396" height="676" alt="Visão Geral" src="https://github.com/user-attachments/assets/afc28799-e9d9-4b3f-a2cf-131643c8f1d7" />

´´´

## 🔍 Explicação dos blocos
>**PC (Program Counter):** É utilizado para trocar o endereço da instrução, ou seja, depois do processador executar a devida operação em um determinado endereço essa unidade se incrementa alterando para o próximo endereço de operação, que por sua vez ficam salvos na memória de instrução.
><img width="398" height="272" alt="PC" src="https://github.com/user-attachments/assets/becbb422-f027-45b3-b5ff-c29339d35903" />

´´´

>**Memória de Instrução:** Recebe o endereço que terá que acessar através do PC, uma vez que nessa memória já se encontra todas as possíveis operações do processador em assembly transformados em binário, depois de acessar o endereço de instrução, essa memória passa as informações de instrução adiante para as devidas partes do sistema para pôr fim executar a operação desejada.
><img width="607" height="542" alt="Memoria de Intrucao" src="https://github.com/user-attachments/assets/cad57a18-515e-4dd2-b550-e5da736e3776" />

´´´

>**UC (Unidade de Controle):** É responsável por “traduzir” a instrução que foi recebida pela memória de instrução para que os dados sejam direcionados e processados conforme a instrução.
><img width="311" height="254" alt="UC (Unidade de Controle)" src="https://github.com/user-attachments/assets/57d725aa-9669-4b63-b9f6-7fdf6bc2a4e5" />
>
>*Por dentro do bloco UC temos o seguinte:*
><img width="533" height="762" alt="Bloco de UC" src="https://github.com/user-attachments/assets/96e30a34-45ce-4d87-8ae5-50d326e572b2" />

´´´

>**Registradores:** Eles armazenam os valores que serão processados, recebendo instruções que indicam quais registradores serão usados e para o que cada registrador será usado, instruções como armazenar um novo valor, exibir o valor que estiver no registrador ou apagar esse valor e posteriormente enviando esses valores para a ULA.
><img width="322" height="355" alt="Registrador" src="https://github.com/user-attachments/assets/a5dbb55d-67db-4885-a0cc-4e5cb57c4792" />
>
>*Por dentro do bloco Registradores temos o seguinte:*
><img width="1248" height="926" alt="Bloco de Registradores" src="https://github.com/user-attachments/assets/6f0e270a-95d5-4af0-a005-38c906b5876e" />

´´´

>**ULA (Unidade Logica Aritmetica):** É onde os dados serão devidamente processados, para isso ela recebe informações dos registradores bem como também as devidas instruções que deverão ser executados.
><img width="491" height="278" alt="ULA (Unidade Logica Aritmetica)" src="https://github.com/user-attachments/assets/93dbf9c6-fe11-40d9-81d4-988424fb75f4" />
>
>*Por dentro do bloco ULA temos o seguinte:*
><img width="1176" height="755" alt="Bloco de ULA" src="https://github.com/user-attachments/assets/a146d6ae-c215-4108-b9d2-bf03bdcf015b" />
>
>*Por dentro do bloco Controle ULA temos o seguinte:*
><img width="321" height="169" alt="Bloco de Controle ULA" src="https://github.com/user-attachments/assets/99a2559e-afa9-4ab0-ba28-9418964c40fe" />

´´´

>**Memória de dados:** É para onde os valores processados são enviados. Para isso recebe os endereços de memória que serão acessados e recebe instruções que indicam se naquela posição os valores serão armazenados ou lidos, podendo ser usado para enviar os valores direto para os registradores se essa for a operação desejada.
><img width="489" height="249" alt="Memoria de Dados" src="https://github.com/user-attachments/assets/9b84459e-9a40-46d8-a563-09dede94a2ed" />

´´´

## 🧩 Tipos
**O nosso processador funciona com 18 bits e para isso os bits foram separados da seguinte maneira**

>**Tipo R**
><img width="342" height="56" alt="Tipo R" src="https://github.com/user-attachments/assets/b9712079-f874-4325-a8c3-53a5f8ef67cf" />

´´´

>**Tipo I**
><img width="343" height="54" alt="Tipo I" src="https://github.com/user-attachments/assets/55578411-f8e6-4b66-9ecc-3a4835d40910" />

´´´

>**Tipo J**
><img width="343" height="52" alt="Tipo J" src="https://github.com/user-attachments/assets/18d33529-7d9a-4164-a036-3a9641fda639" />


## 📖 Operações
Abaixo estão as tabelas contendo os comandos e suas respectivas operações:

|Instrução| opcode/funct | Descrição| Formato|
| :---: | :---: | :---: | :---: |
|Soma |000/000| rd = rs + rt| R|
|Subtração| 000/001| rd = rs - rt| R|
|Multiplicação| 000/010| rd = rs * rt| R|
|Divisão| 000/011| rd = rs / rt| R|
|Negação| 000/100| rd = ~rs| R|
|Menor que| 000/101| se rs < rt, rd = 1| R|
|Deslocamento à esquerda| 000/110| rd = rs << N| R|
|Deslocamento à direita| 000/111| rd = rs >> N| R|
|Carregar dados da memoria| 001/xxx| rt = Memoria[rs + N]| I|
|Operações Salvar dados da memoria| 010/xxx |Memoria[rs + N] = rt| I|
|Desvio condicional| 011/xxx| se rs == rt, PC = ENDR| I|
|Soma imediata| 100/xxx| rt = rs + N| I|
|Desvio incondicional| 111/xxx| PC = ENDR| J|

´´´

| opcode | Operações | ULAOp |
| :---: | :---: | :---: |
| 000 | RegDst / RegWrite / MemToReg | 10 |
| 001 | RegWrite / ULASrc / MemRead | 00 |
| 010 | ULASrc / MemWrite | 00 |
| 011 | Branch | 01 |
| 100 | RegWrite / ULASrc / MemToReg | 11 |
| 101 | --- | 00 |
| 110 | --- | 00 |
| 111 | Jump | 00 |

´´´

|ULAOp|UlaCtrl|
| :---: | :---: |
| 00 | 000 |
| 01 | 101 |
| 10 | funct |
| 11 | 00 |

´´´

| Funct | Operações |
| :---: | :---: |
| 000 | Soma (A + B) |
| 001 |  Subtração (A - B) |
| 010 | Multiplicação (A * B) |
| 011 |  Divisão (A / B) |
| 100 | Negação (~A) |
| 101 | Menor que (A < B) |
| 110 | Deslocamento esquerda (<- A) |
| 111 |  Deslocamento direita (-> A) |

´´´

## 🚀 Como usar
1. Faça o download do Logisim Evolution (https://github.com/logisim-evolution/logisim-evolution)
2. Faça o clone ou download desse repositorio
3. Abra o arquivo Processador.circ no Logisim Evolution
4. Carregue a memoria ROM com as instruções que desejar em hexadecimal
5. Habilite a simulação e os pulsos de clock
