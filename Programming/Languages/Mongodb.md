### Insert multiple files with mongofiles in cmd windows
```Bash
for %f in (animaux_chunk_00*) do mongofiles --uri "mongodb+srv://user:password@cluster.fyc3y6f.mongodb.net/" -d dbname put "%f"
```
