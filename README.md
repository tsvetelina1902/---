# Основна структура на морски шах (Tic Tac Toe)

def print_board(board):
    # Функция за принтиране на игровото табло
    for row in board:
        print("|".join(row))
        print("-" * 5)

def check_winner(board, player):
    # Проверка за победител
    for row in board:
        if all([cell == player for cell in row]):
            return True

    for col in range(3):
        if all([board[row][col] == player for row in range(3)]):
            return True

    if all([board[i][i] == player for i in range(3)]) or all([board[i][2 - i] == player for i in range(3)]):
        return True

    return False

def is_full(board):
    # Проверка дали таблото е пълно
    return all([cell != " " for row in board for cell in row])

def main():
    board = [[" " for _ in range(3)] for _ in range(3)]  # Създаване на празно табло
    players = ["X", "O"]
    current_player_index = 0

    print("Добре дошли в Морски шах!")
    print_board(board)


