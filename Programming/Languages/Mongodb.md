Default port 27017
```Bash
db
show collections
show dbs
use [dbname]


insertOne()
find()
db.movies.find({title: 'Christmas'})


```
### Code
``` Bash
load('file.js')
config.get('editor')
config.set('editor', 'vim')
edit cube # functionName
```
#### JS Code
```Javascript
db = db.getSlidingDB('sample_training')
let result = db.posts.aggregate({
  $sample : { size: 1},
})
print(result.next().body)

```
### Insert multiple files with mongofiles in cmd windows
```Bash
for %f in (animaux_chunk_00*) do mongofiles --uri "mongodb+srv://user:password@cluster.fyc3y6f.mongodb.net/" -d dbname put "%f"
```
### Linux
![[Pasted image 20250817083231.png]]
![[Pasted image 20250817083315.png]]
![[Pasted image 20250817083337.png]]