# Experiment 11(e): Adjacency List Representation of a Graph

## Aim
To write a Python program to demonstrate the adjacency list representation of a given graph.

---

## Algorithm

1. **Create a Node Class**:
   - Define a class `AdjNode` to represent each node in the adjacency list:
     - Store the vertex number.
     - Store a reference to the next adjacent node.

2. **Graph Class**:
   - Define a class `Graph` to represent the graph using an adjacency list:
     - Initialize the number of vertices and create an array to store the adjacency lists.
   
3. **Add an Edge**:
   - Define a method `add_edge(src, dest)` to add an edge between two vertices:
     - Add `dest` to the adjacency list of `src`.
     - Add `src` to the adjacency list of `dest` (for undirected graphs).
   
4. **Print the Graph**:
   - Define a method `print_graph()` to print the graph:
     - Traverse each vertex’s adjacency list and print the vertex along with its adjacent nodes.

5. **Main Program**:
   - Create a graph object with `V` vertices.
   - Add edges using the `add_edge()` method.
   - Print the adjacency list representation using `print_graph()`.

---

## Program

```
"""
A Python program to demonstrate the adjacency
list representation of the graph
"""

# A class to represent the adjacency list of the node


class AdjNode:
	def __init__(self, data):
		self.vertex = data
		self.next = None


# A class to represent a graph. A graph
# is the list of the adjacency lists.
# Size of the array will be the no. of the
# vertices "V"
class Graph:
	def __init__(self, vertices):
		self.V = vertices
		self.graph = [None] * self.V

	# Function to add an edge in an undirected graph
	def add_edge(self, src, dest):
		# Adding the node to the source node
		node = AdjNode(dest)
		node.next = self.graph[src]
		self.graph[src] = node

		# Adding the source node to the destination as
		# it is the undirected graph
		node = AdjNode(src)
		node.next = self.graph[dest]
		self.graph[dest] = node

	
	def print_graph(self):
	    for i in range(self.V):
	        print("Adjacency list of vertex {}\n head".format(i),end=" ")
	        temp=self.graph[i]
	        while temp:
	            print("-> {}".format(temp.vertex),end=" ")
	            temp=temp.next
	        print("\n")



# Driver program to the above graph class
if __name__ == "__main__":
	V = 5
	graph = Graph(V)
	graph.add_edge(0, 1)
	graph.add_edge(0, 4)
	graph.add_edge(1, 2)
	graph.add_edge(1, 3)
	graph.add_edge(1, 4)
	graph.add_edge(2, 3)
	graph.add_edge(3, 4)

	graph.print_graph()


```

## OUTPUT
<img width="911" height="478" alt="image" src="https://github.com/user-attachments/assets/c9129ac2-4ee1-4c9e-8940-cfd07f64bf1a" />

## RESULT

Thus , the Python program for demonstrating the adjacency list representation of the given graph is verified and executed successfully.
