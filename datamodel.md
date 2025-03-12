# Datamodel

In this page inlined below are overview diagrams that are manually curated.

For more details and accuracy, have a look at the documentation generated from the SHACL shapes:
- [didok-shapes](https://zazuko.github.io/opentransportdata-swiss/didok-shapes.html)
- [nova-shapes](https://zazuko.github.io/opentransportdata-swiss/nova-shapes.html)


*(Above links point to documentation generated from the SHACL shapes using [SHACL Play!](https://shacl-play.sparna.fr/play/doc) )*


## Atlas

```mermaid
---
  config:
    class:
      hideEmptyMembersBox: true
---
classDiagram
    direction LR    

    Station -- Organization : provider

    style Station fill:lightgray
    style Organization fill:lightgray
```


## Zoning

```mermaid
---
  config:
    class:
      hideEmptyMembersBox: true
---
classDiagram
    direction TB
    
    LocalNetwork -- Zoningplan
    
    Zoningplan -- Alliance
    Zoningplan -- Tarif
    
    Zone -- Zoningplan
    Zone -- Alliance
    Zone -- Organization : provider
    Zone -- PayLevel

    PayLevel -- Tarif
    Tarif -- Organization : provider

    ZoningPriceCharacteristic -- CustomerSegment
    
    Relation -- Zoningplan
    Relation -- Zone
    Relation "*" o-- "2" Station : stop

    Station -- Organization : provider

    style Station fill:lightgray
    style Organization fill:lightgray
```

## RTM

```mermaid
---
  config:
    class:
      hideEmptyMembersBox: true
---
classDiagram
    direction LR
    DvRelationsgebiet "*" -- "1" Organization : provider
    DvRelationsgebiet "*" -- "1" DvPreistabelle

    DvRelation "*" -- "1" DvRelationsgebiet

    DvRelation "*" o-- "2" Station : stop

    Station -- Organization : provider
    
    class DvRelationsgebiet {
        String label
        String klassenTyp
        int nummer
        int linienCode
    }

    class DvPreistabelle {
        String label
        String anstossTyp
    }

    class DvRelation {
        int tarifwert
        int effektiveKilometer
        int priority
    }

    style Station fill:lightgray
    style Organization fill:lightgray
```