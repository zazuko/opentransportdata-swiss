## Updating the schema on LINDAS

Named-Graph: `https://lindas.admin.ch/sbb/otd-schema`


```
$ curl -i -X PUT -T otd-schema.ttl -u $SPARQL_USERPASS -H "Content-Type: text/turtle" $SPARQL_GSP_ENDPOINT?graph=https%3A%2F%2Flindas.admin.ch%2Fsbb%2Fotd-schema
```
