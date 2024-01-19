---
layout: project
type: project
image: img/sudoku3 crop.jpg
title: "Sudoku Solver"
date: 2023
published: true
labels:
  - Java
  - Recursion
summary: "A Sudoku solver from ICS 211."
---

The assignment focuses on implementing and testing a Sudoku-solving algorithm in Java, employing recursive backtracking. The given code includes a `checkSudoku()` method to validate the adherence of a 9x9 Sudoku array to the game rules. The main objective is to complete the `fillSudoku()` method, which uses recursive backtracking to systematically fill empty cells with values 1 to 9, checking the validity of each placement through the `checkSudoku()` method. The algorithm aims to find a solution by exploring potential values for each empty cell and backtracking if necessary. The assignment emphasizes understanding and applying recursion to solve Sudoku puzzles efficiently, with the goal of creating a functional and effective algorithm for puzzle solving.

## Rules of Sudoku 
<hr>
1. The puzzle is played on a 9x9 grid, which is further divided into 9 3x3 sub-grids.
2. The puzzle initially contains some cells that are already filled with numbers, called "givens".
3. The objective is to fill in the empty cells with numbers from 1 to 9, such that every row, column, and sub-grid contains all of the numbers from 1 to 9.
4. No number can be repeated in the same row, column, or sub-grid.
<hr>

Here's the code:

```cpp
public class Sudoku {

	public static boolean checkSudoku(int[][] sudoku, boolean printErrors) {
		if (sudoku.length != 9) {
			if (printErrors) {
				System.out.println("sudoku has " + sudoku.length + " rows, should have 9");
			}
			return false;
		}
		for (int i = 0; i < sudoku.length; i++) {
			if (sudoku[i].length != 9) {
				if (printErrors) {
					System.out.println("sudoku row " + i + " has " + sudoku[i].length + " cells, should have 9");
				}
				return false;
			}
		}

		for (int i = 0; i < sudoku.length; i++) {
			for (int j = 0; j < sudoku.length; j++) {
				int cell = sudoku[i][j];
				if (cell == 0) {
					continue;
				}
				if ((cell < 1) || (cell > 9)) {
					if (printErrors) {
						System.out.println("sudoku row " + i + " column " + j + " has illegal value " + cell);
					}
					return false;
				}
				for (int m = 0; m < sudoku.length; m++) {
					if ((j != m) && (cell == sudoku[i][m])) {
						if (printErrors) {
							System.out.println("sudoku row " + i + " has " + cell + " at both positions " + j + " and " + m);
						}
						return false;
					}
				}
				for (int k = 0; k < sudoku.length; k++) {
					if ((i != k) && (cell == sudoku[k][j])) {
						if (printErrors) {
							System.out.println("sudoku column " + j + " has " + cell + " at both positions " + i + " and " + k);
						}
						return false;
					}
				}
				for (int k = 0; k < 3; k++) {
					for (int m = 0; m < 3; m++) {
						int testRow = (i / 3 * 3) + k;
						int testCol = (j / 3 * 3) + m;
						if ((i != testRow) && (j != testCol) && (cell == sudoku[testRow][testCol])) {
							if (printErrors) {
								System.out.println("sudoku character " + cell + " at row " +
										i + ", column " + j +
										" matches character at row " + testRow +
										", column " + testCol);
							}
							return false;
						}
					}
				}
			}
		}
		return true;
	}

	public static String toString(int[][] sudoku, boolean debug) {
		if ((!debug) || (checkSudoku(sudoku, true))) {
			String result = "";
			for (int i = 0; i < sudoku.length; i++) {
				if (i % 3 == 0) {
					result = result + "+-------+-------+-------+\n";
				}
				for (int j = 0; j < sudoku.length; j++) {
					if (j % 3 == 0) {
						result = result + "| ";
					}
					if (sudoku[i][j] == 0) {
						result = result + "  ";
					} else {
						result = result + sudoku[i][j] + " ";
					}
				}
				result = result + "|\n";
			}
			result = result + "+-------+-------+-------+\n";
			return result;
		}
		return "illegal sudoku";
	}

	public static boolean fillSudoku(int[][] sudoku) {
		return sudokuHelper(sudoku, 0, 0);
	}

	public static boolean sudokuHelper(int[][] sudoku, int row, int col) {
		if (row == 8 && col == 9) {
			return true;
		}
		if (col == 9) {
			col = 0;
			row++;
		}
		if (sudoku[row][col] == 0) {
			for (int i = 1; i <= 9; i++) {
				if (isValid(sudoku, row, col, i)) {
					sudoku[row][col] = i;
					if (sudokuHelper(sudoku, row, col + 1))
						return true;
					else
						sudoku[row][col] = 0;
				}
			}
		} else {
			return sudokuHelper(sudoku, row, col + 1);
		}
		return false;
	}

	public static boolean isValid(int[][] sudoku, int row, int col, int numToCheck) {
		for (int i = 0; i < 9; i++) {
			if (sudoku[row][i] == numToCheck) {
				return false;
			}
		}
		for (int j = 0; j < 9; j++) {
			if (sudoku[j][col] == numToCheck) {
				return false;
			}
		}
		int checkRow = row - (row % 3);
		int checkCol = col - (col % 3);
		for (int i = checkRow; i < checkRow + 3; i++) {
			for (int j = checkCol; j < checkCol + 3; j++) {
				if (sudoku[i][j] == numToCheck) {
					return false;
				}
			}
		}
		return true;
	}
}
```

The provided Java code defines a Sudoku class with methods to check the validity of a Sudoku puzzle, convert it to a printable string, and fill in the missing values to solve the puzzle. The `checkSudoku()` method verifies if a given Sudoku adheres to the rules, checking for conflicts in rows, columns, and 3x3 subgrids. The `toString()` method converts the Sudoku to a printable string format. The `fillSudoku` method is a recursive function that attempts to find a valid solution for the puzzle, using a helper function `sudokuHelper()` to explore possible assignments. The `isValid()` function checks if a specific value assignment at a given position is valid according to Sudoku rules. The goal is to fill in the Sudoku grid while ensuring that the rules are satisfied, and the solution is stored in the original Sudoku array if found.
