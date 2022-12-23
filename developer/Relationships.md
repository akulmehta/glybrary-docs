# Glybrary Relationships

## Overview
This figure gives an overview of how Glybrary is organized. To make the visualization easier, not all relationships are shown.

```mermaid
erDiagram
%% Mermaid ER diagram can be used to visualize all relationships in Glybrary
  Probe ||--|| Glycoconjugate : "can be" %% polymorphic one-to-one
  Probe ||--|| Linker : "can be" %% polymorphic one-to-one
  Glycoconjugate }o--|{ Linker : "has" %% polymorphic many-to-many
  Glycoconjugate }o--|{ Glycan : "has" %% polymorphic many-to-many
  Probe ||--|| ProteinProbe : "can be" %% polymorphic one-to-one
  ProteinProbe }o--o{ Glycan : "can have" %% polymorphic many-to-many
  Probe ||--|| OtherTypes : "can be" %% polymorphic one-to-one
  Probe }|--o{ Result : "can have" %% many-to-many
  Result ||--o{ DataFile : "can have" %% one-to-many
  Probe }|--o{ PrintRun : "can be" %% many-to-many
  PrintRun }o--o{ Experiment : "can have" %% many-to-many
  Experiment ||--|{ Result : "has" %% one-to-many
```

## Probe Relationships to Probeables

A **Probe** is anything which can be physically placed in a tube or container.

This can be of various types as shown below. Each type in turn captures a unique set of other data to characterize 

```mermaid
erDiagram
%% Mermaid ER diagram can be used to visualize all relationships in Glybrary
  Probe ||--|| Glycoconjugate : "can be" %% polymorphic one-to-one
  Probe ||--|| Linker : "can be" %% polymorphic one-to-one
  Probe ||--|| ProteinProbe : "can be" %% polymorphic one-to-one
  Probe ||--|| Antibody : "can be" %% polymorphic one-to-one
  Probe ||--|| ChemicalProbe : "can be" %% polymorphic one-to-one
  Probe ||--|| Antibody : "can be" %% polymorphic one-to-one
  Probe ||--|| Biospecimen : "can be" %% polymorphic one-to-one
```
