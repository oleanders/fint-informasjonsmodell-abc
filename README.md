# Fint Informasjonsmodell

## Definisjon av informasjonsmodell i YAML

### Kardinalitet/multiplisitet

#### Relasjoner

```yaml
  gyldighetsperiode:
    range: Periode          # 0..1

  navn:
    range: Personnavn
    required: true          # 1..1

  adresser:
    range: Adresse
    multivalued: true       # 0..*

  foreldre:
    range: Person
    multivalued: true
    required: true          # 1..*  
```

#### Felter med komplekse datatyper

```yaml
  postadresse: 
    range: Adresse
    inlined: true           # 0..1

  bostedsadresse: 
    range: Adresse
    inlined: true           
    required: true          # 1..1

  adresselinje: 
    range: Adresselinje
    multivalued: true
    inlined_as_list: true   # 0..*

  adresselinje2:
    range: Adresselinje
    multivalued: true
    inlined_as_list: true   
    required: true          # 1..*
```

### Utgått/deprecated

```yaml
  kommunenavn:
    range: string
    deprecated: Ikke i bruk. Bruk i stedet feltet kommune.
```

## Eksport 

### Mermaid-diagrammer

Må gjøres per fil.

```bash
gen-mermaid-class-diagram --directory ./diagrams src/felles.yaml
```

### Dokumentasjon

```bash
gen-doc --directory ./docs --include-top-level-diagram --diagram-type er_diagram src/felles.yaml
```

## Oppsett av utviklingsmiljø

### om ikke python er på plass

```bash
brew install pipx
pipx ensurepath
```

### Installere LinkML

```bash
pipx install linkml
pipx ensurepath
```

### Verktøy som blir tilgjengelig

- gen-csv
- gen-dbml
- gen-doc
- gen-erdiagram
- gen-excel
- gen-golang
- gen-golr-views
- gen-graphql
- gen-graphviz
- gen-java
- gen-json-schema
- gen-jsonld
- gen-jsonld-context
- gen-linkml
- gen-markdown
- gen-mermaid-class-diagram
- gen-namespaces
- gen-owl
- gen-pandera
- gen-plantuml
- gen-prefix-map
- gen-project
- gen-proto
- gen-py-classes
- gen-pydantic
- gen-python
- gen-rdf
- gen-rust
- gen-shacl
- gen-shex
- gen-sparql
- gen-sqla
- gen-sqlddl
- gen-sqltables
- gen-sssom
- gen-summary
- gen-terminusdb
- gen-typescript
- gen-yaml
- gen-yuml
- linkml
- linkml-convert
- linkml-jsonschema-validate
- linkml-lint
- linkml-run-examples
- linkml-schema-fixer
- linkml-sparql-validate
- linkml-sqldb
- linkml-validate
- run-tutorial


## Andre verktøy

Kan dette brukes til noe? https://github.com/cimug-org/CIMTool?tab=readme-ov-file