# Chess-Unique-legal-positions

This folder is for generating the datasets. The chess board positions are generated by following Kryukov Method. All the illegal positions are then eliminated from the dataset. The perfect play information for the generated legal positions are stored in a mysql database.

- Create container and install the prerequisites from the `Dockerfile`
- Write the name of the n-pieces combination to generate dataset
- Execute `run.sh` file to generate dataset and store in a mysql database

# Analyze_Lc0_move_selection

The positions from the mysql database are passed to the game engines and the results are compared with the perfect play information stored in the same database. Each position's dataset is divided into two new dataset (for example KQkq_draw and KQkq_win) and saved in the `samples` folder. The two new kinds are obtained based on `WDL_score="W"` and `"WDL_score="D"`. The mistakes for only the policies are stored in `failing_stockfish` and `failing_lc0` respectively. The mistakes for search depth=400 are stored in `failing_stockfish_400` and `failing_lc0_400`. Later on, pawn analysis and multiPV analysis are done to observe interesting behaviors from the engine.

- Create container and install the prerequisites from the `Dockerfile`
- Write the name of the n-pieces combination to obtain moves predictions
- Execute `run.sh` file to obtain the mistaken positions, pawn analysis result and multiPV analysis result
# CMPUT657-Project
