# Jogo-PedraPapelTesoura
 Implementação simples de um jogo de Pedra, Papel e Tesoura em C. O jogador escolhe entre "Pedra", "Papel" ou "Tesoura", enquanto o computador faz uma escolha aleatória. O programa compara as escolhas e exibe o vencedor ou se houve empate. Usa rand() para gerar escolhas aleatórias e demonstra lógica condicional básica em C.

Recomendação de site para compilar o código: https://www.programiz.com/

Vamos nos conectar ? Segue meu perfil: https://github.com/ProfAdaelOliveira/SobreMim_Portifolio

Segue projeto em C:

    #include <stdio.h>
    #include <stdlib.h>
    #include <time.h>

    int main() {
         
         int jogador, computador;
    
    srand(time(NULL));
    
    printf("Escolha:\n");
    printf("0 - Pedra\n");
    printf("1 - Papel\n");
    printf("2 - Tesoura\n");
    printf("Sua escolha: ");
    scanf("%d", &jogador);

    if (jogador < 0 || jogador > 2) {
        printf("Escolha inválida!\n");
        return 1;
    }

    computador = rand() % 3;
    
    // Exibindo a escolha do jogador
    printf("Você escolheu: %s\n", 
        (jogador == 0) ? "Pedra" : (jogador == 1) ? "Papel" : "Tesoura");
    
    // Exibindo a escolha do computador
    printf("Computador escolheu: %s\n", 
        (computador == 0) ? "Pedra" : (computador == 1) ? "Papel" : "Tesoura");

    // Lógica para determinar o vencedor
    if (jogador == computador) {
        printf("O jogo empatou!\n");
    } else if ((jogador == 0 && computador == 2) || 
               (jogador == 1 && computador == 0) || 
               (jogador == 2 && computador == 1)) {
        printf("O jogador venceu!\n");
    } else {
        printf("O computador venceu!\n");
    }

    return 0;
    }
