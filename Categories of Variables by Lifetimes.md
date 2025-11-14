*Implicit Heap-Dynamic* --> Allocations

Meemorruy

```mermaid
flowchart TB

subgraph stuff
	stack(Stack Segment)
	data(Data Segment)
	code(Code Segment)
end

heap(Heap Segment)<-->stuff
```

