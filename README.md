# Magical-Grid-Check

In the land of puzzles, Veer was given a square grid of characters with side length N, where N is an odd number. Veer was tasked with determining if the grid was magical. A grid is considered magical if all the characters on both diagonals are the same, and all other characters not on the diagonals are identical but different from the diagonal character. Can you help Veer figure out whether the grid is magical or not?

Input
The first line of the input contains integer N.
Each of the next N lines contain N lowercase English latin characters.

Constraints
3 ≤ N ≤ 500
Note: N is odd.
Output
Print "YES" if the given grid is magical, else print "NO", without the quotes.

def is_magical_grid():
    # Input reading
    N = int(input())
    grid = [input().strip() for _ in range(N)]

    # Characters to check
    diagonal_char = grid[0][0]
    non_diagonal_char = None

    # Traverse the grid
    for i in range(N):
        for j in range(N):
            if i == j or i + j == N - 1:  # Diagonal positions
                if grid[i][j] != diagonal_char:
                    print("NO")
                    return
            else:  # Non-diagonal positions
                if non_diagonal_char is None:
                    non_diagonal_char = grid[i][j]
                elif grid[i][j] != non_diagonal_char:
                    print("NO")
                    return

    # Ensure diagonal and non-diagonal characters are different
    if diagonal_char == non_diagonal_char:
        print("NO")
    else:
        print("YES")

# Call the function
is_magical_grid()
