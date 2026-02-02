

This problem exercises the basic concepts of game playing, using
tic-tac-toe (noughts and crosses) as an example. We define
$X_n$ as the number of rows, columns, or diagonals with exactly $n$
$X$’s and no $O$’s. Similarly, $O_n$ is the number of rows, columns, or
diagonals with just $n$ $O$’s. The utility function assigns $+1$ to any
position with $X_3=1$ and $-1$ to any position with $O_3 = 1$. All other
terminal positions have utility 0. For nonterminal positions, we use a
linear evaluation function defined as ${Eval}(s) = 3X_2(s) + X_1(s) -
(3O_2(s) + O_1(s))$. <br>

1.  Approximately how many possible games of tic-tac-toe are there?<br>

    $2$ states at terminal for each of $2\times 2$ grid cell. $\therefore$
    we have $2^9 = 512$ games possible.
    

3.  Show the whole game tree starting from an empty board down to depth
    2 (i.e., one $X$ and one $O$ on the board), taking symmetry
    into account.<br>

| Level 0             | Level 1                 | Level 2                 |
|--------|--------|--------|
|        |                          | `X O _ / _ _ _ / _ _ _`      |
|        |                          | `X _ O / _ _ _ / _ _ _`      |
|        |                          | `X _ _ / O _ _ / _ _ _`      |
|        |                          | `X _ _ / _ O _ / _ _ _`      |
|        | `X _ _ / _ _ _ / _ _ _`  | `X _ _ / _ _ O / _ _ _`      |
|        |                          | `X _ _ / _ _ _ / O _ _`      |
|        |                          | `X _ _ / _ _ _ / _ O _`      |
|        |                          | `X _ _ / _ _ _ / _ _ O`      |
|        |                          | `O X _ / _ _ _ / _ _ _`      |
|        |                          | `_ X O / _ _ _ / _ _ _`      |
|        |                          | `_ X _ / O _ _ / _ _ _`      |
|        |                          | `_ X _ / _ O _ / _ _ _`      |
|        | `_ X _ / _ _ _ / _ _ _`  | `_ X _ / _ _ O / _ _ _`      |
|        |                          | `_ X _ / _ _ _ / O _ _`      |
|        |                          | `_ X _ / _ _ _ / _ O _`      |
|        |                          | `_ X _ / _ _ _ / _ _ O`      |
|        |                          | `O _ X / _ _ _ / _ _ _`      |
|        |                          | `_ O X / _ _ _ / _ _ _`      |
|        |                          | `_ _ X / O _ _ / _ _ _`      |
|        |                          | `_ _ X / _ O _ / _ _ _`      |
|        | `_ _ X / _ _ _ / _ _ _`  | `_ _ X / _ _ O / _ _ _`      |
|        |                          | `_ _ X / _ _ _ / O _ _`      |
|        |                          | `_ _ X / _ _ _ / _ O _`      |
|        |                          | `_ _ X / _ _ _ / _ _ O`      |
|        |                          | `O _ _ / X _ _ / _ _ _`      |
|        |                          | `_ O _ / X _ _ / _ _ _`      |
|        |                          | `_ _ O / X _ _ / _ _ _`      |
|        |                          | `_ _ _ / X O _ / _ _ _`      |
| `_ _ _ / _ _ _ / _ _ _`       | `_ _ _ / X _ _ / _ _ _`  | `_ _ _ / X _ O / _ _ _`      |
|        |                          | `_ _ _ / X _ _ / O _ _`      |
|        |                          | `_ _ _ / X _ _ / _ O _`      |
|        |                          | `_ _ _ / X _ _ / _ _ O`      |
|        |                          | `O _ _ / _ X _ / _ _ _`      |
|        |                          | `_ O _ / _ X _ / _ _ _`      |
|        |                          | `_ _ O / _ X _ / _ _ _`      |
|        |                          | `_ _ _ / O X _ / _ _ _`      |
|        | `_ _ _ / _ X _ / _ _ _`  | `_ _ _ / _ X O / _ _ _`      |
|        |                          | `_ _ _ / _ X _ / O _ _`      |
|        |                          | `_ _ _ / _ X _ / _ O _`      |
|        |                          | `_ _ _ / _ X _ / _ _ O`      |
|        |                          | `O _ _ / _ _ X / _ _ _`      |
|        |                          | `_ O _ / _ _ X / _ _ _`      |
|        |                          | `_ _ O / _ _ X / _ _ _`      |
|        |                          | `_ _ _ / O _ X / _ _ _`      |
|        | `_ _ _ / _ _ X / _ _ _`  | `_ _ _ / _ O X / _ _ _`      |
|        |                          | `_ _ _ / _ _ X / O _ _`      |
|        |                          | `_ _ _ / _ _ X / _ O _`      |
|        |                          | `_ _ _ / _ _ X / _ _ O`      |
|        |                          | `O _ _ / _ _ _ / X _ _`      |
|        |                          | `_ O _ / _ _ _ / X _ _`      |
|        |                          | `_ _ O / _ _ _ / X _ _`      |
|        |                          | `_ _ _ / O _ _ / X _ _`      |
|        | `_ _ _ / _ _ _ / X _ _`  | `_ _ _ / _ O _ / X _ _`      |
|        |                          | `_ _ _ / _ _ O / X _ _`      |
|        |                          | `_ _ _ / _ _ _ / X O _`      |
|        |                          | `_ _ _ / _ _ _ / X _ O`      |
|        |                          | `O _ _ / _ _ _ / _ X _`      |
|        |                          | `_ O _ / _ _ _ / _ X _`      |
|        |                          | `_ _ O / _ _ _ / _ X _`      |
|        |                          | `_ _ _ / O _ _ / _ X _`      |
|        | `_ _ _ / _ _ _ / _ X _`  | `_ _ _ / _ O _ / _ X _`      |
|        |                          | `_ _ _ / _ _ O / _ X _`      |
|        |                          | `_ _ _ / _ _ _ / O X _`      |
|        |                          | `_ _ _ / _ _ _ / _ X O`      |
|        |                          | `O _ _ / _ _ _ / _ _ X`      |
|        |                          | `_ O _ / _ _ _ / _ _ X`      |
|        |                          | `_ _ O / _ _ _ / _ _ X`      |
|        |                          | `_ _ _ / O _ _ / _ _ X`      |
|        | `_ _ _ / _ _ _ / _ _ X`  | `_ _ _ / _ O _ / _ _ X`      |
|        |                          | `_ _ _ / _ _ O / _ _ X`      |
|        |                          | `_ _ _ / _ _ _ / O _ X`      |
|        |                          | `_ _ _ / _ _ _ / _ O X`      |



4.  Mark on your tree the evaluations of all the positions at depth 2.<br>

    <img width="1429" height="2286" alt="image" src="https://github.com/user-attachments/assets/403caa0e-6799-4674-ab2f-4248f61a8802" />

5.  Using the minimax algorithm, mark on your tree the backed-up values
    for the positions at depths 1 and 0, and use those values to choose
    the best starting move.<br>

    <img width="267" height="427" alt="image" src="https://github.com/user-attachments/assets/31cbbf9e-ae0c-4c99-abaf-70a0e847962d" />


7.  Circle the nodes at depth 2 that would <i>not</i> be
    evaluated if alpha–beta pruning were applied, assuming the nodes are
    generated in the optimal order for alpha–beta pruning.<br>

    <img width="800" height="1280" alt="image" src="https://github.com/user-attachments/assets/2f5252b7-e1ae-48be-999d-410b4c39fcd8" />

