# diagrammer_examples

```
grViz("digraph{

      graph[rankdir = LR]
  
      node[shape = rectangle, style = filled]
  
      node[fillcolor = Coral, margin = 0.2]
      A[label = 'Figure 1: Map']
      B[label = 'Figure 2: Metrics']
  
      node[fillcolor = Cyan, margin = 0.2]
      C[label = 'Figures.Rmd']
  
      node[fillcolor = Violet, margin = 0.2]
      D[label = 'Analysis_1.R']
      E[label = 'Analysis_2.R']
  
      subgraph cluster_0 {
        graph[shape = rectangle]
        style = rounded
        bgcolor = Gold
    
        label = 'Data Source 1'
        node[shape = rectangle, fillcolor = LemonChiffon, margin = 0.25]
        F[label = 'my_dataframe_1.csv']
        G[label = 'my_dataframe_2.csv']
      }
  
      subgraph cluster_1 {
         graph[shape = rectangle]
         style = rounded
         bgcolor = Gold
    
         label = 'Data Source 2'
         node[shape = rectangle, fillcolor = LemonChiffon, margin = 0.25]
         H[label = 'my_dataframe_3.csv']
         I[label = 'my_dataframe_4.csv']
      }
  
      edge[color = black, arrowhead = vee, arrowsize = 1.25]
      C -> {A B}
      D -> C
      E -> C
      F -> D
      G -> D
      H -> E
      I -> E
      
      }")
```
https://cyberhelp.sesync.org/blog/visualization-with-diagrammeR.html

```
library(DiagrammeR)

my_graphviz <- grViz(
  "
  digraph{
    graph[rankdir = LR]
                     
    node[shape = rectangle, style = filled]  
    A[label = 'A']
    B[label = 'B']
    C[label = 'C']
    D[label = 'D']
    E[label = 'E']

    edge[color = black]
    B -> A
    C -> B
    A -> D
    D -> E
    A -> E
    C -> E
  }
  ")

my_graphviz

```
pdf
```
my_graph2 %>% export_svg %>% charToRaw %>% rsvg_pdf("graph2.pdf",width=300,height=200)
```
