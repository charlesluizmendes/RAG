# MongoDB Atlas

## Atlas Vector Search:

Para criando o Vetor de Busca no Atlas Mongo DB para o OpenAI:

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

Para criando o Vetor de Busca no Atlas Mongo DB para o HuggingFace:

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