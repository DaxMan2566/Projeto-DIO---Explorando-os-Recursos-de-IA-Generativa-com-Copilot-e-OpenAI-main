# Explorando os Recursos de IA Generativa com Copilot e OpenAI

Neste projeto, analisei a simplicidade do uso da inteligência artificial no cotidiano, eu mesmo uso até em alguns trabalhos escolares para sanar algumas duvidas, e realmente funciona.

## 1 - Ajuda na criação de código

Regularmente, utilizo IA generativa para me auxiliar a pensar na lógica e implementação de uma funcionalidade. No exemplo abaixo, o Copiloto me ajuda com a criação de uma função que faz um jogo da velha em linguagem python.

Prompt:

Escreva para mim uma linha de codigos em python que faça um jogo da velha.

Resultado:

import tkinter as tk
from tkinter import messagebox

class TicTacToe:
    def __init__(self):
        self.root = tk.Tk()
        self.root.title("Jogo da Velha")
        self.current_player = "X"
        self.board = [""] * 9

        for i in range(9):
            btn = tk.Button(self.root, text="", command=lambda i=i: self.make_move(i))
            btn.grid(row=i // 3, column=i % 3)

    def make_move(self, position):
        if self.board[position] == "":
            self.board[position] = self.current_player
            self.update_button_text(position)
            winner = self.check_winner()
            if winner:
                messagebox.showinfo("Fim do Jogo", f"Jogador {winner} venceu!")
                self.root.quit()
            else:
                self.current_player = "O" if self.current_player == "X" else "X"

    def update_button_text(self, position):
        btn = self.root.grid_slaves(row=position // 3, column=position % 3)[0]
        btn.config(text=self.board[position])

    def check_winner(self):
        winning_combinations = [(0, 1, 2), (3, 4, 5), (6, 7, 8),
                                (0, 3, 6), (1, 4, 7), (2, 5, 8),
                                (0, 4, 8), (2, 4, 6)]

        for combo in winning_combinations:
            if self.board[combo[0]] == self.board[combo[1]] == self.board[combo[2]] != "":
                return self.board[combo[0]]

        if "" not in self.board:
            messagebox.showinfo("Fim do Jogo", "Empate!")
            self.root.quit()

    def run(self):
        self.root.mainloop()

if __name__ == "__main__":
    game = TicTacToe()
    game.run()

## 2 - Lista de alimentos bons para o café da manhã

Prompt:

Faça umas lista de 10 alimentos bons para se comer no café da manhã

Copilot
Claro! Aqui estão 10 alimentos saudáveis que você pode incluir no seu café da manhã para começar o dia com energia e disposição:

Pão integral: Rico em fibras, fornece carboidratos complexos que prolongam a sensação de saciedade e ajudam a controlar os níveis de glicose no sangue1.
Frutas: São essenciais para uma dieta saudável, ricas em vitaminas, fibras, antioxidantes e minerais. Você pode misturar frutas com iogurte, chia ou granola, ou preparar um suco ou vitamina com as suas preferidas1.
Leite: Uma das principais fontes de cálcio, essencial para o desenvolvimento ósseo e prevenção de doenças como a osteoporose. Os veganos podem optar por leites vegetais, que também são livres de colesterol e lactose1.
Queijo: Fonte de proteínas, escolha os queijos brancos, como minas, ricota e cottage, que contêm menos gordura do que os amarelos1.
Cereais: Opções como chia, granola e linhaça são ricas em fibras, vitaminas e nutrientes. Consuma com frutas e iogurtes ou no preparo de vitaminas, tortas e bolos1.
Ovo: Rico em proteínas e contendo 13 nutrientes essenciais, o ovo é uma ótima escolha para o café da manhã1.
Café: A cafeína dá disposição, energia e concentração. O grão de café também possui antioxidantes que protegem nossas células. Evite adicionar açúcar1.
Aveia: Uma porção de aveia com leite e mel é saborosa e nutritiva1.
Iogurte: Escolha versões naturais ou light, adicionando frutas e mel para um café da manhã saudável2.
Smoothies com frutas vermelhas: Misture leite vegetal com morangos, blueberries e framboesa para uma opção deliciosa e nutritiva3.
Lembre-se de variar os alimentos e adaptar às suas preferências pessoais. Um café da manhã equilibrado é fundamental para um dia produtivo e saudável! 🌞🍽️

1: Jasmine Alimentos - 13 sugestões saudáveis para comer no café da manhã 2: MundoBoaForma - 20 opções de café da manhã saudável e light 3: Vitat - O que comer no café da manhã? Melhores opções para cada objetivo

Saiba mais
1

jasminealimentos.com
2

mundoboaforma.com.br
3

vitat.com.br
4

greenme.com.br
5
blog.drogarianovaesperanca.com.br

