#best battleship ever
import os
import time
import random

clear = lambda: os.system('clear')


def init_board():
    game_table = [[' ',' ',' ',' ',' '],
                  [' ',' ',' ',' ',' '],
                  [' ',' ',' ',' ',' '],
                  [' ',' ',' ',' ',' '],
                  [' ',' ',' ',' ',' ']]
    return game_table


def get_surroundings(coord):
    row = coord[0]
    col = coord[1]
    list_of_surroundings = [(row - 1, col), (row + 1, col), (row, col - 1), (row, col + 1)]
    return list_of_surroundings


def print_board(game_board):

    print('\n     1', '  2  ', '3  ', '4  ', '5 \n')

    print('A   ', game_board[0][0], '|',
          game_board[0][1], '|', game_board[0][2], '|', game_board[0][3], '|', game_board[0][4])

    print('    ---+---+---+---+---')

    print('B   ', game_board[1][0], '|',
          game_board[1][1], '|', game_board[1][2], '|',  game_board[1][3], '|', game_board[1][4])

    print('    ---+---+---+---+---')

    print('C   ', game_board[2][0], '|',
          game_board[2][1], '|',  game_board[2][2], '|', game_board[2][3], '|', game_board[2][4])

    print('    ---+---+---+---+---')

    print('D   ', game_board[3][0], '|',
          game_board[3][1], '|',  game_board[3][2], '|', game_board[3][3], '|', game_board[3][4])

    print('    ---+---+---+---+---')

    print('E   ', game_board[4][0], '|',
          game_board[4][1], '|',  game_board[4][2], '|', game_board[4][3], '|', game_board[4][4])


def print_board_shooting_phase(game_board1, game_board2):
    print('\n     Player1                 Player2 / AI           ')
    print('     1', '  2  ', '3  ', '4  ', '5  ', '    1', '  2  ', '3  ', '4  ', '5  \n')

    print('A   ', game_board1[0][0], '|',
          game_board1[0][1], '|', game_board1[0][2], '|', game_board1[0][3], '|', game_board1[0][4], '  A  ', game_board2[0][0], '|',
          game_board2[0][1], '|', game_board2[0][2], '|', game_board2[0][3], '|', game_board2[0][4])

    print('    ---+---+---+---+---', '    ---+---+---+---+---')

    print('B   ', game_board1[1][0], '|',
          game_board1[1][1], '|', game_board1[1][2], '|', game_board1[1][3], '|', game_board1[1][4], '  B  ', game_board2[1][0], '|',
          game_board2[1][1], '|', game_board2[1][2], '|', game_board2[1][3], '|', game_board2[1][4])

    print('    ---+---+---+---+---', '    ---+---+---+---+---')

    print('C   ', game_board1[2][0], '|',
          game_board1[2][1], '|', game_board1[2][2], '|', game_board1[2][3], '|', game_board1[2][4], '  C  ', game_board2[2][0], '|',
          game_board2[2][1], '|', game_board2[2][2], '|', game_board2[2][3], '|', game_board2[2][4])

    print('    ---+---+---+---+---', '    ---+---+---+---+---')

    print('D   ', game_board1[3][0], '|',
          game_board1[3][1], '|', game_board1[3][2], '|', game_board1[3][3], '|', game_board1[3][4], '  D  ', game_board2[3][0], '|',
          game_board2[3][1], '|', game_board2[3][2], '|', game_board2[3][3], '|', game_board2[3][4])

    print('    ---+---+---+---+---', '    ---+---+---+---+---')

    print('E   ', game_board1[4][0], '|',
          game_board1[4][1], '|', game_board1[4][2], '|', game_board1[4][3], '|', game_board1[4][4], '  E  ', game_board2[4][0], '|',
          game_board2[4][1], '|', game_board2[4][2], '|', game_board2[4][3], '|', game_board2[4][4])


def get_move(game_board, message):
    user_input = input('\n' + message).upper()
    valid_inputs = ['A1', 'A2', 'A3', 'A4', 'A5',
                    'B1', 'B2', 'B3', 'B4', 'B5',
                    'C1', 'C2', 'C3', 'C4', 'C5',
                    'D1', 'D2', 'D3', 'D4', 'D5',
                    'E1', 'E2', 'E3', 'E4', 'E5']

    while True:

        while user_input not in valid_inputs:
            user_input = input('Invalid input. Try again ').upper()
            continue
        if list(user_input)[0] == 'A':
            row = 0
        elif list(user_input)[0] == 'B':
            row = 1
        elif list(user_input)[0] == 'C':
            row = 2
        elif list(user_input)[0] == 'D':
            row = 3
        elif list(user_input)[0] == 'E':
            row = 4

        if list(user_input)[1] == '1':
            col = 0
        elif list(user_input)[1] == '2':
            col = 1
        elif list(user_input)[1] == '3':
            col = 2
        elif list(user_input)[1] == '4':
            col = 3
        elif list(user_input)[1] == '5':
            col = 4

        return (row, col)


