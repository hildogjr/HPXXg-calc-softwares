# HPXXg-softwares
HP 48/49/50g repository of the software that I created using the acknowledge of the Electrical Engineer course' subjects.

Here are the compiled files and the source code used in my personal HP.

Topics:

- Electrical Power Systems

- Robotic


# Description (how to use) in Portuguese language:

==================
Programas para SEP
==================

---------------------------
Programa de redução de Kron
---------------------------

Nome do programa: KRON
Nome do projeto: kron.hpprj
Tipo de programa: Script User-RPL
Dependências: não possui

Criado para a disciplina Sistema elétricos de potência 1.
O programa não verifica se a matriz de entrada é simétrica ou se a barra de redução está contida na matriz.

Entradas
 - Matriz de impedância
 - Número da barra a ser reduzida

Saída
 - Matriz com a linha/coluna escolhida reduzida pelo método de Kron

------------------------------------------------------------------------
Programa para adição de uma nova barra a uma matriz de impedância Zbus
------------------------------------------------------------------------

Nome do programa: BARRA (barraNova)
Nome do projeto: barraNova.hpprj
Tipo de programa: Script User-RPL
Dependências: KRON

Criado para a disciplina Sistemas elétricos de potência 1.

Possui interface gráfica e necessita da biblioteca anterior para executar a redução de Kron durante os cálculos.

Entradas (interface da forma gráfica)
 - Matriz de impedância original do sistema
 - Impedância nova conectada ao sistema
 - Ponto 1 de conexão da impedância ao sistema
 - Ponto 2 de conexão da impedância ao sistema

Saída
 - Matriz nova com a inclusão da impedância, sua dimesão vária em função da orginal e pontos de conexão
 
=======================
Programas para Robótica
=======================
 
------------------------------------------
Programa para a criação da matriz de Euler
------------------------------------------

Nome do programa: EULERM (EulerMatriz)
Nome do projeto: EulerMatriz.hpprj
Tipo de programa: Script User-RPL
Dependências: não possui

Cria a matriz de Euler para um sistema de 2 ou 3 coordenas.

Entradas
- 1 ângulo (para cálculo no plano) ou 1 vetor de 3 ângulos (para cálculo no espaço), o ângulo deve estar no sistema que a calculadora estiver no momento (graus, radianos ou grados)

Saída
- Matriz de transformação de Euler, lembrar que sua inversa é facilmente conseguida por sua transposição (é uma propriedade pois a matriz possui determinante igual a 1)

----------------------------------------------------------------------------
Programa para a criação da matriz de transformação de coordenadas homogeneas
----------------------------------------------------------------------------

Nome do programa: T.CH (coordHomogenias)
Nome do projeto: coordHomogeneas.hpprj
Tipo de programa: Script User-RPL
Dependências: EULERM

Cria a matriz de transformação de coordenadas homogeneas de duas e três dimensões.

Entradas (interface da forma gráfica)
- 2 coordenadas ou 3 coordenadas
- Ângulos de rotação (1 ou 3)
- Translação (2 ou 3 posições em coordenadas)

Saída
- Matriz de transformação de coordenadas homogeneas

------------------------------------------------------------------------------------------
Programa para inverter a matriz de transformada de coordenadas homogéneas por propriedades
------------------------------------------------------------------------------------------

Nome do programa: INV.CH (invMatrizCoordHomog)
Nome do projeto: invMatrizCoordHomog.hpprj
Tipo de programa: Script User-RPL
Dependências: não possui

Inverte a matriz de transformadas de coordenadas homogéneas sem inverter diretamente, apenas pela propriedade do determinante 1 da matriz de Euler e a translação inversa.

Entradas (interface da forma gráfica)
- Matriz de transformação de coordendas homogéneas, não importando a ordem

Saída
- Matriz invertida

------------------------------------------------------------------
Programa para conseguir a tranformada entre dois frames de um robô
------------------------------------------------------------------

Nome do programa: T.FR
Nome do projeto: transfFramesRobo.hpprj
Tipo de programa: Script User-RPL
Dependências: não possui

Consegue a matriz de transformação de coordenadas homogêneas para um sistema de três eixo usando os padrões de robótica já estabelecidos (Richard P. Paul, 1981).

Entrada (interface gráfica)
- Rotação no eixo Z (teta)
- Distâncias entre eixos x (d)
- Distância entre eixos z (l)
- Rotação no eixo x (alpha)

Saída
- Matriz de transformação
