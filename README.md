    while True:
        row = int(input(f"Играч {players[current_player_index]}, въведете ред (0-2): "))
        col = int(input(f"Играч {players[current_player_index]}, въведете колона (0-2): "))

        if board[row][col] != " ":
            print("Тази клетка е заета! Опитайте отново.")
            continue

        board[row][col] = players[current_player_index]
        print_board(board)

        if check_winner(board, players[current_player_index]):
            print(f"Поздравления! Играч {players[current_player_index]} печели!")
            break

        if is_full(board):
            print("Играта е равна!")
            break

        current_player_index = 1 - current_player_index  # Смяна на играча

if __name__ == "__main__":
    main()
