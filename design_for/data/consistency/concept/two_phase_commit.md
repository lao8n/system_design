**Two-phase commit**

**How it works**: 2PC is a database protocol used to guarantee atomic transaction commit across multiple nodes i.e. either all nodes succeed or all nodes fail. Because 2PC is a blocking protocol a single node failure blocks progress until the node has recovered so it is not performant.