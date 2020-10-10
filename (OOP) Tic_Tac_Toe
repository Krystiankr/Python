import time

class Tic_tac_toe():
    score_x=0
    score_o=0
    def __init__(self):
        self.board = ["O"," "," ",
                      " "," "," ",
                      " "," ","X"]
        self.player_x = "X"
        self.player_o = "O"
        self.current_move = "X"
        self.win_movesx = []
        #these are the possible moves to be made
        self.moves = []
        #keeps track of all won moves
        self.win_movesss = []
        #stores information about the selected person at a given time
        self.win_for = ""
    def print_board(self):
        print("Printing board!\n")
        print("%s | %s | %s\n---------\n%s | %s | %s\n---------\n%s | %s | %s"
              %(self.board[0],self.board[1],self.board[2],
                self.board[3],self.board[4],self.board[5],
                self.board[6],self.board[7],self.board[8]))
        print()
       
    def make_move(self, position, player):
        if self.board[position] == " ":
            self.board[position]=player
            #self.change_move()
            self.print_board()
        else:
            print("This field is taken")

    def make_move_simulatana(self, position, player):
        self.board[position]=player

    def check_win(self, player):
        combos = [[0,1,2],[3,4,5],[6,7,8],[0,3,6],[1,4,7],[2,5,8],[0,4,8],[2,4,6]]      
        for combo in combos:
            flag = True
            for co in combo:
                if self.board[co] != player:
                    flag = False   
            if flag:
                return True

    #The function returns the number of possible moves
    #adds possible moves to the list
    def available_moves(self):
        amount=0
        self.moves=[]
        for  i in range(0,9):
            if self.board[i] == " ":
                amount += 1
                self.moves.append(i)
        return amount

    def change_move(self):
        if self.current_move == "X":
            self.current_move = "O"
        else:
            self.current_move = "X"

    def current_movee(self):
        return self.current_move

    def print_moves(self):
        for el in self.moves:
            print(el,end=',')
        print()

    def clean_board(self):
        self.board = [" "," "," ",
                      " "," "," ",
                      " "," "," "]
        
    def print_available_moves(self):
        self.win_moves = []  
        for el in self.moves:
            self.make_move_simulatana(int(el),"X")
            if self.check_win("X"):          
                self.win_moves.append(el)  
            self.board[el] = " "
    
    def print_ava_moves(self):
        if self.available_moves():
            print("Available moves[{}]:".format(self.available_moves()),end='')
        else:
            print("No available moves")

    def print_win_movess(self):
        i = 0
        for el in self.win_moves:
            i += 1
            self.win_movesss.append(el)
            
        if self.win_moves:
            print("({}) winning moves: [{}]: ".format(self.win_for,i),end='')
            for el in self.win_moves:
                print(el,end=',')
            print()
        else:
            print("No win moves")



    #uses a list of possible moves, makes a move and checks if
    #it is won, if so, adds it to the list
    #in addition, it adds to the variable who is winning
    def win_moves(self, player):
        self.available_moves()
        self.win_movesx = []     
        self.win_for = ""
        pointer = False
        for el in self.moves:
            self.make_move_simulatana(int(el),player)
            if self.check_win(player):
                self.win_movesx.append(el)
                pointer = True
            self.board[el] = " "
        self.win_for = player
        return pointer

    def opposite_player(self, player):
        if player == "X":
            return "O"
        else:
            return "X"

    def print_opposite_moves():
        i = 0
        for el in self.win_moves:
            i += 1
            self.win_movesss.append(el)
            
        if self.win_moves:
            print("({}) block moves: [{}]: ".format(self.win_for,i),end='')
            for el in self.win_moves:
                print(el,end=',')
            print()
        else:
            print("No block moves")        

    def print_current_move(self):
        print("Current move: {}".format(self.current_move))

    def block_enemy(self, player):
        self.best_move(self.opposite_player(player))
        self.print_opposite_moves()

    def best_move_legit(self, player):
        if self.win_moves(player):
            print("There is a winning move: {}".format(self.win_movesx[0]))
        elif self.win_moves(self.opposite_player(player)):
            print("There is no a winning move for: {}".format(player))
            print("There is a block move: {}".format(self.win_movesx[0]))
        else:
            print("There is no a winning move for: {}".format(player))
            print("There is no a block move")
            if self.available_moves():
                print("There is available moves: {}".format(self.moves[0]))
            else:
                print("There is no available moves")
    def pc(self, player):
        if self.win_moves(player):
            return self.win_movesx[0]
        elif self.win_moves(self.opposite_player(player)):
            return self.win_movesx[0]
        else:
            if self.available_moves():
                return self.moves[0]
            else:
                print("There is no available moves")
        #win for me
            #take first move or display no win moves
        #block enemy
            #takie first move blok or display no block moves
        #first move availavle
            #takie first move display no moves
        
    
if __name__ == "__main__":
    Game=Tic_tac_toe()
    Game.print_board()    
    Game.best_move_legit("O")
    while True:
        if Game.check_win("X") or Game.check_win("O"):
            if Game.current_movee() == "X":
                Game.score_o += 1
                print("Win O, Score: {}".format(Game.score_o))
            else:
                Game.score_x += 1
                print("Win X, Score: {}".format(Game.score_x))
            Game.clean_board()
            Game.print_board()
        elif Game.available_moves()==0:
            print("Tie")
            Game.clean_board()
        #Game.make_move(int(input("Move: {} Where?".format(Game.current_movee()))),Game.current_movee())
        time.sleep(1.5)
        Game.make_move(Game.pc("O"),"O")
        if Game.check_win("X") or Game.check_win("O"):
            if Game.current_movee() == "X":
                Game.score_o += 1
                print("Win O, Score: {}".format(Game.score_o))
            else:
                Game.score_x += 1
                print("Win X, Score: {}".format(Game.score_x))
            Game.clean_board()
            Game.print_board()
        elif Game.available_moves()==0:
            print("Tie")
            Game.clean_board()
        time.sleep(1.5)
        Game.make_move(Game.pc("X"),"X")
        Game.print_board()