def get_ai_move(game_board, message):
    valid_inputs = ['A1', 'A2', 'A3', 'A4', 'A5',
                    'B1', 'B2', 'B3', 'B4', 'B5',
                    'C1', 'C2', 'C3', 'C4', 'C5',
                    'D1', 'D2', 'D3', 'D4', 'D5',
                    'E1', 'E2', 'E3', 'E4', 'E5']
    print(message)
    time.sleep(2)
    clear()
    ai_input = random.choice(valid_inputs)

    if list(ai_input)[0] == 'A':
        row = 0
    elif list(ai_input)[0] == 'B':
        row = 1
    elif list(ai_input)[0] == 'C':
        row = 2
    elif list(ai_input)[0] == 'D':
        row = 3
    elif list(ai_input)[0] == 'E':
        row = 4

    if list(ai_input)[1] == '1':
        col = 0
    elif list(ai_input)[1] == '2':
        col = 1
    elif list(ai_input)[1] == '3':
        col = 2
    elif list(ai_input)[1] == '4':
        col = 3
    elif list(ai_input)[1] == '5':
        col = 4

    return (row, col)


def get_coord_list(game_board):
    coord_list = []
    for i in range(0, len(game_board)):
        for j in range(0, len(game_board)):
            coord_list.append((i, j))
    return coord_list


def first_move(player_board, player_moves, player_number, message):
    if player_number == 'AI':
        ship1_first_move = get_ai_move(player_board, message)
        player_moves.append(ship1_first_move)
        player_board[ship1_first_move[0]][ship1_first_move[1]] = 'X'
        time.sleep(1)
        clear()
        print(f'{player_number} ship selection phase. ')
        print_board(player_board)
    else:
        ship1_first_move = get_move(player_board, message)
        player_moves.append(ship1_first_move)
        player_board[ship1_first_move[0]][ship1_first_move[1]] = 'X'
        clear()
        print(f'{player_number} ship selection phase. ')
        print_board(player_board)


def second_move(player_board, player_moves, player_number, message):
    if player_number == 'AI':
        list_of_valid_moves = list(set(get_surroundings(player_moves[0])))
        ship1_second_move = get_ai_move(player_board, message)
        while ship1_second_move not in list_of_valid_moves:
            ship1_second_move = get_ai_move(player_board, message)
        player_moves.append(ship1_second_move)
        player_board[ship1_second_move[0]][ship1_second_move[1]] = 'X'
        time.sleep(1)
        clear()
        print(f'{player_number} ship selection phase. ')
        print_board(player_board)
    else:
        list_of_valid_moves = list(set(get_surroundings(player_moves[0])))
        ship1_second_move = get_move(player_board, message)
        while ship1_second_move not in list_of_valid_moves:
            ship1_second_move = get_move(player_board, message)
        player_moves.append(ship1_second_move)
        player_board[ship1_second_move[0]][ship1_second_move[1]] = 'X'
        clear()
        print(f'{player_number} ship selection phase. ')
        print_board(player_board)

def third_move(player_board, player_moves, player_number, message):
    if player_number == 'AI':
        list_of_valid_moves = list((set(coord_list)) - (set(get_surroundings(player_moves[0])) | set(get_surroundings(player_moves[1]))))
        ship2_first_move = get_ai_move(player_board, message)
        while ship2_first_move not in list_of_valid_moves:
            ship2_first_move = get_ai_move(player_board, message)
        player_moves.append(ship2_first_move)
        player_board[ship2_first_move[0]][ship2_first_move[1]] = 'X'
        time.sleep(1)
        clear()
        print(f'{player_number} ship selection phase. ')
        print_board(player_board)
    else:
        list_of_valid_moves = list((set(coord_list)) - (set(get_surroundings(player_moves[0])) | set(get_surroundings(player_moves[1]))))
        ship2_first_move = get_move(player_board, message)
        while ship2_first_move not in list_of_valid_moves:
            ship2_first_move = get_move(player_board, message)
        player_moves.append(ship2_first_move)
        player_board[ship2_first_move[0]][ship2_first_move[1]] = 'X'
        clear()
        print(f'{player_number} ship selection phase. ')
        print_board(player_board)

