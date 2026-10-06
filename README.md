# Universal Agentic Semantics (UAS) Engine

Deterministic compiler infrastructure converting high-entropy, unstructured source material into mathematically weighted, graph-addressable XML topology for autonomous LLM ingestion, knowledge graph synthesis, and Retrieval-Augmented Generation (RAG) pipelines.

---

## 1. System Overview

The UAS Engine establishes a formal Intermediate Representation (IR) between unstructured source texts and agent reasoning contexts. Under the core governing directive of the system, raw source text is treated as an immutable byte sequence: the compiler never mutates raw content, instead wrapping it within explicit semantic topology, assigning mathematical cognitive weights, building concept namespaces, and binding graph edges with closed categorical typing.

```
Raw Source Stream ───► [Entropy Assessment] ───► [Legacy Migration] ───► [Segmentation]
                                                                               │
[Executable Validation] ◄─── [Graph Promotion] ◄─── [Weighting Engine] ◄───────┘
```

The system operates across three core architectural components:
* **Semantic Architect Mode:** Operational agent compiler specification enforcing evidence-bound semantic segmentation, namespace registry construction, and strict preservation contracts.
* **UAS Schema Engine:** Normative schema contract defining root element structures, dual-axis role/edge taxonomies, deterministic repair policies, and executable validation checks.
* **Supervisory / Escalation Skills:** Context entropy monitors that scan workspace data density and conditionally escalate general agents into deterministic compiler mode.

---

## 2. Compilation Pipeline & Taxonomies

### 2.1 Ten-Phase Compilation Pipeline

Compilation executes across ten discrete, evidence-bound phases:

1. **PHASE-01 (Source Inventory):** Identifies source format, structural headings, tables, formulas, citations, code blocks, acronym frequency, and recurring concept signatures.
2. **PHASE-02 (Legacy Migration Detection):** Checks for pre-UAS containers (`<document>`, `<content_body>`, `<agent_ingestion_map>`) and applies migration transforms before compilation.
3. **PHASE-03 (Semantic Segmentation):** Divides source text into addressable `semantic_unit` objects preserving sequential order (`source_order`), surface typology (`surface_form`), and exact byte offsets (`source_span`).
4. **PHASE-04 (Dual-Axis Role Classification):** Assigns a closed `base_role` to each unit while preserving domain nuance via `specialized_role`.
5. **PHASE-05 (Concept & Acronym Registry):** Compiles the `concept_registry` resolving symbols, acronym expansions, aliases, and collision groups before topological assembly.
6. **PHASE-06 (Cognitive Weighting):** Calculates numeric cognitive priority weights ($0.00$ to $1.00$) combining baseline modifiers and graph centrality.
7. **PHASE-07 (Graph Construction):** Synthesizes directed edges across units, sections, formulas, and concepts using closed `base_relation` types.
8. **PHASE-08 (Promotion & Repair):** Evaluates promotion thresholds to promote critical units to top-level graph nodes and deterministically repairs dangling pointers.
9. **PHASE-09 (UAS Emission):** Emits `<UAS_Document>` enforcing strict child element sequence.
10. **PHASE-10 (Executable Validation):** Runs assertion checks emitting failure counts and broken references directly into `<validation_report>`.

### 2.2 Dual-Axis Taxonomy Specifications

To balance strict cross-system interoperability with expressive domain preservation, UAS enforces a "strict core, expressive perimeter" dual-axis taxonomy.

#### Closed Base Roles (`base_role`)
Every semantic unit must strictly map to one of 18 closed base roles:
* `CLAIM`
* `DEFINITION`
* `REQUIREMENT`
* `CONSTRAINT`
* `MECHANISM`
* `ALGORITHM`
* `FORMULA`
* `PARAMETER`
* `EVIDENCE`
* `PROOF`
* `EXAMPLE`
* `WARNING`
* `LIMITATION`
* `OUTCOME`
* `IMPLEMENTATION_DIRECTIVE`
* `OPEN_QUESTION`
* `AMBIGUITY`
* `OBSERVATION`

