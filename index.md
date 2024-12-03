---
title: Home
layout: home
---

## Reuma.pt to OMOP CDM 5.4

```mermaid
graph LR
  %% Define styling for different groups
  classDef sourceStyle fill:#FFDDC1,stroke:#333,stroke-width:2px;
  classDef cdmStyle fill:#C1E1FF,stroke:#333,stroke-width:2px;
  classDef stemStyle fill:#FFD700,stroke:#333,stroke-width:2px;

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
    I[stem_table]:::stemStyle
  end

  %% Define relationships between nodes
  A --> B
  D --> E
  F --> H
  G --> I
