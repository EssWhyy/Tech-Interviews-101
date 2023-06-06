<frontmatter>
  title: Graphs
  layout: default.md
  pageNav: 4
  pageNavTitle: "Topics"
</frontmatter>

<br>

## Graphs

Another very common topic tested in Leetcode is graphs. Graphs build upon arrays by introducing 2 dimensions, and having relations between elements/nodes.

### General Structure
Most undirected graphs in Leetcode questions can be modelled as a simple 2D-array or matrix. Which can then be queried by: arr["row"]["col"]

Nodes can be represented by numbers with state:
- 0: Not Visited
- 1: Visited in previous cycle
- -1: Visited in this cycle (used for DFS)

We can then express directions in the graph as such:
```
python
a,b,dis = queue.popleft()
for row,col in [(a,b-1),(a,b+1),(a-1,b),(a+1,b)]: #4-directional matrix
    #[(a,b-1),(a,b+1),(a-1,b),(a+1,b),(a+1,b+1),(a+1,b-1),(a-1,b+1),(a-1,b-1)] 8-directional matrix
    
    if 0<=row<m and 0<=col<n and visited[row][col]==0:
        visited[row][col]=1
        distance[row][col]=dis+1
        queue.append([row,col,distance[row][col]])
```

Its important to define the matrix bounds at the start, in the above example, m and n are the bounds for the rows and cols respectively.


### Breadth First Search

Breadth First Search uses a queue structure (FIFO) to iterate through frontiers in a graph.

- *Time Complexity:  O(V+E)
- *Space Complexity: O()

Pseudocode for BFS is as follows:
```
python
def bfs(visited, graph, node): #function for BFS
  visited.append(node)
  queue.append(node)

  while queue:          # Creating loop to visit each node
    m = queue.pop(0) 
    print (m, end = " ") 

    for neighbour in graph[m]:
      if neighbour not in visited:
        visited.append(neighbour)
        queue.append(neighbour)

```

### Depth First Search
Depth First Search uses the idea of backtracking to traverse through a graph. 
It uses a stack instead of a queue.

DFS has the same (worst case) time complexity as DFS at O(V+E), however it is slightly better for cases where the target/end node is far away from the start node.

```
python
visited = set() # Set to keep track of visited nodes of graph.

def dfs(visited, graph, node):  #function for dfs 
    if node not in visited:
        print (node)
        visited.add(node)
        for neighbour in graph[node]:
            dfs(visited, graph, neighbour)
```

### Directed Acyclic Graph and Topological Sort

Some graphs may have directed edges. In this case, one possible way to model such directed graphs is using a dictionary format / adjacency list:

```
python
graph = {
    'a': ['b', 'e'],
    'b': ['c', 'd'],
    'd': ['e']
}
```

One question that comes up is: "How do we know if the directed graph has a cycle?"
We can use DFS to detect cycles iteratively:

```
python
def dfs(x):
	vis[x] = -1
	for y in digraph[x]:
		if vis[y] == -1 or (vis[y] == 0 and not dfs(y)):
			return False
	vis[x] = 1
	return True
	
for i in range(numCourses):
	if vis[i] == 0 and not dfs(i): return False
return True
```

We can also use Topologcial sort, a graph without cycles will have at least one topological sorted order.

```

```

### Shortest Path Algorithm

For unweighted graphs, we can simply use BFS to get the shortest path.
(see above), just keep track of the distance while recursing.

For weighted graphs with no negative weight cycles, we need to use Dijkstra's algorithm. Say we have a start node n, Dijkstra first assigns an infinite weight to each node, then iteratively reduces the weight based on the 

```
python


```

### Minimum Spanning Trees

