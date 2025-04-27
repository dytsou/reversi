# Reversi Game in LabVIEW

A fully-featured implementation of the classic Reversi board game in LabVIEW, featuring both local play and online multiplayer capabilities.

## Features

- Classic Reversi/Othello gameplay on an 8x8 board
- Player vs. Computer mode with AI opponent
  - AI implemented using minimax algorithm with heuristic evaluation
  - Multiple difficulty levels via search depth
- Online multiplayer mode (client-server architecture)
- Beautiful graphical interface

## Project Structure

The project is organized into the following components:

### Main VIs
- `main.vi` - Main game interface for local play
- `client.vi` - Client interface for online play
- `server.vi` - Server application for hosting online games
- `online(client1st).vi` - Online game where client moves first
- `online(server1st).vi` - Online game where server moves first

### Game Logic (subvis.lvlib)
- `availablePlaces.vi` - Identifies valid move locations
- `countResult.vi` - Tallies the score
- `heuristic.vi` - Evaluates board positions for AI
- `isEnd.vi` - Determines if the game has ended
- `minimax.vi` - AI decision algorithm
- `randomMove.vi` - Random move generator
- `takeStep.vi` - Executes a game move

### Board Visualization (drawPlate.lvlib)
- `canBePlaced.vi` - Verifies if a piece can be placed at a position
- `initialize(picture).vi` - Sets up the initial board
- `putPiece(picture).vi` - Places a piece on the board

## Requirements

- LabVIEW 2022 or later
- TCP/IP connectivity for online play

## Getting Started

1. Open `othello.lvproj` in LabVIEW
2. Run `main.vi` to play locally or:
   - Run `server.vi` on the host machine
   - Run `client.vi` on the connecting machine

## Game Rules

Reversi (also known as Othello) is played on an 8×8 board with discs that are black on one side and white on the other.

- Players take turns placing discs on the board with their assigned color facing up
- To make a valid move, a player must place a disc such that it creates a straight line (horizontal, vertical, or diagonal) between the newly placed disc and another of their discs, with one or more of the opponent's discs in between
- All opponent's discs that are in this straight line are flipped to the current player's color
- If a player cannot make a valid move, their turn is skipped
- The game ends when neither player can make a valid move
- The player with the most discs of their color on the board wins

## Development

This project uses LabVIEW's native libraries for GUI rendering and TCP/IP communication for networking functionality.