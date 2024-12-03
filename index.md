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
    G1[SF36.csv]:::sourceStyle
    G2[ProData.csv]:::sourceStyle
    G3[ClinicalData.csv]:::sourceStyle
    G4[ConditionData.csv]:::sourceStyle
    G5[DemographicsData.csv]:::sourceStyle
    G6[DiseaseActivityData.csv]:::sourceStyle
  end

  subgraph CDM Tables
    B[person]:::cdmStyle
    E[observation_period]:::cdmStyle
    H[visit_occurrence]:::cdmStyle
    I[stem_table]:::stemStyle
    C1[condition_occurrence]:::cdmStyle
    C2[measurement]:::cdmStyle
    C3[observation]:::cdmStyle
  end

  %% Define relationships between nodes
  A --> B
  D --> E
  F --> H

  %% Map all relevant sources to stem_table
  G1 --> I
  G2 --> I
  G3 --> I
  G4 --> I
  G5 --> I
  G6 --> I

  %% Map stem_table to other CDM tables
  I --> C1
  I --> C2
  I --> C3
