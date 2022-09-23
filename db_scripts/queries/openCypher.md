#### Query1
```
Match (m:Movie) where m.released > 2000 RETURN m limit 5
```
#### Query2
```
Match (m:Movie) where m.released > 2005 RETURN m
```
#### Query3
```
Match (m:Movie) where m.released > 2005 RETURN count(m)
```

#### Query4
```
MATCH (p:Person)-[d:DIRECTED]-(m:Movie) where m.released > 2010 RETURN p,d,m
```

#### Query5
```
MATCH (p:Person)-[d:ACTED_IN]-(m:Movie) where m.released > 2010 RETURN p,d,m
```

#### Query6
```
MATCH (p:Person) RETURN p limit 20
```

#### Query7
```
MATCH (n) RETURN n limit 20
```

#### Query8
```
MATCH (m:Movie) return m.title, m.released
```

#### Query9
```
MATCH (p:Person) return p.name, p.born
```

#### Query10
```
Create (p:Person {name: 'John Doe'}) RETURN p
```

#### Query11
```
Create (p:Person {name: 'John Doe'}) RETURN p
```

#### Query12
```
Match (p:Person {name: 'Tom Hanks'}) RETURN p
```

#### Query13
```
MATCH (p:Person) where p.name = "Tom Hanks" RETURN p
```

#### Query14
```
MATCH (m:Movie {title: "Cloud Atlas"}) return m
```

#### Query15
```
MATCH (m:Movie) where m.released > 2010 and m.released < 2015 RETURN m
```

#### Query16
```
MERGE (p:Person {name: 'John Doe'})
ON MATCH SET p.lastLoggedInAt = timestamp()
ON CREATE SET p.createdAt = timestamp()
Return p
```

#### Query17
```
MERGE (m:movie {title: 'Greyhound'})
ON MATCH SET m.lastUpdatedAt = timestamp()
ON CREATE SET m.released = "2020", m.lastUpdatedAt = timestamp()
Return m
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
MATCH (p:Person)-[r:ACTED_IN]->(m:Movie) RETURN p,r,m
```

#### Query21
```
MATCH (p:Person)-[r:ACTED_IN]-(m:Movie) RETURN p,r,m
```

#### Query22
```
MATCH (p:Person)-[r:REVIEWED]-(m:Movie) return p,r,m
```

#### Query23
```
MATCH (m:Movie {title: 'Cloud Atlas'})<-[d:DIRECTED]-(p:Person) return p.name
```

#### Query24
```
MATCH (tom:Person {name: "Tom Hanks"})-[:ACTED_IN]->(:Movie)<-[:ACTED_IN]-(p:Person) return p.name
```

#### Query25
```
MATCH (p:Person)-[relatedTo]-(m:Movie {title: "Cloud Atlas"}) return p.name, type(relatedTo)
```

#### Query26
```
MATCH (p:Person {name: 'Kevin Bacon'})-[*1..3]-(hollywood) return DISTINCT p, hollywood
```