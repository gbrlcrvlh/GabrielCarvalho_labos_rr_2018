## Algoritmo do banqueiro

Criado em 1965 pelo holandês Edsger Dijkstra, é um algoritmo de alocação de recursos e prevenção de deadloocks (quando todo processo pertencente ao conjunto estiver esperando por um evento que somente um outro processo desse mesmo conjunto poderá fazer acontecer).

### O problema:
Considere que existem N clientes em um banco e S seja a soma do saldo disponível na conta de cada cliente. Sempre que um emprestimo é feito, o valor do empréstimo é subtraido do valor total disponível no banco. Então sempre que um emprestimo é requisitado, é necessário verificar se o valor do empréstimo menos o total disponível do banco seja maior que S.  
  
O problema se assemelha a requisição de recursos pelos processos de um sistema. Onde para evitar o deadloock é preciso verificar a segurança do "emprestimo" de recursos.

### Estrutura do algoritmo:
Assumindo **N** o número de processos e **M** tipos de recursos, temos:  
  
**Disponível**  
É um array de tamanho **M** que representa **M** tipos de recursos disponível com K instancias diponível.
Supondo que os recursos de um sistema disponível seja:  
A B C D  
3 1 1 2  
temos que:  
**Disponivel**[0] = 3  
**Disponivel**[1] = 1  
**Disponivel**[2] = 1  
**Disponivel**[2] = 2  
  
**Máximo**  
E uma matriz **N** x **M** que representa o número máximo de recursos cada processo pode ter.
Supondo que P0-P3 sejam os processos e A-D sejam os recursos:  
   A B C D  
P1 1 2 2 1  
P2 1 0 3 3  
PE 1 1 1 0  
temos que:  
**Maximo**[0][1] = 2 (Máximo de recursos do tipo B que o processo P1 pode ter é 2)

**Alocado**  
É uma matriz **N** x **M** que representa o número de recursos alocados por cada processo  
  
**Necessidade**  
É uma matriz **N** x **M** que representa o número de recursos que ainda pode ser pedido por cada processo, sendo assim podemos concluir que:  
**Necessidade**[i][j] = **Maximo**[i][j] - **Alocado**[i][j]  
  
### Requerimento de recursos: 
Para cada requerimento de recurso é necessário verificar se  
1. O número de requerimento é menor que **Necessidade**[i][j] (Erro)
2. O número de requerimento é menor que o **Disponível** pelo sistema no determinado tipo. (Aguarda)  
  
Caso contrário os recursos serão alocados:
**Disponivel** = **Disponivel** - **Requisição**
**Alocado**[i] = **Alocado**[i] + **Requisição**
**Necessidade**[i] = **Necessidade**[i] - **Requisição**
  
3. O estado final é seguro (Se sim -> **FIM**)  
  
caso contrário, os valores serão restaurados e o processo espera.
  
### Verificação de segurança:
1. Tendo Trabalho um vetor de tamanho **M** e Finalizado um vetor de tamanho **N**, temos:
**Trabalho** = **Disponível**  
**Finalizado**[i] = **false** para i = 0, 1 ... N - 1  
  
2. Encontra um i (processo) tal que:  
**Finalizado**[i] = **false**    
**Necessidade**[i] <= **Trabalho**  
Caso não exista um i com essas condições, então vá para a etapa 4  
  
3. Execute:
**Trabalho** = **Trabalho** + **Alocado**
**Finalizado**[i] = **true**
volte para o passo 2

4. Sistema seguro -> **FIM**
  
Disponível em: https://www.studytonight.com/operating-system/bankers-algorithm  
Disponível em: https://pt.wikipedia.org/wiki/Algoritmo_do_banqueiro  
Disponível em: http://homepages.dcc.ufmg.br/~dorgival/slides/so/08-deadlocks-6pp.pdf
