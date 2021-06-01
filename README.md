# Database link
HTTP requests can be issued to [this](https://bakend-ai.herokuapp.com/) link.

# List of available requests 

## Score Result (prefix: <strong>/ai-module/</strong>)

This module communicates with the AI and Ingestion teams. We take from the Ingestion team a JSON containing an id, the title of a post and its content and we send to the AI team this data. 

We verifiy if the post is already in the database (its score has already been calculated) and if so, we just result the resulted JSON (id, title, content and score => result entity). If the post is not already in the database, then we send the JSON containing its details to the AI and they in turn calculate its value of truth (true, false or partially false). They generate this score via a python script that we run. We take the score, generate a result entity that has the post's details plus the score and then we send it back to the Ingestion team. 

# Other mentions

## POST request body format

```json
{
  "id": 1,
  "title" : "test title",
  "content": "test content"
}
```

# Authors: Brinzila Maria, Alexandra Serdenciuc
