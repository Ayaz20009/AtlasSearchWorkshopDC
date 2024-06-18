# AtlasSearchWorkshopDC


## $search
```
{
  index: 'movie_index',
  text: {
    'query': 'new yark',
    'path': 'title',
    'fuzzy': {
      'maxEdits': 2,
      'prefixLength': 0
      }
  },
  'highlight': { "path": 'title' }
}
```
## $project
```
{
   'document': "$$ROOT",
   'highlights': {"$meta": "searchHighlights"},
   'score': {
     '$meta': 'searchScore'
     }
}
```
## $match
```
{"document.poster": {'$ne': null}}
```
## $limit
```
15
```
## $sort
```
{"score": -1}
```
