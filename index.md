---
title: Home
layout: home
---

## Reuma.pt to OMOP CDM 5.4

```mermaid
graph LR
  subgraph Sources
    A[PatientData.csv]
    D[PatientDatesData.csv]
    F[VisitData.csv]
    G[SF36.csv]
  end
  
  subgraph CDM Tables
    B[person]
    E[observation_period]
    H[visit_occurrence]
    I[stem_table]
  end
  
  A --> B
  D --> E
  F --> H
  G --> I
