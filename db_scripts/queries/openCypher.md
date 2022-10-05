#### Query1
```
Match (m:Movie) 
WHERE m.released > 2000 
RETURN m limit 5
```
#### Query2
```
Match (m:Movie) 
WHERE m.released > 2005 
RETURN m
```
#### Query3
```
Match (m:Movie) 
WHERE m.released > 2005 
RETURN count(m)
```

#### Query4
```
MATCH (p:Person)-[d:DIRECTED]-(m:Movie) 
WHERE m.released > 2010 
RETURN p,d,m
```

#### Query5
```
MATCH (p:Person)-[d:ACTED_IN]-(m:Movie)
WHERE m.released > 2010 
RETURN p,d,m
```

#### Query6
```
MATCH (p:Person) 
RETURN p 
LIMIT 20
```

#### Query7
```
MATCH (n) 
RETURN n 
LIMIT 20
```

#### Query8
```
MATCH (m:Movie) 
RETURN m.title, m.released
```

#### Query9
```
MATCH (p:Person) 
RETURN p.name, p.born
```

#### Query10
```
CREATE (p:Person {name: 'John Doe'}) 
RETURN p
```

#### Query11
```
CREATE (p:Person {name: 'John Doe'}) 
RETURN p
```

#### Query12
```
MATCH (p:Person {name: 'Tom Hanks'}) 
RETURN p
```

#### Query13
```
MATCH (p:Person) 
WHERE p.name = "Tom Hanks" 
RETURN p
```

#### Query14
```
MATCH (m:Movie {title: "Cloud Atlas"}) 
RETURN m
```

#### Query15
```
MATCH (m:Movie) 
WHERE m.released > 2010 and m.released < 2015 
RETURN m
```

#### Query16
```
MERGE (p:Person {name: 'John Doe'})
ON MATCH SET p.lastLoggedInAt = timestamp()
ON CREATE SET p.createdAt = timestamp()
RETURN p
```

#### Query17
```
MERGE (m:movie {title: 'Greyhound'})
ON MATCH SET m.lastUpdatedAt = timestamp()
ON CREATE SET m.released = "2020", m.lastUpdatedAt = timestamp()
RETURN m
```

#### Query18
```
MATCH (p:Person), (m:Movie)
WHERE p.name = "Tom Hanks" and m.title = "Cloud Atlas"
CREATE (p)-[w:WATCHED]->(m)
RETURN type(w)
```

#### Query19
```
MATCH (p:Person), (m:Movie)
WHERE p.name = "<Your Name>" and m.title = "Cloud Atlas"
CREATE (p)-[w:WATCHED]->(m)
RETURN type(w)
```

#### Query20
```
MATCH (p:Person)-[r:ACTED_IN]->(m:Movie) 
RETURN p,r,m
```

#### Query21
```
MATCH (p:Person)-[r:ACTED_IN]-(m:Movie) 
RETURN p,r,m
```

#### Query22
```
MATCH (p:Person)-[r:REVIEWED]-(m:Movie) 
RETURN p,r,m
```

#### Query23
```
MATCH (m:Movie {title: 'Cloud Atlas'})<-[d:DIRECTED]-(p:Person) 
RETURN p.name
```

#### Query24
```
MATCH (tom:Person {name: "Tom Hanks"})-[:ACTED_IN]->(:Movie)<-[:ACTED_IN]-(p:Person) 
RETURN p.name
```

#### Query25
```
MATCH (p:Person {name: 'Kevin Bacon'})-[*1..3]-(hollywood) 
RETURN DISTINCT p, hollywood
```
