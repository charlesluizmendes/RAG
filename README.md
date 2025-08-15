# MongoDB Atlas

## Atlas Local:

Para acessar terminal do container e o MongoDB Atlas, execute os comandos abaixo:

```
CMD> docker exec -it [ID do Container Docker do Mongo] bash  
```

```
CLI> mongosh
```

Agora para a criação dos Vetores de Busca, utilize o JSON abaixo:

### OpenAI:

```
use seu_database

db.sua_collection.createSearchIndex({
  name: "vector_index",
  type: "vectorSearch",
  definition: {
    "fields": [
      {
        "type": "vector",
        "path": "embedding",
        "numDimensions": 1536,
        "similarity": "cosine"
      },
      {
        "type": "filter",
        "path": "id"
      }
    ]
  }
})
```

### HuggingFace:

```
use seu_database

db.sua_collection.createSearchIndex({
  name: "vector_index",
  type: "vectorSearch",
  definition: {
    "fields": [
      {
        "type": "vector",
        "path": "embedding",
        "numDimensions": 768,
        "similarity": "cosine"
      },
      {
        "type": "filter",
        "path": "id"
      }
    ]
  }
})
```

## Atlas Cloud:

Para criação dos Vetores de Busca no Atlas Cloud, acesse as opcoes abaixo:

Cluster > Browse Collection >
Atlas Search > Create Search Index >
Vector Search > [Selecione o Database e Collection] > JSON Editor > Next

Em seguida inseira o JSON abaixo:

### OpenAI:

```
{
  "fields": [
    {
      "type": "vector",
      "path": "embedding",
      "numDimensions": 1536,
      "similarity": "cosine"
    },
    {
      "type": "filter",
      "path": "id"
    }
  ]
}
```

### HuggingFace:

```
{
  "fields": [
    {
      "type": "vector",
      "path": "embedding",
      "numDimensions": 768,
      "similarity": "cosine"
    },
    {
      "type": "filter",
      "path": "id"
    }
  ]
}
```