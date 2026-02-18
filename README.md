# Red Project - Strategic Rock Paper Scissors

A command-line interface (CLI) game developed in Go (Golang) that reinvents the classic Rock-Paper-Scissors by adding RPG elements, an economy system, and strategic combat mechanics.

## Project Overview

In this game, the player faces a computer opponent in a duel to the death. Unlike the traditional game, this version introduces a health point (HP) system and a strategic shop. Players start with a budget of 1000 gold coins to purchase potions that can alter the outcome of the match. The goal is to reduce the opponent's HP to zero using a combination of standard moves and special items.

## Game Mechanics

### 1. The Economy & Shop
Before combat begins, the player accesses a shop to spend their starting budget (1000 coins). Strategic resource management is key, as purchased potions are the only way to gain an advantage during the duel.

**Available Potions:**
- **Red Potion (150 coins)**: Heals the player for 15 HP.
- **Blue Potion (200 coins)**: Increases damage dealt by 15 points if the player wins the next round.
- **Poison Potion (250 coins)**: Inflicts 5 damage to the opponent for 3 consecutive turns.
- **Vengeance Potion (400 coins)**: Reflects all incoming damage back to the opponent for the current turn.
- **Clairvoyance Potion (500 coins)**: Allows the player to predict the opponent's move on the next turn. A correct prediction deals massive damage (50 HP).

### 2. Combat Rules
The combat proceeds in rounds. In each round, both the player and the computer choose a sign.

**Damage Values:**
- **Rock**: Beats Scissors and deals 12 damage.
- **Scissors**: Beats Paper and deals 11 damage.
- **Paper**: Beats Rock and deals 10 damage.
- **Draw**: No damage is inflicted.

### 3. Strategy
At the start of each turn, the player can choose to use an item from their inventory or attack directly. The computer also has its own inventory generated randomly based on the same budget constraints and can use potions against the player.

## Technical Structure

The project is organized into modular packages to separate logic, user interface, and data management.

- **main.go**: The entry point of the application. It orchestrates the game flow (setup, shop, combat).
- **outils/**: A custom package containing the core game functions.
  - **clear.go**: Utility to clear the terminal screen for a cleaner UI.
  - **menu.go**: Handles the main menu display and user selection.
  - **perso.go**: Defines the `Perso` structure (Player/AI attributes) and initialization logic.
  - **inventaire.go**: Manages the shop interface and the AI's inventory generation algorithm.
  - **combat.go**: Contains the main game loop, including move resolution, potion effects, and win/loss conditions.

## Installation and Run

### Prerequisites
- Go installed (version 1.25 or higher).

### Steps
1. Clone the repository or download the source code.
2. Open a terminal in the project directory.
3. Run the game using the following command:

```bash
go run main.go
