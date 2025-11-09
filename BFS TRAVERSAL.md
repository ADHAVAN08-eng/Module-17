# Experiment 11(b): BFS Traversal

## Aim
To write a Python program to print the BFS (Breadth-First Search) traversal from a given source vertex in a graph.

---

## Algorithm

1. **Start the program**:
   - Create a graph using an adjacency list representation.
   - Add edges between vertices using the `addEdge()` function.

2. **Implement the BFS function**:
   - Initialize all vertices as not visited.
   - Use a queue to track the vertices for traversal.
   - Mark the starting vertex as visited and enqueue it.
   - Dequeue a vertex, process it, and enqueue all its adjacent unvisited vertices while marking them as visited.

3. **Input**:
   - The user provides the starting vertex for the BFS traversal.

4. **Perform BFS traversal**:
   - Start from the given source vertex and traverse all reachable vertices using BFS.
   - Print the vertices in the BFS order.

5. **End the program**:
   - The program outputs the order of vertices visited during the BFS traversal.

---

## Program

```

# Python3 Program to print BFS traversal
# from a given source vertex. BFS(int s)
# traverses vertices reachable from s.
from collections import defaultdict

# This class represents a directed graph
# using adjacency list representation
class Graph:

	# Constructor
	def __init__(self):

		# default dictionary to store graph
		self.graph = defaultdict(list)

	# function to add an edge to graph
	def addEdge(self,u,v):
		self.graph[u].append(v)

	# Function to print a BFS of graph
	def BFS(self, s):

		# Mark all the vertices as not visited
		visited = [False] * (max(self.graph) + 1)

		# Create a queue for BFS
		queue = []

		# Mark the source node as
		# visited and enqueue it
		queue.append(s)
		visited[s] = True

		while queue:
		    
		    s=queue.pop(0)
		    print(s,end=" ")
		    
		    for i in self.graph[s]:
		        if visited[i]==False:
		            queue.append(i)
		            visited[i]=True
# Create a graph given in
# the above diagram
n=int(input())
g = Graph()
g.addEdge(0, 1)
g.addEdge(0, 2)
g.addEdge(1, 2)
g.addEdge(2, 0)
g.addEdge(2, 3)
g.addEdge(3, 3)

print ("Following is Breadth First Traversal"
				" (starting from vertex {})".format(n))
g.BFS(n)


```

## OUTPUT
<img width="1135" height="248" alt="image" src="https://github.com/user-attachments/assets/e3266910-1162-4272-8dc7-13b83963fced" />


## RESULT
Thus, the Python program to print BFS traversal from a given source vertex is verified and executed successfully.
