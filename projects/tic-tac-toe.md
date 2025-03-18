### Description:
This mini project focuses on the implementation of a Minimax function a well-established artificial intelligence decision-making algorithm. By integrating Minimax, we can showcase the ability of a formidable foe that fully optimizes move selection and game strategy.

![Tic-Tac-Toe demo video](/projects/videos/tic-tac-toe.mp4)

### Minimax Algorithm:

The Minimax algorithm is a foundational technique in game theory and artificial intelligence, designed to identify the optimal move in competitive two-player scenarios. This approach is widely used in games such as Tic-Tac-Toe, Chess, and Connect Four, where players aim to maximize their own chances of victory while minimizing those of their opponent.

```javascript
function minimax(newBoard, player) {
  // Find available spots on the board
  var availSpots = findIndexEmptySquares();

  // Check if the current board state is a win for Player 1 (P1)
  if (checkWin(newBoard, P1)) {
    return { score: -10 }; // If P1 wins, return a negative score
  }
  
  // Check if the current board state is a win for Player 2 (P2)
  else if (checkWin(newBoard, P2)) {
    return { score: 10 }; // If P2 wins, return a positive score
  }
  
  // If there are no empty spots left, it's a tie
  else if (availSpots.length === 0) {
    return { score: 0 }; // Return a score of 0 for a tie
  }

  // List to keep track of possible moves and their scores
  var moves = [];

  // Try every possible move
  for (var i = 0; i < availSpots.length; i++) {
    var move = {}; // Object to store information about this move
    move.index = newBoard[availSpots[i]]; // Save the current state of the spot

    // Make the move on the board
    newBoard[availSpots[i]] = player;

    // Call minimax recursively to evaluate the move
    if (player == P2) {
      // If it's Player 2's turn, call minimax for Player 1
      var result = minimax(newBoard, P1);
      move.score = result.score; // Get the score from the recursive call
    } else {
      // If it's Player 1's turn, call minimax for Player 2
      var result = minimax(newBoard, P2);
      move.score = result.score; // Get the score from the recursive call
    }

    // Undo the move (backtrack) to evaluate the next possible move
    newBoard[availSpots[i]] = move.index;
    moves.push(move); // Add this move to the list of moves
  }

  var bestMove;
  
  // Determine the best move based on the current player
  if (player === P2) {
    // If it's Player 2's turn (the maximizing player)
    var bestScore = -10000; // Initialize to a very low score
    for (var i = 0; i < moves.length; i++) {
      if (moves[i].score > bestScore) {
        bestScore = moves[i].score; // Update best score
        bestMove = i; // Record the index of the best move
      }
    }
  } else {
    // If it's Player 1's turn (the minimizing player)
    var bestScore = 10000; // Initialize to a very high score
    for (var i = 0; i < moves.length; i++) {
      if (moves[i].score < bestScore) {
        bestScore = moves[i].score; // Update best score
        bestMove = i; // Record the index of the best move
      }
    }
  }
  
  // Return the best move from the list
  return moves[bestMove];
}
```

In this Tic-Tac-Toe implementation, the Minimax function assesses the most advantageous move by recursively simulating all potential game outcomes.

### Demo
Test your skills and check out the demo on my github [here.](https://noodlebenji2960.github.io/tic-tac-toe/)