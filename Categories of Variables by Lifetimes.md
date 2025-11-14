*Implicit Heap-Dynamic* --> Allocations

Meemorruy

```mermaid
flowchart TB

subgraph sdf
	stack(Stack Segment)
	data(Data Segment)
	code(Code Segment)

heap(Heap Segment)<-->sdf
```
