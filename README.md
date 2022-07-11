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


```
library(DiagrammeR)
library(DiagrammeRsvg)
library(rsvg)

result<-
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
    
         label = 'aaa'
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

result%>% export_svg %>% charToRaw %>% rsvg_pdf("graph1.pdf")


result<-add_mathjax(
  grViz("digraph{

      graph[rankdir = LR]
      subgraph cluster_0 {
        graph[shape = rectangle]
        style = rounded
        bgcolor = LemonChiffon
    
        label = '$s_m^*$'
        node[shape = rectangle, fillcolor = PaleGreen, style=filled]
        S1[label = '$s_1$']
        S2[label = '...']
        node[shape = rectangle, fillcolor = White, style=filled]
        S3[label = '...']
        node[shape = rectangle, fillcolor = PaleGreen, style=filled]
        S4[label = '...']
        node[shape = rectangle, fillcolor = White, style=filled]
        S5[label = '...']
        S6[label = '...']
        node[shape = rectangle, fillcolor = PaleGreen, style=filled]
        S8[label = '...']
        
        node[shape = rectangle, color=LemonChiffon, fillcolor = LemonChiffon, style=filled]
        S7[label = '......']
        
        {rank = same; S2; S3;}
        
        S1 -> S2
        S1 -> S3
        S2 -> S4
        S3 -> S5
        S3 -> S6
        S4 -> S7
        S7 -> S8
        
      }
      
      node[shape = rectangle, fillcolor = PaleGreen, style=filled]
      S9[label='$s_{m+1}$']
      node[shape = rectangle, fillcolor = White, style=filled]
      S10[label='...']
      S11[label='...']
      
            
      edge[color = black, arrowhead = vee, arrowsize = 1.25]
      S8->{S9 S10 S11}
    }"))

result

result%>% export_svg %>% charToRaw %>% rsvg_pdf("graph1.pdf")


export_graph(result,
             file_name="result.pdf",
             file_type="pdf")


```





```
library(DiagrammeR)
library(DiagrammeRsvg)
library(rsvg)

result<-
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
    
         label = 'aaa'
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

result%>% export_svg %>% charToRaw %>% rsvg_pdf("graph1.pdf")

###########
# m state #
###########

result<-add_mathjax(
  grViz("digraph{

      graph[rankdir = LR]
      subgraph cluster_0 {
        graph[shape = rectangle]
        style = rounded
        bgcolor = LemonChiffon
    
        label = '$s_m^*$'
        node[shape = rectangle, fillcolor = PaleGreen, style=filled]
        S1[label = '$s_1$']
        S2[label = '...']
        node[shape = rectangle, fillcolor = White, style=filled]
        S3[label = '...']
        node[shape = rectangle, fillcolor = PaleGreen, style=filled]
        S4[label = '...']
        node[shape = rectangle, fillcolor = White, style=filled]
        S5[label = '...']
        S6[label = '...']
        node[shape = rectangle, fillcolor = PaleGreen, style=filled]
        S8[label = '...']
        
        node[shape = rectangle, color=LemonChiffon, fillcolor = LemonChiffon, style=filled]
        S7[label = '......']
        
        {rank = same; S2; S3;}
        
        S1 -> S2
        S1 -> S3
        S2 -> S4
        S3 -> S5
        S3 -> S6
        S4 -> S7
        S7 -> S8
        
      }
      
      node[shape = rectangle, fillcolor = PaleGreen, style=filled]
      S9[label='$s_{m+1}$']
      node[shape = rectangle, fillcolor = White, style=filled]
      S10[label='...']
      S11[label='...']
      
            
      edge[color = black, arrowhead = vee, arrowsize = 1.25]
      S8->{S9 S10 S11}
    }"))

result

htmltools::html_print(result)
result%>%export_svg()

###################
# 5 state pulling #
###################

result<-grViz("digraph{
      graph[rankdir = LR]
      subgraph cluster_1 {
        graph[shape = rectangle]
        style = rounded
        bgcolor = LemonChiffon
        label = 'New State (State 0*)'
        
        node[shape = rectangle, fillcolor = PaleGreen, style=filled]
        S0[label = 'State 0']
        node[shape = rectangle, fillcolor = PaleGreen, style=filled]
        S2[label = 'State 2']
        node[shape = rectangle, fillcolor = White, style=filled]
        S1[label = 'State 1']
        
        S0 -> S2
        S0 -> S1
      }
      
      node[shape = rectangle, fillcolor = PaleGreen, style=filled]
      S3[label = 'State 3']
      node[shape = rectangle, fillcolor = White, style=filled]
      S4[label = 'State 4']
        
      S2 -> S3
      S2 -> S4
    }")

result%>%export_svg %>% charToRaw %>% rsvg_pdf("5state_pulling.pdf")


result<-grViz("digraph{
      graph[rankdir = LR]

      node[shape = rectangle, fillcolor = PaleGreen, style=filled]
      S0[label = 'State 0']
      node[shape = rectangle, fillcolor = White, style=filled]
      S1[label = 'State 1']
      node[shape = rectangle, fillcolor = PaleGreen, style=filled]
      S2[label = 'State 2']
        
      S0 -> S1
      S0 -> S2
      
      node[shape = rectangle, fillcolor = PaleGreen, style=filled]
      S3[label = 'State 3']
      node[shape = rectangle, fillcolor = White, style=filled]
      S4[label = 'State 4']
        
      S2 -> S3
      S2 -> S4
    }")

result
result%>%export_svg %>% charToRaw %>% rsvg_pdf("5state.pdf")

```
