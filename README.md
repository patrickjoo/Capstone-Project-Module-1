# Game Store Inventory & Sales System 

## 📌 Project Overview

This is a is a command-line-based application designed to help game store businesses manage their product data efficiently. The system provides essential features to add, view, update, delete, and sell games. This tool allows store owners or staff to monitor inventory and track sales without the need for complex software.

## Features

The system supports the following key functionalities, grouped by CRUD operations and transaction handling:

### Create (Add Game Data)
- Add new game records with required fields: ID, name, category, genre, stock, and price.
- Validate inputs for format and value (e.g., ID format, no negative stock/price).
- Prevent duplication of Game ID.
- Option to confirm before saving the new game to the database.

### Read (View Game Catalog)
- View all available games in a formatted table.
- Search game data by:
  - Game ID
  - Category (e.g., Nintendo, Playstation, Xbox)

### Update (Modify Game Data)
- Update any field (except Game ID) for a specific game.
- Input validation is enforced depending on the field type (numeric or alphabetic).
- Confirmation required before applying changes.

### Delete (Remove Game Data)
- Remove a game entry by ID.
- Preview game details before deletion.
- Confirmation prompt to avoid accidental removal.

### Sell (Process Game Transactions)
- Reduce stock based on sale quantity.
- Prevent over-selling by checking stock availability.
- Display total transaction amount and remaining stock.

## Business Understanding

Retail game stores often struggle with managing their inventory and tracking transactions efficiently, especially when relying on manual recordkeeping. This system simulates a lightweight digital solution for those stores, helping staff manage daily operations and improve accuracy in stock control and sales recording.

## Target Users

This application is intended for:
- Small to medium-sized game store owners and staff.
- Students or beginners learning Python who want to practice CRUD logic.
- Anyone building a simple inventory or sales tracking system in a terminal-based environment.

## Data Structure

The application uses a list of dictionaries to store game data. Each game entry follows this format:

```python
{
    "Id": "GN001",
    "Name": "Pokemon Legends Arceus",
    "Category": "Nintendo",
    "Genre": "Action RPG",
    "Stock": "25",
    "Price": "650000"
}

Accepted Categories:
- Nintendo
- Playstation
- Xbox
```
## Functional Breakdown
The system is modularized into several functions, each responsible for specific operations:

- `mainDashboard()`: Displays the main menu.
- `inputMenu()`: Receives user input.
- `addGame()`: Handles input, validation, and storage of new game data.
- `listGame()`: Shows all games.
- `gameById()`: Displays a game by its ID.
- `gameByCategory()`: Filters games by category.
- `updateGame()`: Edits a selected field of a game.
- `deleteGame()`: Deletes a game after confirmation.
- `sellGame()`: Handles sales transaction and reduces stock.
- `startMenu()`: Runs the main program loop.

## How to Use
  1. Save the Code: Save the Python source file as `Capstone Project_Patrick Jonathan.py`

  2. Open Terminal or Command Prompt: Navigate to the folder where the file is saved.

  3. Run the Program: Execute the program using the command:

## Menu Navigation
When the program runs, the user will be presented with this main menu:

  ==== GAME STORE MENU ====
  1. Add Game
  2. Game Catalog
  3. Update Game
  4. Delete Game
  5. Sell Game
  6. Exit

Each option leads to relevant submenus for more specific tasks.

## Flowchart
The following flowchart summarizes the flow of the program:

```mermaid 
graph TD
    A[Start Program] --> B{Run Loop};
    B --> C[Main Menu];
    C --> D{User Input};

    %% Add Game Flow
    D -- Add Game --> E[Add Game Sub-Menu];
    E --> E1[Input Game Data];
    E1 --> E2{Save Data?};
    E2 -- Yes --> E3[Save to List];
    E2 -- No --> E4[Cancel Add];
    E3 --> B;
    E4 --> B;

    %% View Game Catalog
    D -- Game Catalog --> F[Game Catalog Sub-Menu];
    F --> F1[Show All Games];
    F --> F2[Search by Game ID];
    F --> F3[Filter by Category];
    F1 --> B;
    F2 --> B;
    F3 --> B;

    %% Update Game Flow
    D -- Update Game --> G[Update Game Sub-Menu];
    G --> G1[Input Game ID];
    G1 --> G2{Game Found?};
    G2 -- No --> G3[Show Not Found];
    G2 -- Yes --> G4[Select Field to Edit];
    G4 --> G5[Input New Value];
    G5 --> G6{Confirm Update?};
    G6 -- Yes --> G7[Update Data];
    G6 -- No --> G8[Cancel Update];
    G3 --> B;
    G7 --> B;
    G8 --> B;

    %% Delete Game Flow
    D -- Delete Game --> H[Delete Game Sub-Menu];
    H --> H1[Input Game ID];
    H1 --> H2{Game Found?};
    H2 -- No --> H3[Show Not Found];
    H2 -- Yes --> H4{Confirm Delete?};
    H4 -- Yes --> H5[Delete Game];
    H4 -- No --> H6[Cancel Delete];
    H3 --> B;
    H5 --> B;
    H6 --> B;

    %% Sell Game Flow
    D -- Sell Game --> I[Sell Game Sub-Menu];
    I --> I1[Input Game ID];
    I1 --> I2{Game Found?};
    I2 -- No --> I3[Show Not Found];
    I2 -- Yes --> I4[Input Quantity];
    I4 --> I5{Enough Stock?};
    I5 -- No --> I6[Show Stock Error];
    I5 -- Yes --> I7{Confirm Sale?};
    I7 -- Yes --> I8[Reduce Stock & Show Total];
    I7 -- No --> I9[Cancel Sale];
    I3 --> B;
    I6 --> B;
    I8 --> B;
    I9 --> B;

    %% Exit & Invalid
    D -- Exit --> J[Exit Program];
    J --> K[End];

    D -- Invalid --> L[Show Invalid Input];
    L --> B;
```

## Author
Patrick Jonathan / patrickjoo
