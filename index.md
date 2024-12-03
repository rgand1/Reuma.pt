---
title: Home
layout: home
---

## Reuma.pt to OMOP CDM 5.4

```mermaid
graph LR
  %% Define styling for different groups
  classDef sourceStyle fill:#FFDDC1,stroke:#333,stroke-width:2px;   %% Light peach for Sources
  classDef cdmStyle fill:#C1E1FF,stroke:#333,stroke-width:2px;      %% Light blue for CDM Tables
  classDef stemStyle fill:#FFD700,stroke:#333,stroke-width:2px;     %% Gold color for Stem Table

  %% Define subgraphs (groups) for clarity
  subgraph Sources
    A[PatientData.csv]:::sourceStyle
    D[PatientDatesData.csv]:::sourceStyle
    F[VisitData.csv]:::sourceStyle
    G[SF36.csv]:::sourceStyle
  end

  subgraph CDM Tables
    B[person]:::cdmStyle
    E[observation_period]:::cdmStyle
    H[visit_occurrence]:::cdmStyle
    I[stem_table]:::stemStyle  %% Assigning stemStyle to stem_table
  end

  %% Define relationships between nodes
  A --> B
  D --> E
  F --> H
  G --> I