*Specialized Role Mapping:* Domain-specific roles are admitted as aliases linked to a base role (e.g., `PROBLEM` $\to$ `CLAIM`, `SOLUTION` $\to$ `MECHANISM`, `GUARANTEE` $\to$ `CONSTRAINT`, `DETECTION` $\to$ `ALGORITHM`). Unsupported roles that cannot be resolved deterministically must trigger a `ROLE_OVERFLOW` record in the `<ambiguity_register>`.

#### Closed Base Relations (`base_relation`)
Every topological edge in the cognitive map must strictly map to one of 10 closed base relations:
* `DEPENDS_ON`
* `DEFINES`
* `IMPLEMENTS`
* `CONSTRAINS`
* `CAUSES`
* `EVIDENCES`
* `CONTRADICTS`
* `SEQUENCES`
* `CONTAINS`
* `INFERRED_RELATED_TO`

*Specialized Relation Subtypes:* Semantic links can provide granular subtypes mapped directly to base relations (e.g., `MANDATES` $\to$ `CONSTRAINS`, `PROVES_VIA` $\to$ `EVIDENCES`, `ENABLES` $\to$ `CAUSES`, `RESOLVES` $\to$ `DEPENDS_ON`). Unregistered relations trigger `RELATION_OVERFLOW`.

### 2.3 Mathematical Weighting Engine

Cognitive weights ($w$) determine memory indexing, RAG retrieval ranking, and topological promotion:

$$w = \text{clamp}\left(0.50 + \sum \Delta_{\text{modifiers}} + 0.05 \cdot C_{\text{normalized}},\, 0.00,\, 1.00\right)$$

Where $C_{\text{normalized}}$ represents normalized graph degree centrality, and modifiers ($\Delta$) are assigned per semantic condition:

| Condition | Delta ($\Delta$) | Description |
| :--- | :--- | :--- |
| **Core Thesis / Architecture** | $+0.30$ | Foundational ontology or core system architecture |
| **Executable Rule / Constraint** | $+0.25$ | Formal directives, deployment constraints, schema rules |
| **Causal / Proof Relationship** | $+0.20$ | Critical path dependency or validation chain |
| **Formula / Parameter / Algorithm**| $+0.15$ | Formal logic, metrics, or algorithmic operations |
| **Acronym / Collision Risk** | $+0.15$ | Namespace ambiguity vectors requiring disambiguation |
| **Schema Validation Control** | $+0.10$ | Logic controlling migration or validation checks |
| **Contextual Example / Analogy** | $+0.05$ | Illustrative framing or application examples |
| **Rhetorical / Low-Action Bridge**| $-0.15$ | Background prose or repetitive narrative |
| **Low-Confidence Inference** | $-0.10$ | Inferred links lacking explicit source anchors |

#### Promotion Rules
* **Rule `PM-01` ($w \ge 0.85$):** The semantic unit, formula, or concept must appear directly as an addressable node in `<cognitive_map>` or be reachable from an adjacent promoted node.
* **Rule `PM-02` ($w \ge 0.95$):** The promoted node must possess explicit topological edges; isolated critical nodes require an `<ambiguity_register>` entry justifying node isolation.

---

## 3. Cryptographic Original Text Hash Locking (C Implementation)

### 3.1 Problem Statement
When autonomous LLMs or agents perform structural extraction, they frequently introduce subtle mutations: whitespace compression, quote normalization (`"` to `”`), missing trailing punctuation, character substitutions, and paraphrasing drift. 

While UAS directives mandate zero textual mutation under `VERBATIM_FULL` mode, software cannot rely on neural probability to enforce byte-level immutability. To guarantee complete provenance and cryptographic integrity, an updated native compiler is planned in C.

### 3.2 Native C Engine Architecture

The native C engine operates as a memory-mapped verification and enforcement layer that binds the raw text input directly to the emitted semantic XML.

```
[Raw Source File] ──► mmap() ──► Authoritative Root SHA-256
                            │
               ┌────────────┴────────────┐
               ▼                         ▼
      Byte-Span Registry          Agent Output Stream
     (Offset, Len, Hash)                 │
               │                         ▼
               └────────► [Verification Subsystem] ──► Validated UAS Document
                                (C Engine)
```