def fourth_move(player_board, player_moves, player_number, message):
    if player_number == 'AI':
        list_of_valid_moves = list(set(get_surroundings(player_moves[2])) - (set(get_surroundings(player_moves[0])) | set(get_surroundings(player_moves[1]))))
        ship2_second_move = get_ai_move(player_board, message)
        while ship2_second_move not in list_of_valid_moves:
            ship2_second_move = get_ai_move(player_board, message)
        player_moves.append(ship2_second_move)
        player_board[ship2_second_move[0]][ship2_second_move[1]] = 'X'
        time.sleep(1)
        clear()
        print(f'{player_number} ship selection phase. ')
        print_board(player_board)
    else:
        list_of_valid_moves = list(set(get_surroundings(player_moves[2])) - (set(get_surroundings(player_moves[0])) | set(get_surroundings(player_moves[1]))))
        ship2_second_move = get_move(player_board, message)
        while ship2_second_move not in list_of_valid_moves:
            ship2_second_move = get_move(player_board, message)
        player_moves.append(ship2_second_move)
        player_board[ship2_second_move[0]][ship2_second_move[1]] = 'X'
        clear()
        print(f'{player_number} ship selection phase. ')
        print_board(player_board)

def fifth_move(player_board, player_moves, player_number, message):
    if player_number == 'AI':
        list_of_valid_moves = list(set(coord_list) - (set(get_surroundings(player_moves[0])) | set(get_surroundings(player_moves[1])) |  set(get_surroundings(player_moves[2])) | set(get_surroundings(player_moves[3]))))
        ship3 = get_ai_move(player_board, message)
        while ship3 not in list_of_valid_moves:
            ship3 = get_ai_move(player_board, message)
        player_moves.append(ship3)
        player_board[ship3[0]][ship3[1]] = 'X'
        time.sleep(1)
        clear()
        print(f'{player_number} ship selection phase. ')
        print_board(player_board)
    else:
        list_of_valid_moves = list(set(coord_list) - (set(get_surroundings(player_moves[0])) | set(get_surroundings(player_moves[1])) |  set(get_surroundings(player_moves[2])) | set(get_surroundings(player_moves[3]))))
        ship3 = get_move(player_board, message)
        while ship3 not in list_of_valid_moves:
            ship3 = get_move(player_board, message)
        player_moves.append(ship3)
        player_board[ship3[0]][ship3[1]] = 'X'
        clear()
        print(f'{player_number} ship selection phase. ')
        print_board(player_board)

def sixth_move(player_board, player_moves, player_number, message):
    if player_number == 'AI':
        list_of_valid_moves = list(set(coord_list) - (set(get_surroundings(player_moves[0])) | set(get_surroundings(player_moves[1])) |  set(get_surroundings(player_moves[4])) | set(get_surroundings(player_moves[2])) | set(get_surroundings(player_moves[3]))))
        ship4 = get_ai_move(player_board, message)
        while ship4 not in list_of_valid_moves:
            ship4 = get_ai_move(player_board, message)
        player_moves.append(ship4)
        player_board[ship4[0]][ship4[1]] = 'X'
        time.sleep(1)
        clear()
        print(f'{player_number} ship selection phase. ')
        print_board(player_board)
    else:
        list_of_valid_moves = list(set(coord_list) - (set(get_surroundings(player_moves[0])) | set(get_surroundings(player_moves[1])) |  set(get_surroundings(player_moves[4])) | set(get_surroundings(player_moves[2])) | set(get_surroundings(player_moves[3]))))
        ship4 = get_move(player_board, message)
        while ship4 not in list_of_valid_moves:
            ship4 = get_move(player_board, message)
        player_moves.append(ship4)
        player_board[ship4[0]][ship4[1]] = 'X'
        clear()
        print(f'{player_number} ship selection phase. ')
        print_board(player_board)


def shooting(player_turn):
    if player_turn == 1:
        shot = get_move(player2_hits_board, message_shooting_phase_player1)
        if shot in player2_moves:
            establish_if_boat_sunk(shot, player2_moves, player2_hits_board)
        else:
            player2_hits_board[shot[0]][shot[1]] = 'M'
    else:
        shot = get_move(player1_hits_board, message_shooting_phase_player2)
        if shot in player1_moves:
            establish_if_boat_sunk(shot, player1_moves, player1_hits_board)
        else:
            player1_hits_board[shot[0]][shot[1]] = 'M'
    clear()
    print_board_shooting_phase(player1_hits_board, player2_hits_board)


