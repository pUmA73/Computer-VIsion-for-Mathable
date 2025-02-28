# Computer-VIsion-for-Mathable
Computer vision project that extracts information from pictures of mathable game board

# Tasks
Three tasks were achieved in this project. The given input images represent a sequence of pieces placed during a game, one new piece added every image (note: input images are not provided in this repo).

- Task 1: detect the cell in which every new piece is placed
- Task 2: detect the number on the new piece
- Task 3: calculate scores based on a turns.txt file

# Implementation

- For the first task, the HSV color space is used to retain only the white squares in the grid, which are then enclosed by a bounding box to extract only the grid from the images. A perspective shift is applied to minimize differences between images.
<img width="534" alt="image" src="https://github.com/user-attachments/assets/84e6b2b3-7654-40c3-af64-39681304f5c8" />

- For the second task, the HSV color space is used to extract only the pieces from the images. A difference is made between the masks obtained using HSV extraction. Several filters are applied to remove artifacts—especially in cases where the pieces are placed on the edge of the grid, causing differences between the lines of the cells. The largest contour after processing is taken as the area where the piece is placed. The centroid of the selected area is calculated and enclosed within a cell.

- For the third task, two matrices are used: one for the board structure, which stores the restrictions for operations and applicable bonuses, and another for the pieces placed on the board during the game. Scores are generated for each piece, which are then used to calculate the score for each player's row.
<img width="349" alt="image" src="https://github.com/user-attachments/assets/805da43f-0339-44c0-9437-1de111f3571a" />

# Note

The "images" and "templates" folders have to be created manually, as the code only creates the "results", "output_images", and "templates_processed" folders automatically.
The folder structure should look something like this.

<img width="211" alt="image" src="https://github.com/user-attachments/assets/4cb79efd-5be5-493a-a61d-bb3b7399006e" />




