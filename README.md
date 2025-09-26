# HCPN_TRAFFIC_CONTROL
A modelagem de um sistema de controle de tráfego em uma interseção urbana com prioridade para veículos de transporte público (como ônibus ou metrôs de superfície). 

<p align="center">
  <img src="https://github.com/Danilo0liveira/HCPN_TRAFFIC_CONTROL/blob/main/figures/visao_geral.jpg?raw=true" alt="Logo" width="800"/>
</p>

<p align="center">Figura 01: Representação Do Interseção</p>


# Modelagem do Sistema


Na interseção tem-se a representação de quatro filas e quatro semáforos. Esses são representados nas Figuras 02 e 04, respectivamente. A fila consiste na geração de veículos (carros e onibus) através de uma distribuição exponencial. Os carros e ônibus seguem uma distribuição baseado em um valor médio distinto, indicando as diferença, na média da quantidade de carros e ônibus no cruzamento. 

<p align="center">
  <img src="https://github.com/Danilo0liveira/HCPN_TRAFFIC_CONTROL/blob/main/figures/fila_semaforo.png?raw=true" alt="Logo" width="800"/>
</p>

<p align="center">Figura 02: Representação Da fila</p>


Na Figura 02, os veículos chegando, ativados pela transição NOVO_ONIBUS/NOVO_CARRO, aguardam em uma place que representa as duas faixas FILA_ONI/FILA_CARRO. O ônibus ativa um sistema de prioridade, na page da fila, levando a ficha para um place de prioridade que é uma saída para a interação entre FILA e SEMAFORO, mostrada na Figura 03.

<p align="center">
  <img src="https://github.com/Danilo0liveira/HCPN_TRAFFIC_CONTROL/blob/main/figures/interacao_prioridade.png?raw=true" alt="Logo" width="400"/>
</p>

<p align="center">Figura 03: Representação Da fila</p>

Após estar na fila, Figura 02, caso o sinal esteja verde, a transição PARTIDA_CARRO/PARTIDA_ONIBUS levam as fichas para os places de SAIDA_ONIBUS/SAIDA_CARRO que indicam que o carro saiu da insterseção. Note que, as transições de partida utilizam dos places ORDEM_FILA_ONIBUS/ORDEM_FILA_CARRO para garantir a partida dos carros na ordem de chegada. Além disso, os places ACTUALLY_VERDE_O/ACTUALLY_VERDE_C utilizam fichas inteiras temporizadas para garantir que os veículos propagem-se no tempo de simulação. As transições de partida adicionam um tempo as fichas temporizadas de 5 segundos para os ônibus e 2 segundos para os carros.

<p align="center">
  <img src="https://github.com/Danilo0liveira/HCPN_TRAFFIC_CONTROL/blob/main/figures/semaforo.png?raw=true" alt="Logo" width="800"/>
</p>

<p align="center">Figura 04: Representação Do Semaforo</p>




