# Tetris Game in C++

This is a simple implementation of the classic **Tetris** game written in **C++**. The game is designed to run in the terminal and provides basic functionality, including moving Tetrominoes, placing them on the board, and handling the game over condition. 

## Features:
- **7 Tetromino shapes**: I, O, T, S, Z, J, L.
- **Basic controls**: Move the Tetrominoes left, right, and down.
- **Game pause and restart**: Pause the game at any time and restart it when needed.
- **Game over condition**: When a new Tetromino cannot be placed at the top of the board, the game ends.
- **Terminal-based interface**: The game is played in the terminal with a simple grid to represent the game board.
  
## Controls:
- **[A]**: Move the current Tetromino left.
- **[D]**: Move the current Tetromino right.
- **[S]**: Move the current Tetromino down.
- **[P]**: Pause the game. Press any key to resume.
- **[R]**: Restart the game.
- **[X]**: Exit the game.

## How the Game Works:

- The game starts with a random Tetromino falling from the top of the screen.
- Players can move the Tetrominoes left, right, and down using the arrow keys or the designated keys (`A`, `D`, `S`).
- Once the Tetromino reaches the bottom of the screen or collides with other blocks, it is placed on the board.
- New Tetrominoes are generated randomly after each placement.
- The game ends when a new Tetromino cannot be placed because the board is full.

## Compilation and Running the Game:

### On Linux/macOS:

1. **Install a C++ compiler** (e.g., `g++`).
2. **Disable terminal buffering** for reading user input without pressing Enter:
   ```bash
   stty -icanon -echo


   

3. **Compile the program:**

g++ -o tetris tetris.cpp


4. **Run the game:**

./tetris

5. **Re-enable terminal settings after the game exits:
**

stty icanon echo

**#### On Windows:**
Install a C++ compiler (e.g., MinGW, Visual Studio, or MSYS2).

Compile the program:


g++ -o tetris tetris.cpp
Run the game:


tetris.exe
Code Explanation:
The game is divided into multiple classes for clarity and organization:

Tetromino Class:

Represents a single Tetromino with its shape, position (x, y), and block character (e.g., I, O, T).

The shape is defined using a 4x4 matrix where each 1 represents a block part of the Tetromino and 0 represents an empty space.

GameBoard Class:

Contains the grid representing the game board (HEIGHT x WIDTH matrix).

Responsible for drawing the grid, checking if a move is possible, placing a Tetromino on the board, and clearing the board.

TetrisGame Class:

Manages the overall game logic, including the game loop, handling user input, updating the Tetromino position, rendering the game state, and managing the game over state.

Terminal Input Handling:

The game uses kbhit() and _getch() for Windows to detect keypresses.

On Linux/macOS, it uses ioctl() and read() to get user input without the need for pressing Enter.

Rendering:

The game uses ANSI escape codes (\033[H\033[J) to clear the terminal screen and redraw the game board each frame.

The game board is printed with vertical walls | and horizontal separators -.

Game Over:

The game ends when the board is full, and a new Tetromino cannot be placed at the top. A "Game Over!" message is displayed, and the player can choose to restart or exit.

Example Screenshots:
While the game doesn't have graphical elements, the output in the terminal will look something like this:


|          |          
|    I     |        
|   I I    |     
|   I I    |     
|   I I    |     
|----------|       
[ A ] Left [ D ] Right [ S ] Down [ P ] Pause [ R ] Restart [ X ] Exit


In this example, the I Tetromino is falling, and the controls are displayed at the bottom.

License:
This project is open-source and available for modification and distribution. You are free to use, modify, and contribute to this code.

Acknowledgments:
This project was created as an exercise to implement a basic terminal-based game in C++.

Inspired by the classic Tetris game.

Contributions:
Feel free to fork this repository, create issues, submit pull requests, or suggest improvements. Contributions are welcome!



