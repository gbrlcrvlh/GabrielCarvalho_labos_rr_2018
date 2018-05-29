### (Prática - A)
![1](https://github.com/gbrlcrvlh/GabrielCarvalho_labos_rr_2018/blob/master/Imagens/%5Bquestao%201%5D%20-%20pratica%20A%201.0.png)  

![2](https://github.com/gbrlcrvlh/GabrielCarvalho_labos_rr_2018/blob/master/Imagens/%5Bquestao%201%5D%20-%20pratica%20A%201.1.png)    

![3](https://github.com/gbrlcrvlh/GabrielCarvalho_labos_rr_2018/blob/master/Imagens/%5Bquestao%201%5D%20-%20pratica%20A%201.2.png)  

Podemos verificar que na 1° primeira imagem ambos os processos estão prontos para executar, porém os processos fazem uma espécie de fila para serem executados. Observamos então que o **processo roxo** executará primeiro que o **processo vermelho**, o que é visto na 2° imagem e logo depois na 3° imagem podemos ver o **processo vermelho** ser executado. O problema pode estar em o **processo roxo** necessitar de uma informação gerada pelo **processo vermelho** o que o levará para um estado **bloqueado** até o **processo vermelho** ser executado.

### (Prática - B)
![1](https://github.com/gbrlcrvlh/GabrielCarvalho_labos_rr_2018/blob/master/Imagens/%5Bquestao%201%5D%20-%20pratica%20B%201.0.PNG)

![1](https://github.com/gbrlcrvlh/GabrielCarvalho_labos_rr_2018/blob/master/Imagens/%5Bquestao%201%5D%20-%20pratica%20B%201.1.png)

Nesta simulação podemos observar o processo de starvation, onde apesar de ambos terem sido criado no mesmo instante, podemos ver pelo **temp UCP** que só o **processo vermelho** está sendo executado devido a sua prioridade ser maior que a do **processo preto**.
#### solução 1:
![1](https://github.com/gbrlcrvlh/GabrielCarvalho_labos_rr_2018/blob/master/Imagens/%5Bquestao%201%5D%20-%20pratica%20B%201.2.png)
Aumentando a prioridade do **processo preto**.

#### solução 2:
![1](https://github.com/gbrlcrvlh/GabrielCarvalho_labos_rr_2018/blob/master/Imagens/%5Bquestao%201%5D%20-%20pratica%20B%201.3.png)
Suspendendo o **processo vermelho**.

### (Prática - C)

***Qual o espaço de endereçamento real máximo de um processo?***
O espaço máximo de endereçamento de um processo físico é o resultado da quantidade de espaço disponível na memória principal mais o espaço disponível da memória secundária.  

***Qual o espaço de endereçamento real mínimo de um processo?***
Corresponde ao tamanho mínimo da tabela de carregamento.

***Qual o tamanho da página virtual?***
Em algumas arquiteturas de computadores este tamanho pode ser configurável pelo usuário, em outras o tamanho da página será decidido de acordo com o hardware.

### (Prática - D)
![1](https://github.com/gbrlcrvlh/GabrielCarvalho_labos_rr_2018/blob/master/Imagens/%5Bquestao%201%5D%20-%20pratica%20D%201.0.PNG) 

***Quais os critérios utilizados pelo simulador para selelcionar o processo a ser transferido para o arquivo de paginação (swap out)?***
Será selecioinado o processo com a menor chance de execução pelo processador. Neste caso vários algoritmos de escalonamento de CPU podem ser utulizados.

***Quando o processo deve ser transferido novamente para a memória principal (swap in)?***
Quando a limite de memória principal não for suficiente para todos os processos estaremcarregados.
