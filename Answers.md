# CSS 382 Search Project Answers

## Q1: Depth First Search
Implemented graph-search DFS in `search.py` using `util.Stack`.
- Fringe items store `(state, actions)`.
- Uses a visited set to avoid re-expanding states.
- Returns the first found goal path as a legal action list.

## Q2: Breadth First Search
Implemented graph-search BFS in `search.py` using `util.Queue`.
- Marks states visited when enqueued to prevent duplicate frontier entries.
- Guarantees minimum number of actions when step costs are uniform.

## Q3: Uniform Cost Search
Implemented UCS in `search.py` using `util.PriorityQueue`.
- Fringe items store `(state, actions, g)` where `g` is path cost.
- Priority is `g`.
- Uses a best-cost table to re-open/update states only when a cheaper path is found.

## Q4: A* Search
Implemented A* in `search.py` using `util.PriorityQueue`.
- Fringe items store `(state, actions, g)`.
- Priority is `g + h(state)`.
- Uses best-cost table to prune stale higher-cost entries.

## Q5: Corners Problem
Implemented `CornersProblem` in `searchAgents.py`.
- State representation: `(pacmanPosition, visitedCornersTuple)`.
- `visitedCornersTuple` is 4 booleans in fixed corner order.
- Goal test checks all corners visited.
- Successors update position and corner-visit flags.

## Q6: Corners Heuristic
Implemented `cornersHeuristic` in `searchAgents.py`.
- Computes the minimum path length to visit remaining corners in a relaxed space using Manhattan distances.
- Enumerates all permutations of unvisited corners (max 24 cases).
- Returns 0 at goal states.

## Q7: Food Heuristic
Implemented `foodHeuristic` in `searchAgents.py`.
- Heuristic value is the maximum maze distance from current position to any remaining food dot.
- Uses `problem.heuristicInfo` to cache pairwise maze distances across calls.
- Returns 0 when no food remains.

## Q8: Closest Dot Search
Implemented `findPathToClosestDot` and `AnyFoodSearchProblem.isGoalState` in `searchAgents.py`.
- `AnyFoodSearchProblem.isGoalState`: goal is any state containing food.
- `findPathToClosestDot`: solves `AnyFoodSearchProblem` with BFS and returns that action path.
