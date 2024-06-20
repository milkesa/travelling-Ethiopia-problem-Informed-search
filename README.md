# travelling-Ethiopia-problem-Informed-search

Informed search algorithms
In this assignment I have tried to use three informed search algorithms to find the optimal path between Addis Ababa and Moyale. The three algorithms used are

Uniform cost search
Greedy search
A* search algorithms


=> I have used a list as data structure to store Ethiopian cities. 
=> I have used a dictionary to represent the cost of reaching a cities from the available 
   directions
=> I have also use dictionary to show the heuristic value of a certain city


Uniform Cost search

First I implemented Uniform Cost Search (UCS) algorithm using Python's heapq module to manage the priority queue. UCS is a variant of Dijkstra's algorithm, used for finding the least-cost path from a start node to a goal node in a weighted graph. The uniform_cost_search function takes three parameters: 

start (the starting node), 
goal (the goal node), and 
cost_dict (a dictionary representing the graph where keys are nodes and values are dictionaries of neighboring nodes and the cost to reach them). 

The algorithm initializes the open set (priority queue) with the start node and a cost of 0. It also initializes the came_from dictionary to track the path and the g_score dictionary to store the cost from the start node to each node, setting the cost to the start node as 0 and all other nodes as infinity. A visited set is used to keep track of explored nodes.

The main loop of the algorithm continues until the priority queue is empty. In each iteration, the node with the lowest cumulative cost is popped from the priority queue. If this node is the goal node, the path is reconstructed by tracing back through the came_from dictionary. If not, the algorithm explores all neighbors of the current node, updating the cumulative cost and path if a cheaper path is found. The updated cost and neighbor nodes are then pushed onto the priority queue. If the goal node is reached, the reconstructed path is returned. If the priority queue is exhausted without reaching the goal, the function returns None, indicating that the goal is not reachable. Additionally, the algorithm prints the set of visited nodes, which can be useful for debugging and understanding the search process.

 
Greedy search 

This Greedy Best-First Search (GBFS) algorithm using Python's heapq module to manage the priority queue. GBFS is a heuristic-based search algorithm that prioritizes nodes based on a heuristic estimate of the cost to reach the goal. In the code, the greedy_best_first_search function takes four parameters: start (the starting node), goal (the goal node), cost_dict (a dictionary representing the graph with nodes and their neighbors along with the cost to reach them), and heuristics (a dictionary that provides heuristic estimates for reaching the goal from each node). The algorithm initializes the priority queue with the start node, using its heuristic estimate as the priority. It also initializes the came_from dictionary to keep track of the path and a visited set to keep track of explored nodes.

The main loop of the algorithm continues until the priority queue is empty. In each iteration, the node with the smallest heuristic estimate is popped from the priority queue. If this node is the goal, the algorithm reconstructs the path by tracing back through the came_from dictionary. If the current node is not the goal, the algorithm explores all its neighbors. For each unvisited neighbor, the algorithm updates the came_from dictionary, pushes the neighbor onto the priority queue with its heuristic estimate, and marks the neighbor as visited. The process continues until the goal node is reached or the priority queue is exhausted. If the goal node is reached, the reconstructed path is returned. If the priority queue is exhausted without finding the goal, the function returns None, indicating that the goal is not reachable. Additionally, the algorithm prints the set of visited nodes, which provides insight into the nodes explored during the search process.

A* search Algorithm

The provided code implements the A* search algorithm using Python's heapq module to manage the priority queue. A* search is a widely used pathfinding and graph traversal algorithm that finds the shortest path from a start node to a goal node. It combines the features of Uniform Cost Search (UCS) and Greedy Best-First Search (GBFS) by using both the cost to reach a node and a heuristic estimate of the remaining cost to reach the goal.

In the code, the a_star_search function takes four parameters: start (the starting node), goal (the goal node), cost_dict (a dictionary representing the graph with nodes, their neighbors, and the cost to reach them), and heuristics (a dictionary providing heuristic estimates for reaching the goal from each node). The algorithm initializes the priority queue with the start node, using its f_score (g_score + heuristic) as the priority. It also initializes the came_from dictionary to keep track of the path, g_score to store the cost from the start node to each node, and f_score to store the estimated total cost from the start to the goal through each node. The visited set keeps track of explored nodes.

The main loop of the algorithm continues until the priority queue is empty. In each iteration, the node with the lowest f_score is popped from the priority queue. If this node is the goal, the algorithm reconstructs the path by tracing back through the came_from dictionary. If the current node is not the goal, the algorithm explores all its neighbors. For each neighbor, it calculates the tentative g_score for reaching the neighbor through the current node. If this tentative g_score is better (lower) than the previously known g_score, the path and scores are updated, and the neighbor is pushed onto the priority queue with its updated f_score. The neighbor is also marked as visited. The process continues until the goal node is reached or the priority queue is exhausted. If the goal node is reached, the reconstructed path is returned. If the priority queue is exhausted without finding the goal, the function returns None, indicating that the goal is not reachable. Additionally, the algorithm prints the set of visited nodes, providing insight into the nodes explored during the search process.



By Milkesa Kumera