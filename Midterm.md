Chapters 1, 3, 4
Question for history of programming languages history.
Language criteria
Grammars
Regular Expressions
Go program

Sentence Definition: A sentence is anything that the grammar generates.


```chartsview
#-----------------#
#- chart type    -#
#-----------------#
type: WordCloud

#-----------------#
#- chart data    -#
#-----------------#
data: |
  dataviewjs:
  return dv.pages()
           .flatMap(p => p.file.etags)
           .groupBy(p => p)
           .map(p => ({tag: p.key, count: p.rows.length}))
           .array();

#-----------------#
#- chart options -#
#-----------------#
options:
  wordField: "tag"
  weightField: "count"
  colorField: "count"
  wordStyle:
    rotation: 30
  enableSearchInteraction:
    operator: tag
```
