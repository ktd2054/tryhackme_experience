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

#### Analysis Tab

The Analysis tab contains the input entities referenced in reports, along with associated external references. Reports play a central role in OpenCTI, as they consolidate knowledge on threats and events that have been extracted, processed, and mapped within the platform. This enables analysts to quickly identify the source of information and assess its context.

In addition to the extracted data, analysts can enhance reports by adding investigation notes, attaching external resources, and linking related intelligence for knowledge enrichment.

To view report details, navigate to the Analysis tab and select a report from the list displayed on the left panel. This will open a detailed view of the report’s entities, relationships, and references.

#### Events

Definition: Recorded security-related occurrences, tied to incidents, campaigns, or intrusion sets.

Purpose: Acts as a timeline reference, connecting multiple entities such as threat actors, malware, and victims.

Example: A ransomware campaign launched in March 2025 targeting healthcare providers.

#### Observations

Definition: Technical artifacts or facts observed in the real world (STIX Cyber Observables).

Purpose: Serves as raw evidence for analysis, such as IPs, domains, hashes, or email headers.

Example: An IP address linked to a known command-and-control (C2) server.

#### Threats

Definition: Adversarial activities or actors capable of causing harm to an organization.

Purpose: Profiles adversaries, their tactics, motivations, and objectives.

Example: A financially motivated threat actor exploiting zero-day vulnerabilities.

#### Arsenal

Definition: Tools, malware, exploits, and attack techniques used by adversaries.

Purpose: Identifies attacker capabilities and predicts potential tactics.

Example: Use of Mimikatz for credential dumping.

#### Entities

Definition: Core objects in the OpenCTI knowledge graph (e.g., organizations, threat actors, malware, vulnerabilities).

Purpose: Serves as the building blocks for relationships and threat analysis.

Example: APT29 as a threat actor entity linked to specific campaigns and tools.

### OpenCTI Dashboard 2

- General Tabs Navigation

In day-to-day use, OpenCTI analysts navigate through different entities within the platform to explore and utilize threat intelligence for investigations.
For this walkthrough, we will examine the Cobalt Strike malware entity, commonly found under the Arsenal tab.

When we select an intelligence entity, its details are presented through several key tabs:

1. Overview Tab

-  Provides general information about the selected entity, including:
  
-  Entity ID and confidence level
  
-  Description and related context
  
-  Relationships with threats, intrusion sets, and attack patterns
  
- Reports mentioning the entity
  
-  Any external references


2. Knowledge Tab

-  Displays all linked information associated with the entity, such as:
  
-  Associated reports, indicators, and relationships
  
-  Attack pattern timeline
  
-  Detailed panels on the right-hand side covering threats, attack vectors, events, and observables connected to the entity


3. Analysis Tab

-  Lists reports where the entity has been observed.
  
-  Provides actionable intelligence about the threat
  
-  Assists in guiding investigation tasks


4. Indicators Tab

- Shows all Indicators of Compromise (IOCs) linked to the entity and related threats.

5. Data Tab

- Contains files uploaded or generated for export that relate to the entity.

- Useful for sharing information in technical or non-technical formats.

6. History Tab

- Tracks changes made to the entity’s attributes, relationships, and linked data.

- Updated automatically by platform workers for audit and traceability.