#### Memory-Mapped Ingestion Buffer
The source file is loaded into an immutable virtual memory segment via zero-copy mapping (`mmap` on POSIX, `CreateFileMapping` on Win32):

```c
typedef struct {
    const uint8_t *buffer;
    size_t length;
    uint8_t root_sha256[32];
} uas_source_buffer_t;
```

#### Hash-Locked Span Registry
During segmentation, semantic units do not store duplicate text strings. Instead, they register exact coordinate spans and precomputed sub-span SHA-256 cryptographic digests:

```c
typedef struct {
    uint64_t unit_id;
    size_t byte_offset;
    size_t byte_length;
    uint8_t span_sha256[32];
    uint8_t verified;
} uas_text_lock_t;
```

#### Cryptographic Verification Subsystem
Before an emitted UAS XML artifact is committed to storage or ingested into downstream agent memory:
1. **Span Resolution:** The verification engine parses the `source_span` attribute (e.g., `source_span="bytes:1042-1250"`) on each `<semantic_unit>`.
2. **Hash Comparison:** The engine hashes the raw memory block `buffer[1042 ... 1250]` and validates it against `span_sha256`.
3. **Byte Equivalence (`VERBATIM_FULL`):** If preservation mode is verbatim, `memcmp()` directly compares the emitted inner XML text with `buffer + byte_offset`.
4. **Deterministic Halting:** Any byte deviation (even a single whitespace character) causes an instant compile rejection, returning the exact mismatch coordinates to the agent pipeline.

---

## 4. Threat Model: XML Serialization & Agentic Anomalies

Deploying autonomous neural models to construct graph-linked XML exposes pipelines to predictable systemic anomalies:

```
┌────────────────────────────────────────────────────────────────────────┐
│                        AGENTIC ANOMALY VECTORS                         │
├────────────────────────────┬───────────────────────────────────────────┤
│ Structural Corruption      │ Malformed entity escapes (&, <, >), tag   │
│                            │ imbalance, premature context truncation.  │
├────────────────────────────┼───────────────────────────────────────────┤
│ Taxonomy Drift             │ Hallucinating roles (e.g., RULE, NOTE) or │
│                            │ silently coercing complex logic into      │
│                            │ generic OBSERVATION tokens.               │
├────────────────────────────┼───────────────────────────────────────────┤
│ Topological Severing       │ Cognitive edges referencing non-existent  │
│                            │ target IDs; missing concept registry tags.│
├────────────────────────────┼───────────────────────────────────────────┤
│ Preservation Decay         │ Masking compressed summaries as verbatim  │
│                            │ to bypass preservation_audit requirements.│
└────────────────────────────┴───────────────────────────────────────────┘
```

* **Silent Role & Relation Flattening:** Under high cognitive or token loads, agents take algorithmic shortcuts. Instead of classifying a unit as `ALGORITHM` or `CONSTRAINT`, agents default to `OBSERVATION`. Similarly, complex causal relationships are flattened to `INFERRED_RELATED_TO`. This destroys structural density.
* **Entity & Ampersand Collisions:** Ingesting code snippets or formulas often leads to unescaped ampersands or brackets, breaking downstream XML parsers.
* **Dangling Concept Pointers:** Agents frequently reference concepts in units (`concept_ref="CR-012"`) but fail to declare the concept in `<concept_registry>`, severing semantic graph queries.

---

## 5. Cross-Agent Anomaly Watcher Protocol

To guarantee reliable execution across any model (Claude, GPT-4, Gemini, or open-weight models), an external supervisory layer monitors the agent output stream in real time.

```
Agent Output Stream ──► [Watcher: Lexer & Well-Formedness]
                                   │
                                   ▼
                        [Watcher: Structural Parser]
                                   │
                        ┌──────────┴──────────┐
                        ▼                     ▼
             Taxonomy Interceptor     Reference Validator
                        │                     │
                        └──────────┬──────────┘
                                   ▼
                       [C Engine Hash Comparator]
                                   │
                        Pass ──────┴────── Fail
                         │                  │
                         ▼                  ▼
                  Approved Artifact     Deterministic Reject /
                                        Escalation Reprompt
```

