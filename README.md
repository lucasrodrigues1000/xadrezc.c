# xadrezc.c

#include <stdio.h>

#define TAM 8

// Verifica se a posição está dentro do tabuleiro
int posicao_valida(int x, int y) {
    return (x >= 0 && x < TAM && y >= 0 && y < TAM);
}

void movimentos_cavalo(int x, int y) {
    // Todas as 8 possíveis direções do cavalo
    int dx[] = { 2, 1, -1, -2, -2, -1, 1, 2 };
    int dy[] = { 1, 2,  2,  1, -1, -2, -2, -1 };

    printf("Movimentos possíveis do cavalo em (%d, %d):\n", x, y);

    for (int i = 0; i < 8; i++) {
        int novo_x = x + dx[i];
        int novo_y = y + dy[i];

        if (posicao_valida(novo_x, novo_y)) {
            printf("(%d, %d)\n", novo_x, novo_y);
        }
    }
}

int main() {
    int x = 4; // Linha
    int y = 4; // Coluna

    movimentos_cavalo(x, y);

    return 0;
}
