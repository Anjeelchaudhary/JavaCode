## 22.BackTraking
Code for 
[nQueens in board](https://github.com/Anjeelchaudhary/JavaCode/blob/master/22.Backtracking/Nqueens.java)

#### # Placing of nQueens in board

```
     public class Nqueens {
    //This code is only for how to placing nQueens in the chess borad
    public static void nQeen(char board[][],int row) {
        //base case 
        if(row == board.length) {
            print(board);
            return;
        }
        //workdone
        for(int j=0; j<board.length; j++) {
            board[row][j] = 'Q';
            nQeen(board,row+1);//function call
            board[row][j] = 'X';//backtrack
        }
    }
    //for printing of borads
    public static void print(char borad[][]) {
        for(int i=0; i<borad.length ; i++) {
            for(int j=0; j<borad.length ; j++) {
                System.out.print(borad[i][j]+" ");
            }
            System.out.println();
        }
    }
```
#
Code for 
[nQueens in safePlace](https://github.com/Anjeelchaudhary/JavaCode/blob/master/22.Backtracking/nQueensIsSafe.java)

#### # nQueens in safePlace
```
 public class nQueensIsSafe {
    public static boolean isSafe(char[][] board,int row,int col) {
        //vertical
        for(int i=row-1;i>=0;i--) {
            if(board[i][col] == 'Q') {
                return false;
            }
        }
        //diag left up
        for(int i=row-1,j=col-1;i>=0 && j>=0;i--,j--) {
            if(board[i][j] == 'Q') {
                return false;
            }
        }
        //diag right up 
        for(int i=row-1,j=col+1;i>=0 && j<board.length;i--,j++) {
            if(board[i][j] == 'Q') {
                return false;
            }
        }
        return true;
    }
    //This code is only for how to placing nQueens in the chess borad
    public static void nQeen(char board[][],int row) {
        //base case 
        if(row == board.length) {
            print(board);
            return;
        }
        //workdone
        for(int j=0; j<board.length; j++) {
            if(isSafe(board,row,j)) {
                board[row][j] = 'Q';
                nQeen(board,row+1);//function call
                board[row][j] = 'X';//backtrack
            }
            
        }
    }
    //for printing of borads
    public static void print(char borad[][]) {
        for(int i=0; i<borad.length ; i++) {
            for(int j=0; j<borad.length ; j++) {
                System.out.print(borad[i][j]+" ");
            }
            System.out.println();
        }
    }
```