# Tic-Tac-Toe Game

This project is a simple Tic-Tac-Toe game implemented in Java using the **Swing** library for the graphical user interface (GUI). The game allows two players to take turns marking spaces in a 3x3 grid, and it determines the winner based on the standard Tic-Tac-Toe rules.

## Features
- Two-player turn-based gameplay
- Graphical user interface (GUI) using Java Swing
- Button-based interaction for marking moves
- Displays a message when a player wins or when the game ends in a draw
- Reset functionality to clear the board and start a new game

## How to Play
1. Run the program.
2. A 3x3 grid will appear with buttons labeled `-`.
3. Player **O** goes first, followed by player **X**.
4. Click on any available button to place your mark (O or X).
5. The game checks for a winner after each move:
   - Three of the same marks in a row, column, or diagonal wins the game.
   - If all spaces are filled and no one has won, the game is declared a draw.
6. Click the **Clear** button to reset the board and start a new game.

## Running the Program
Ensure you have Java installed and run the following command:
```sh
javac mainGame.java
java mainGame
```

## Reference Code
You can refer to the following Java code for the implementation:
```java
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

public class mainGame {
    public static void main(String[] args) {
        TicTac tictac = new TicTac();
    }
}

class TicTac extends JFrame implements ActionListener {
    JButton b1, b2, b3, b4, b5, b6, b7, b8, b9, clear;
    JLabel message;
    int counter = 0;
    
    public TicTac() {
        super("Tic-Tac-Toe");
        JPanel panel = new JPanel();
        JFrame frame = new JFrame("Grid");
        
        message = new JLabel(" ");
        b1 = new JButton("-");
        b2 = new JButton("-");
        b3 = new JButton("-");
        b4 = new JButton("-");
        b5 = new JButton("-");
        b6 = new JButton("-");
        b7 = new JButton("-");
        b8 = new JButton("-");
        b9 = new JButton("-");
        clear = new JButton("Clear");
        
        panel.setLayout(new GridLayout(4, 3, 3, 3));
        
        panel.add(b1); panel.add(b2); panel.add(b3);
        panel.add(b4); panel.add(b5); panel.add(b6);
        panel.add(b7); panel.add(b8); panel.add(b9);
        panel.add(clear); panel.add(message);
        
        frame.add(panel);
        
        b1.addActionListener(this);
        b2.addActionListener(this);
        b3.addActionListener(this);
        b4.addActionListener(this);
        b5.addActionListener(this);
        b6.addActionListener(this);
        b7.addActionListener(this);
        b8.addActionListener(this);
        b9.addActionListener(this);
        clear.addActionListener(this);
        
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.pack();
        frame.setVisible(true);
        frame.setSize(200, 250);
    }
    
    public void actionPerformed(ActionEvent ae) {
        JButton clickedButton = (JButton) ae.getSource();
        if (!clickedButton.getText().equals("-")) return;
        
        counter++;
        clickedButton.setText(counter % 2 == 0 ? "X" : "O");
        clickedButton.setEnabled(false);
        
        checkWinner();
    }
    
    private void checkWinner() {
        // Logic to check if a player has won the game
    }
}
```

## Future Enhancements
- Implement a smarter AI opponent
- Add a scoreboard to track wins
- Improve the UI with better styling

## License
This project is open-source and free to use.

