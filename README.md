# Tetris---C

Este commit foca na correta aplicação da lógica de Fila (FIFO - First-In, First-Out) em um array estático.

Estrutura e Funcionalidades
O programa opera como uma Fila Circular, permitindo que os índices frente e tras percorram o array de forma eficiente, sem desperdiçar espaço após a remoção de elementos.

Estruturas de Dados:
struct Peca: Define o objeto a ser armazenado na fila, contendo o nome (tipo da peça, ex: 'I', 'T') e um id numérico único.

Fila Circular: Implementada usando um array estático (Peca filaPecas[5]) com controle modular dos índices (% CAPACIDADE_MAXIMA).

Operações Implementadas:
inserirPeca() (Enqueue): Adiciona uma nova peça gerada automaticamente ao final (tras) da fila, se houver espaço.

jogarPeca() (Dequeue): Remove a peça da frente (frente) da fila, simulando o jogador utilizando a peça.

gerarPeca(): Função auxiliar que cria peças com tipos aleatórios e IDs sequenciais.

Controles: Funções para verificar se a fila está filaCheia() ou filaVazia().
