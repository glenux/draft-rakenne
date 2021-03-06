# Entity-Relationship Diagrams - Domain Specific Language

## Goals

* Describe all possible cases according to MERISE
* Be simple to read and write by a human user
* Be simple to parse by a machine

## Example

```yaml
entities:
  user:
    name: "Utilisateur"
    properties:
      - name: id
        type: integer
        key: true
        options: ['autoincrement']
      - name: password_hash
        type: varchar
        limit: 250
      - name: role
        type: varchar
        limit: 10
      - name: created_at
        type: datetime
      - name: updated_at
        type: datetime
  url:
    name: "Adresses"
    properties:
      - name: id
        type: varchar
        limit: 250
        key: true
      - name: custom_id
        type: varchar
        limit: 250
      - name: source_url
        type: text
      - name: short_url
        type: varchar
        limit: 250
      - name: created_at
        type: datetime
      - name: updated_at
        type: datetime
      - name: expires_at
        type: datetime

relationships:
  manages_urls:
    name: "GereAdresse"
    links:
      - name: user: 
        equals: 1
      - name: url:
        min: 0
        max: n
    properties: []
```

## References

* [Petit cours de Modélisation, Christophe DARMANGEAT](http://pise.info/modelisation/)
