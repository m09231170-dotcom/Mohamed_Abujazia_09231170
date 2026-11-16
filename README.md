# CS453 - Individual AI Project: Campus Delivery Agent

**Name:** Mohamed Muftah Abu jazia
**Student ID:** 09231170
**GitHub username:** <YOUR_GITHUB_USERNAME>
**Project choice:** Campus Delivery Agent

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/<YOUR_GITHUB_USERNAME>/<YOUR_REPO_NAME>/blob/main/project.ipynb)

> Replace the placeholders above with your real username, repository name and branch (main or master).
> This repository is private; the professor (`AliElzaileek`) was invited as a collaborator.

## Assigned variant
- Student ID sum of character codes mod 4: **v = 3**
- Closed road: **E-G**
- Start: **S**, target building: **D**

## Files
- `project.ipynb`: the full workbook (Tasks 1, 2, 4, 5, 6, 10, 11)
- `README.md`: this file
- `docs/`, `references/`: supplied course material (unchanged)

## Dependencies and how to run
Python 3 standard library only (`copy`, `collections`, `heapq`, `itertools`). No GPU, paid API or extra files.
1. Open `project.ipynb` in Google Colab (badge above, or File > Open notebook > GitHub).
2. Runtime > Restart session and run all.
3. Check the printed variant and the BFS / A* mission outputs.

## Progress
- Task 1: PEAS and environment classification
- Task 2: state = (location, delivered), legal actions, transitions, goal, costs
- Task 4: simulator (legal moves, delivery only at the target, clear errors for illegal actions)
- Task 5: BFS with FIFO queue, repeated-state tracking, route reconstruction
- Task 6: A* with priority queue, g+h, best-cost tracking, goal test on removal

## Algorithm summary
- **BFS** (uninformed): expands level by level, so with unit-cost roads the first route found has the fewest moves. Result: S -> A -> D (2 moves).
- **A*** (informed): orders by f = g + h using the supplied heuristic table for target D. h is admissible because it holds distances of the original graph and removing a road cannot shorten any distance. Result: S -> A -> D (2 moves), expanding fewer nodes than BFS.
- After each route the simulator executes the moves and the delivery, ending in state `("D", True)`.

## Sources
- Supplied CS453 two-week workbook (graph, variant helper, heuristic table) and the course graph-search / informed-search STUDENT notebooks.
- Russell & Norvig, *Artificial Intelligence: A Modern Approach* (BFS, A*).

## AI assistance disclosure
Tool: Claude (Anthropic). Help: task explanation and a draft of the code and explanations. Verification: ran in a fresh Colab session, checked the variant and results by hand, tested illegal actions and edge cases
