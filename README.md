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

No funcionamento Automatico as placas realizam uma comunicação entre si e executam uma rotina de funcionamento que é na seguinte sequencia:

 1° - aciona agitador box1, desliga agitador box2, executa essa rotina por 1 hora e 20 minutos.
 2° - aciona agitador box1, aciona valvula de descarte do conteudo do box2 até  a boia de nivel minimo ser acionada, que fecha a valvula de descarte, executa essa rotina por 1 hora e 20 minutos .
 3° - aciona agitador box1, verifica o nivel do reservatorio de entrada, se estiver cheio abastece box2 até acionar o nivel maximo ou se esvaziar o reservatorio de entrada, desliga as bombas até encher o reservatorio de entrada e completar o nivel maximo do box2, executa essa rotina por 1 hora e 20 minutos ou completar o box2.
 4° - desliga o agitador box1, aciona agitador box2, executa essa rotina por 1 hora e 20 minutos.
 5° - aciona agitador box2, aciona valvula de descarte do conteudo do box1 até  a boia de nivel minimo ser acionada, que fecha a valvula de descarte, executa essa rotina por 1 hora e 20 minutos .
 6° - aciona agitador box2, verifica o nivel do reservatorio de entrada, se estiver cheio abastece box1 até acionar o nivel maximo ou se esvaziar o reservatorio de entrada, desliga as bombas até encher o reservatorio de entrada e completar o nivel maximo do box1, executa essa rotina por 1 hora e 20 minutos ou completar o box1.
 7° - reinicia todo o processo.
 *no processo Automatico é informado no lcd os estados de execução de cada box.
