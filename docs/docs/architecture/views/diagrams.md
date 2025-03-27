# Diagrams

## Mermaid embedded

```mermaid
sequenceDiagram
    Alice->>John: Hello John, how are you?
    John-->>Alice: Great!
    Alice-)John: See you later!

```

## PlantUML embedded

```puml
@startuml
title: PlantUML sequence diagram
Alice -> Bob: Authentication Request
Bob --> Alice: Authentication Response
@enduml
```

## PlantUML external

!!! warning "External PlantUML files are not supported"

    Please note that loading puml from external files is not supported yet.
    Kudos to `mkdocs_puml` plugin: they are [planning](https://github.com/MikhailKravets/mkdocs_puml/issues/89) to enhance it.

```
--8<-- "context.puml"
```

![context diagram](context.png)
