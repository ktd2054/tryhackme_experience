## OpenCTI Introduction

According to TryHackMe.com, OpenCTI is another open-sourced platform designed to provide organisations with the means to manage CTI through the storage, analysis, visualisation and presentation of threat campaigns, malware and IOCs.
Developed by the collaboration of the French National cybersecurity agency (ANSSI), the platform's main objective is to create a comprehensive tool that allows users to capitalise on technical and non-technical information while developing relationships between each piece of information and its primary source. 

## OpenCTI Data Model

OpenCTI uses a STIX-based graph model to store, connect, and analyze cyber threat intelligence, with automation for deduplication, inference, and data governance, plus interactive tools for exploration.

STIX 2.1-based knowledge graph:
- Entities (nodes) = threat objects (e.g., malware, threat actors, IPs).
- Relationships (edges) = how entities are connected (e.g., “uses”, “targets”).

### Entity Types

- STIX Domain Objects (SDOs): Attack Patterns, Threat Actors, Malware, etc.
- STIX Cyber Observables (SCOs): IPs, domains, file hashes, etc.
- STIX Relationship Objects (SROs): Connects two entities (e.g., uses, associated-with).
- OpenCTI extensions: Extra entity types (e.g., disinformation, narratives, crypto wallets).

### Architecture Components

- GraphQL API – main interface to query/manage data.

- Workers – process and store data asynchronously.

- Connectors – ingest, enrich, and export CTI data.

### Data Intelligence Features

- Deduplication – auto-detect and merge duplicates.

- Merging – unify multiple entities into one.

- Confidence & Markings – TLP tags, trust levels, access control.

- Inference Rules – auto-create relationships and sightings.

### Exploration Tools

- Schema browser – explore available entity/relationship types.
- Graph visualizations – pivot across related entities for investigations.

### Summary Table

| Component                      | Purpose                                                                   |
| ------------------------------ | ------------------------------------------------------------------------- |
| **STIX-Based Graph**           | Core data model with rich entity and relationship representation.         |
| **GraphQL API**                | Querying, managing, and interacting with data.                            |
| **Workers & Connectors**       | Ingest, export, enrich, and process CTI data asynchronously.              |
| **Data Intelligence Features** | Deduplication, merging, marking, confidence control, and inference rules. |
| **Exploration Tools**          | Interactive schema browsing and investigative graph navigation.           |


## OpenCTI Labs

### OpenCTI Dashboard 1

After connecting to the OpenCTI web platform, the opening dashboard displays distinct visual widgets summarizing the data ingested into the system. These widgets highlight key metrics such as the total number of entities, relationships, reports, and observables, along with changes recorded within the last 24 hours.

On the left-hand sidebar, under the “Activities and Knowledge” section, OpenCTI organizes information into two main categories:

- Activities – Contains security incidents ingested into the platform, typically in the form of reports.

- Knowledge – Provides interconnected data about attacker tools, targeted victims, and the types of threat actors involved.

This structure allows users to quickly assess recent activity and navigate linked threat intelligence data for deeper analysis.

