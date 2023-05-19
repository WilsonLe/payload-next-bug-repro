# Reproduce Bug

1. Edit `.env` file with an empty mongo database
2. Create **more than** 22 documents of in `Examples` collection
3. Create a document in `Users` collection with more than 22 documents in `Examples`
4. The error should occur in the terminal:

```
[09:09:45] ERROR (payload): CastError: Cast to ObjectId failed for value "{
  '0': '64673cbe7b43c50c05008b9b',
  '1': '64673cbe7b43c50c05008ba5',
  '2': '64673cbc7b43c50c05008b73',
  '3': '64673cbd7b43c50c05008b91',
  '4': '64673cbc7b43c50c05008b7d',
  '5': '64673cbb7b43c50c05008b69',
  '6': '64673cb97b43c50c05008b55',
  '7': '64673cb27b43c50c05008b48',
  '8': '64673cba7b43c50c05008b5f',
  '9': '64673cbd7b43c50c05008b87',
  '10': '64673cbe7b43c50c05008baf',
  '11': '64673cbf7b43c50c05008bb9',
  '12': '64673cbf7b43c50c05008bc3',
  '13': '64673cbf7b43c50c05008bcd',
  '14': '64673cc07b43c50c05008bd7',
  '15': '64673cc07b43c50c05008be1',
  '16': '64673cc17b43c50c05008beb',
  '17': '64673cc17b43c50c05008bf5',
  '18': '64673cc27b43c50c05008bff',
  '19': '64673cc27b43c50c05008c09',
  '20': '64673cc27b43c50c05008c13',
  '21': '64673cc37b43c50c05008c1d'
}" (type Object) at path "_id" for model "examples"
    at model.Query.exec (webpack-internal:///(api)/./node_modules/mongoose/lib/query.js:4155:23)
    at Function.paginate (/Users/wilsonle/tmp/my-app/node_modules/mongoose-paginate-v2/dist/index.js:158:51)
    at find (webpack-internal:///(api)/./node_modules/payload/dist/collections/operations/find.js:106:30)
    at runMicrotasks (<anonymous>)
    at processTicksAndRejections (node:internal/process/task_queues:96:5)
    at async handler (webpack-internal:///(api)/./node_modules/@payloadcms/next-payload/dist/handlers/[collection]/index.js:37:36)
```
