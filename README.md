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

Este commit expande o projeto Tetris Stack para simular as duas estruturas críticas de gerenciamento de peças do jogo: a Fila Circular (Peças Futuras) e a Pilha Linear (Peças de Reserva/Hold).

Histórico de Commit: feat: Integração Fila Circular e Pilha para Controle de Peças 🕹️
Este commit foca na coordenação e regras de movimento de peças entre as duas estruturas de dados, garantindo a lógica de jogo (manter a fila sempre cheia).

Estrutura e Funcionalidades
O sistema coordena a remoção (Fila: FIFO; Pilha: LIFO) e o movimento de peças, com restrições de capacidade em ambas as estruturas.

1. Fila Circular (Next Pieces)
Implementação: Array estático com lógica modular para o reaproveitamento de espaço.

Capacidade: Fixa em 5.

Regra de Reposição: Após qualquer ação (jogar, reservar, usar reserva) que remova uma peça da frente da fila ou da pilha, uma nova peça é gerada e adicionada ao final da fila (ENQUEUE) para mantê-la sempre cheia.

2. Pilha Linear (Hold Pieces)
Implementação: Array estático com controle do topo (LIFO).

Capacidade: Fixa em 3.

Operações: PUSH (reservar) e POP (usar).

3. Ações de Jogo:
Jogar Peça: Remove a peça da FRENTE da Fila (DEQUEUE) e repõe a Fila.

Reservar Peça: Remove a peça da Fila (DEQUEUE) e a move para o TOPO da Pilha (PUSH), se houver espaço. Repõe a Fila.

Usar Peça Reservada: Remove a peça do TOPO da Pilha (POP) para uso imediato. Repõe a Fila.
