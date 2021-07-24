# Fonte de Tensão Variável (3V-12V | 100mA) criada para a matéria SSC0180 Eletrônica para Computação
Criação de uma fonte, ligada em 127V AC (60Hz), que produza, na saída, uma tensão ajustável entre 3V-12V, com uma corrente contínua de 100mA a 12V.

# Diagrama da Fonte
<img src="images/circuito_principal.png">

### Gráficos da Simulação
<img src="images/graphs.png">

### Link para o Circuito
https://tinyurl.com/yhocpyjx

### Componentes do Circuito
**Transformador:** A tomada (entrada da fonte) fornece um RMS de 127V (pico em 180). Como nossa fonte deve fornecer uma tensão máxima de 12V. O transfomador reduzirá a voltagem original para ~18V.

**Ponte de diodos (retificação):** A ponte de diodos faz com que a voltagem seja sempre positiva. Assim, ela irá variar de 18V (pico) a 0V, ao invés de variar de 18V a -18V. *Observação: é preciso levar em conta que a cada diodo, do modelo usado, tem um drop voltage de ~0.6V. Com isso, após passar pela ponte a voltagem fica com um pico de ~16V.*

**Capacitor (filtragem):** O capacitor tem a função de diminuir a variação na voltagem. O que antes variava de 16V a 0V, agora será mantido sempre acima de ~13V. <!-- Como? --> 

**Diodo Zenner (regulador):** O diodo zenner consegue manter uma uma tensão X sobre ele, contanto que a tensão sobre ele seja >= X. Nesse caso, escolhemos um diodo de 13V, o que implica que, como nossa voltagem é sempre >= ~13V, graças ao capacitor, o Zenner manterá sempre os 13V sobre ele.

**Transistor:** O transistor vem para solucionar um grande impasse: se tivermos um resistor muito pequeno antes do diodo zenner, podemos queimá-lo. Se aumentarmos esse resistor, ficamos com uma tensão baixa demais. Portanto, adicionamos o transistor, que fornece um caminho alternativo para a corrente, enquanto a voltagem ainda é fornecida pelo Zenner. *Observação: o transistor tem um drop voltage de ~<!-- ???? -->.*

# Tabela de Componentes
| QUANTIDADE | COMPONENTES                      | ESPECIFICAÇÕES                                                                                         | VALOR   |
|------------|----------------------------------|--------------------------------------------------------------------------------------------------------|---------|
|            |                                  |                                                                                                        |         |
| 1          | Transformador                    | 12V e 200mA                                                                                            | R$26,99 |
| 4          | Diodo                            | Diodo retificador 1N4007 Corrente: 1A (máx 30A) Tensão Reversa: 1000V Encapsulamento: DO41 Drop ~ 0.6V | R$0,09  |
| 1          | Ponte Retificadora (Alternativa) | Datasheet                                                                                              | R$3,67  |
| 1          | Capacitor                        | Capacitor Eletrolitico 560uF/35V 105º 10x20mm Jamicon                                                  | R$33,00 |
| 1          | Resistor 820Ω                    | Resistor 820R 5% (1/4W)                                                                                | R$0,05  |
| 1          | Resistor 2.2kΩ                   | Resistor 2K2 5% (1/4W)                                                                                 | R$0,05  |
| 1          | Diodo Zener                      | Diodo Zener 1N4743 [13V / 1W]                                                                          | R$0,19  |
| 1          | Potenciômetro                    | Resistência: 5K (5000Ω) Potência: 0,2W Tipo: Linear Rotativo Tensão Máxima: 200V AC                    | R$1,99  |
| 1          | Transistor NPN                   | Transistor NPN - BC548 Tensão Coletor Emissor = 30V Tensão Coletor Base = 30V Tensão Emissor Base = 5V | R$0,17  |

# Esquemático e PCB no Eagle
<!-- Adicionar Imagem -->

# Cálculos dos Valores
<!-- Adicionar Cálculos-->

# Vídeo explicativo
<!-- Adiciona Vídeo -->