def shooting_ai(player_turn):
    if player_turn == 1:
        shot = get_move(ai_hits_board, message_shooting_phase_player1)
        if shot in ai_moves:
            establish_if_boat_sunk(shot, ai_moves, ai_hits_board)
        else:
            ai_hits_board[shot[0]][shot[1]] = 'M'
    else:
        shot = get_ai_move(player1_hits_board, message_shooting_phase_ai)
        if shot in player1_moves:
            establish_if_boat_sunk(shot, player1_moves, player1_hits_board)
        else:
            player1_hits_board[shot[0]][shot[1]] = 'M'
    clear()
    print_board_shooting_phase(player1_hits_board, ai_hits_board)


def establish_if_boat_sunk(coord, player_moves, player_hits_board):
    if coord in player_moves[0:4]:
        index = player_moves.index(coord)
        if index == 0:
            if player_hits_board[player_moves[1][0]][player_moves[1][1]] == 'H':
                player_hits_board[player_moves[1][0]][player_moves[1][1]] = 'S'
                player_hits_board[player_moves[0][0]][player_moves[0][1]] = 'S'
            else:
                player_hits_board[coord[0]][coord[1]] = 'H'
        elif index == 1:
            if player_hits_board[player_moves[0][0]][player_moves[0][1]] == 'H':
                player_hits_board[player_moves[1][0]][player_moves[1][1]] = 'S'
                player_hits_board[player_moves[0][0]][player_moves[0][1]] = 'S'
            else:
                player_hits_board[coord[0]][coord[1]] = 'H'
        elif index == 2:
            if player_hits_board[player_moves[3][0]][player_moves[3][1]] == 'H':
                player_hits_board[player_moves[3][0]][player_moves[3][1]] = 'S'
                player_hits_board[player_moves[2][0]][player_moves[2][1]] = 'S'
            else:
                player_hits_board[coord[0]][coord[1]] = 'H'
        elif index == 3:
            if player_hits_board[player_moves[2][0]][player_moves[2][1]] == 'H':
                player_hits_board[player_moves[2][0]][player_moves[2][1]] = 'S'
                player_hits_board[player_moves[3][0]][player_moves[3][1]] = 'S'
            else:
                player_hits_board[coord[0]][coord[1]] = 'H'
    else:
        player_hits_board[coord[0]][coord[1]] = 'S'


def check_victory(player_moves, player_hits_board, winner):
    if (player_hits_board[player_moves[0][0]][player_moves[0][1]] == 'S' and
        player_hits_board[player_moves[1][0]][player_moves[1][1]] == 'S' and
        player_hits_board[player_moves[2][0]][player_moves[2][1]] == 'S' and
        player_hits_board[player_moves[3][0]][player_moves[3][1]] == 'S' and
        player_hits_board[player_moves[4][0]][player_moves[4][1]] == 'S' and
        player_hits_board[player_moves[5][0]][player_moves[5][1]] == 'S' ):
        return winner
    else:
        return 0


# global variables
player1_board = init_board()
player2_board = init_board()
ai_board = init_board()

coord_list = get_coord_list(init_board())

player1_moves = []
player2_moves = []
ai_moves = []

player1_hits_board = init_board()
player2_hits_board = init_board()
ai_hits_board = init_board()

message_fill_board = 'Place your ship '
message_fill_board_ai = '\nAI is procesing'
message_shooting_phase_player1 = 'Take a shot Player1 '
message_shooting_phase_player2 = 'Take a shot Player2 '
message_shooting_phase_ai = "\nAI is shooting"

