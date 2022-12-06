# Projeto-Automa-o-Estacao-tratamento-de-esgoto
O projeto consiste em automação de uma estação de tratamento de esgoto por meios de placas comerciais e controladas por arduino NANO, sensores como boias de niveis,
funcionamento automatico e manual.

Nesse projeto foi utilizado:
3 x placas plc para arduino NANO, 6 entradas digitais, 5 saidas digitais, comunicação serial, i2c e 2 entradas analogicas.
3 x arduinos NANO.
3 x boias de nivel eletronica.
1 x lcd 16x02 com comunicação i2c.
11 x push boton, normalmente aberto.
1 x chave 2 posições.

As placas de plc são conectadas entre si por meio dos pinos de comunicação i2c, ligação paralelo entre as 3 placas e lcd com i2c (sda,slc e gnd).
A comunicação entre as placas é realizado por meio do protocolo i2c, com ligação pararela nos pinos correspondentes sda e slc para realizar a comunicação, 
é importante gligar o gnd também das placas para evitar qualquer interferencia ou minimizar qualquer instabilidades durante a comunicação.

O funcionamento Manual é simples, é posicionado a chave seletora em manual, cada um dos 11 push boton acionam uma saida correspondente, o qual aciona um motor, bomba ou
valvula.

.
.
.

em construção.