### 5.1 Real-Time Streaming Interception
1. **Context Entropy Guard:** Scans incoming source materials. If `raw_text_ratio > 0.80` and `technical_density == HIGH`, standard chat execution is intercepted, immediately injecting `UAS_MODE` system directives.
2. **Lexical Hash Interceptor:** As tokens stream, incoming attributes (`base_role="..."`, `base_relation="..."`) are validated via hash table lookups against the closed taxonomies. Any hallucinated token halts generation before completion.
3. **Graph Integrity Queue:** IDs generated across `<semantic_unit>`, `<formal_definition>`, and `<concept>` are indexed into a fast validation bitset. Edges referencing undeclared IDs are flagged immediately.

### 5.2 Deterministic Machine-Readable Error Feedback
When an anomaly occurs, the supervisory layer does not prompt with subjective natural language. It feeds back a structured error packet that forces targeted deterministic repair:

```xml
<compilation_error_intercept phase="PHASE-10">
    <check_id>VAL-ROLE-ENUM</check_id>
    <severity>fatal</severity>
    <failed_ref>unit_104</failed_ref>
    <invalid_token>HYPOTHESIS</invalid_token>
    <instruction>Token 'HYPOTHESIS' is not permitted in closed base_role_taxonomy. Map to base_role='CLAIM' with specialized_role='HYPOTHESIS' or register an entry in ambiguity_register type='ROLE_OVERFLOW'.</instruction>
</compilation_error_intercept>
```

---

## 6. Repository Layout & Artifact Manifest

```
.
├── README.md                           # Core technical documentation and engine specifications
├── modes/
│   ├── semantic-architect.xml          # Legacy v1.0 operational compiler mode
│   └── UAS_MODE.xml                    # v3.0 normative compiler mode and phase pipelines
├── schemas/
│   └── UAS_SCHEMA_ENGINE.xml           # v2.0 schema contract, taxonomies, and validation checks
├── skills/
│   ├── uas_semantic_compiler.xml       # v4.0 execution skill, weighting deltas, and promotion rules
│   └── assess_and_escalate.xml         # Context entropy assessment and mode escalation logic
└── c_engine/                           # Native C deterministic text-locking implementation
    ├── include/
    │   ├── uas_core.h                  # Core buffer, span registry, and compiler structures
    │   ├── uas_hashlock.h              # Cryptographic span verification and mmap interface
    │   └── uas_taxonomy.h              # Closed taxonomy lookups and enum validators
    ├── src/
    │   ├── uas_core.c                  # Ingestion, validation, and emission pipeline
    │   ├── uas_hashlock.c              # SHA-256 span calculations and memcmp verification
    │   └── uas_taxonomy.c              # Perfect hash table for O(1) role/relation matching
    └── Makefile
```

---

## 7. Implementation Roadmap & Execution Checklist

- [ ] **Repository Reorganization:** Move XML modes, schemas, and skills into structured subdirectories (`modes/`, `schemas/`, `skills/`).
- [ ] **Native C Engine Scaffolding:**
  - [ ] Implement `uas_source_buffer_t` with POSIX `mmap` / Win32 `CreateFileMapping`.
  - [ ] Integrate cryptographic hashing library (BLAKE3 or SHA-256) for root and sub-span digests.
  - [ ] Build `uas-verify` CLI: `uas-verify --source <raw_input.txt> --artifact <compiled_output.xml>`.
- [ ] **Streaming Anomaly Watcher:**
  - [ ] Implement event-driven XML streaming validator using `libxml2` or `expat`.
  - [ ] Implement taxonomy hash table verification against the closed 18-role and 10-relation sets.
  - [ ] Construct machine-readable reprompt generator for automated agent self-repair loops.
- [ ] **Validation Suite Integration:**
  - [ ] Add regression tests validating compliance checks `VAL-XML-WELL-FORMED` through `VAL-MIGRATION-REPORT`.
  - [ ] Stress-test edge cases: nested code blocks, unescaped math expressions, and high acronym density.