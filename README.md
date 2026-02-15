# modelagem-grafo-streaming
Modelagem de dados em grafos para serviço de streaming usando Neo4j
# Modelagem de Dados em Grafos – Serviço de Streaming

Este projeto apresenta a modelagem de dados em grafos para um serviço de streaming utilizando o Neo4j.

## Entidades (Nós)
- User
- Movie
- Series
- Genre
- Actor
- Director

## Relacionamentos
- WATCHED (com propriedade rating)
- ACTED_IN
- DIRECTED
- IN_GENRE

## Implementação
A modelagem foi realizada em uma instância local do Neo4j Desktop, com criação dos nós e relacionamentos utilizando a linguagem Cypher.
```cypher
MATCH (n) DETACH DELETE n;

CREATE (u:User {name: "João"});
CREATE (m:Movie {title: "Inception", year: 2010});
CREATE (s:Series {title: "Dark", year: 2017});
CREATE (g:Genre {name: "Sci-Fi"});
CREATE (a:Actor {name: "Leonardo DiCaprio"});
CREATE (d:Director {name: "Christopher Nolan"});

CREATE (u)-[:WATCHED {rating: 5}]->(m);
CREATE (u)-[:WATCHED {rating: 4}]->(s);
CREATE (a)-[:ACTED_IN]->(m);
CREATE (d)-[:DIRECTED]->(m);
CREATE (m)-[:IN_GENRE]->(g);
CREATE (s)-[:IN_GENRE]->(g);
