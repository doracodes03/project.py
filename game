def print_board(board):
    for row in board:
        print(" ".join(row))

def check_square(board, row, col):
    if row > 0 and col > 0 and board[row][col] == board[row-1][col-1] \
            and board[row-1][col] == board[row][col-1] \
            and board[row-1][col-1] != '.':
        return True
    return False

def main():
    size = int(input("Enter the size of the board (e.g., 3 for 3x3): "))
    board = [['.' for _ in range(size)] for _ in range(size)]
    player = 'X'
    game_over = False
    moves = 0
    player_scores = {'X': 0, 'O': 0}

    while not game_over:
        print_board(board)
        print(f"Player {player}'s turn:")
        row = int(input("Enter row (0 to {size-1}): "))
        col = int(input("Enter column (0 to {size-1}): "))

        if board[row][col] == '.':
            board[row][col] = player
            moves += 1

            if check_square(board, row, col):
                player_scores[player] += 1

            if moves == size * size:
                game_over = True
                print("It's a tie!")

            player = 'X' if player == 'O' else 'O'
        else:
            print("That spot is already taken. Try again.")

    print("Game over! Final scores:")
    print(f"Player X: {player_scores['X']} points")
    print(f"Player O: {player_scores['O']} points")

if _name_ == "_main_":
    main()
