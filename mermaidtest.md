```mermaid
flowchart LR
    START[Start] --> 1[Read From Mongo]
    
    %% Setup Section
    subgraph 1 [Setup<br/>ABCD-12456]
        direction LR
        READA[<a href='/mermaidtest2.md'>works</a>] --> GETC[Get Doc]
    end
    
    1 -->  ABC
    
    %%
    subgraph ABC [Action]
        IS{SEC Exists?} --> |YES| DEL[Delete The UNI]
        IS --> |NO| WRITE[Write the updated Doc]
        DEL --> WRITE
    end

    WRITE --> END[End]
```
