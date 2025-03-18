# Datamodel

In this page inlined below are overview diagrams that are manually curated.

For more details and accuracy, have a look at the documentation generated from the SHACL shapes:
- [didok-shapes](https://zazuko.github.io/opentransportdata-swiss/didok-shapes.html)
- [nova-shapes](https://zazuko.github.io/opentransportdata-swiss/nova-shapes.html)


*(Above links point to documentation generated from the SHACL shapes using [SHACL Play!](https://shacl-play.sparna.fr/play/doc) )*


## Atlas (Didok)

```mermaid
---
  config:
    class:
      hideEmptyMembersBox: true
---
classDiagram
    direction LR    

    Station -- "1" Organization : provider

    style Station fill:lightgray
    style Organization fill:lightgray
```


## Verbund

```mermaid
---
  config:
    class:
      hideEmptyMembersBox: true
---
classDiagram
    direction LR
    
    LocalNetwork -- Zoningplan
    
    Zoningplan -- "1" Alliance
    Zoningplan -- "*" Tarif
    
    Zone -- "1" Organization : provider
    Zone -- "1" Alliance
    Zone "*" --* Zoningplan
    Zone -- "*" PayLevel

    PayLevel "*" -- "1" Tarif
    PayLevel -- "*" LocalNetwork
    Tarif -- "1" Organization : provider

    ZoningPriceCharacteristic -- "*" CustomerSegment
    
    TransportEdge "*" o-- "2" Station : stop
    TransportEdge "*" -- "*" Zone
    TransportEdge "*" -- "*" Anwendungsbereich
    TransportEdge -- "*" PayLevel
    TransportEdge "*" -- "*" LocalNetwork
    TransportEdge "*" -- "*" Zoningplan

    Station -- Organization : provider

    style Station fill:lightgray
    style Organization fill:lightgray
```


## Direkter Verkehr (DV)

```mermaid
---
  config:
    class:
      hideEmptyMembersBox: true
---
classDiagram
    direction LR
    Relationsgebiet "*" -- "1" Organization : provider
    Relationsgebiet "*" -- "1" Preistabelle    

    Relation "*" o-- "2" Station : stop
    Relation "*" -- "1" Relationsgebiet

    Station -- Organization : provider
    
    VorberechnetePreistabelle --|> Preistabelle
    VorberechnetePreistabelle  *-- "*" Tarifwertpreisauspraegung

    Tarifwertpreisauspraegung "*" -- "*" CustomerSegment

    style Station fill:lightgray
    style Organization fill:lightgray
```