def human_vs_human():
    # fill the game_board for first player
    clear()
    print('*There are four ships on the board. \n*First two ships are two cell long , and the last two are one cell long .\n')
    print('Player1 ship selection phase. ')
    print_board(player1_board)
    first_move(player1_board, player1_moves, 'Player1', message_fill_board)
    second_move(player1_board, player1_moves, 'Player1', message_fill_board)
    third_move(player1_board, player1_moves, 'Player1', message_fill_board)
    fourth_move(player1_board, player1_moves, 'Player1', message_fill_board)
    fifth_move(player1_board, player1_moves, 'Player1', message_fill_board)
    sixth_move(player1_board, player1_moves, 'Player1', message_fill_board)
    time.sleep(2)
    clear()

    # second player phases
    input("Next player's placement phase.Press any key to continue ")
    clear()

    # fill the game board for second player
    print('*There are four ships on the board. \n*First two ships are two cell long , and the last two are one cell long .\n')
    print('Player2 ship selection phase. ')
    print_board(player2_board)
    first_move(player2_board, player2_moves, 'Player2', message_fill_board)
    second_move(player2_board, player2_moves, 'Player2', message_fill_board)
    third_move(player2_board, player2_moves, 'Player2', message_fill_board)
    fourth_move(player2_board, player2_moves, 'Player2', message_fill_board)
    fifth_move(player2_board, player2_moves, 'Player2', message_fill_board)
    sixth_move(player2_board, player2_moves, 'Player2', message_fill_board)
    time.sleep(2)
    clear()
    #shooting phase
    turns = int(input('How many turns do you want to play? '))
    count = 0
    print_board_shooting_phase(player1_hits_board, player2_hits_board)
    while True:
        shooting(1)
        winner = check_victory(player2_moves, player2_hits_board, 1)
        if winner == 1:
            break
        shooting(2)
        winner = check_victory(player1_moves, player1_hits_board, 2)
        if winner == 2:
            break
        count += 1
        if turns == count:
            break
    if winner == 1:
        print('\nPlayer one is the winner')
    elif winner == 2:
        print('\nPlayer two is the winner')
    else:
        print("\nIt's a tye ")


def human_vs_ai():
    # fill the game_board for first player
    clear()
    print('*There are four ships on the board. \n*First two ships are two cell long , and the last two are one cell long .\n')
    print('Player1 ship selection phase. ')
    print_board(player1_board)
    first_move(player1_board, player1_moves, 'Player1', message_fill_board)
    second_move(player1_board, player1_moves, 'Player1', message_fill_board)
    third_move(player1_board, player1_moves, 'Player1', message_fill_board)
    fourth_move(player1_board, player1_moves, 'Player1', message_fill_board)
    fifth_move(player1_board, player1_moves, 'Player1', message_fill_board)
    sixth_move(player1_board, player1_moves, 'Player1', message_fill_board)
    time.sleep(2)
    clear()

    # second player phases
    input("Next player's placement phase.Press any key to continue ")
    clear()

    # fill the game board for second player
    print('AI ship selection phase. ')
    print_board(ai_board)
    first_move(ai_board, ai_moves, 'AI', message_fill_board_ai)
    second_move(ai_board, ai_moves, 'AI', message_fill_board_ai)
    third_move(ai_board, ai_moves, 'AI', message_fill_board_ai)
    fourth_move(ai_board, ai_moves, 'AI', message_fill_board_ai)
    fifth_move(ai_board, ai_moves, 'AI', message_fill_board_ai)
    sixth_move(ai_board, ai_moves, 'AI', message_fill_board_ai)
    time.sleep(2)
    clear()
    #shooting phase
    turns = int(input('How many turns do you want to play? '))
    count = 0
    print_board_shooting_phase(player1_hits_board, ai_hits_board)
    while True:
        shooting_ai(1)
        winner = check_victory(ai_moves, ai_hits_board, 1)
        if winner == 1:
            break
        shooting_ai('AI')
        winner = check_victory(player1_moves, player1_hits_board, 'AI')
        if winner == 'AI':
            break
        count += 1
        if turns == count:
            break
    if winner == 1:
        print('\nPlayer one is the winner')
    elif winner == 'AI':
        print('\nAI is the winner')
    else:
        print("\nIt's a tye ")


def main():
    clear()
    print( ''' 
######                                                          
#     #   ##   ##### ##### #      ######  ####  #    # # #####  
#     #  #  #    #     #   #      #      #      #    # # #    # 
######  #    #   #     #   #      #####   ####  ###### # #    # 
#     # ######   #     #   #      #           # #    # # #####  
#     # #    #   #     #   #      #      #    # #    # # #      
######  #    #   #     #   ###### ######  ####  #    # # #      
                                                                ''' )
    select_game = input('Please choose a game type: \n  Press 1 for HUMAN VS. HUMAN \n  Press 2 for HUMAN VS. AI \n')
    while select_game != '1' and select_game != '2':
        select_game = input('Please choose a game type: \n  Press 1 for HUMAN VS. HUMAN \n  Press 2 for HUMAN VS. AI \n')
    if select_game == '1':
        human_vs_human()
    else:
        human_vs_ai()


main()
