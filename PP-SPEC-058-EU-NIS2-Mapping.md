# PP-SPEC-058: Proof of Efficacy Mapping to the EU NIS2 Directive

| Field | Value |
|---|---|
| Status | DRAFT v0.1 |
| Author | Craig Ellrod, Nebulonium, Inc. (dba HACKERverse®) |
| Date | October 8, 2026 |
| License | CC BY 4.0 |
| Maps to | Directive (EU) 2022/2555 (NIS2) and Commission Implementing Regulation (EU) 2024/2690 |
| Series | Proof Protocol Framework Mapping Specifications |

---

## 1. Purpose

This specification defines how the cybersecurity risk-management measures and incident reporting obligations of the NIS2 Directive can be bound to Proof Protocol test cases, evidence, and efficacy results.

NIS2 is Directive (EU) 2022/2555 of the European Parliament and of the Council of 14 December 2022 on measures for a high common level of cybersecurity across the Union, published in the Official Journal of the European Union on 27 December 2022. Member States were required to transpose it by 17 October 2024. Commission Implementing Regulation (EU) 2024/2690 of 17 October 2024 lays down technical and methodological requirements of cybersecurity risk-management measures, and further specifies when an incident is significant, for DNS service providers, TLD name registries, cloud computing service providers, data centre service providers, content delivery network providers, managed service providers, managed security service providers, providers of online marketplaces, online search engines and social networking services platforms, and trust service providers.

The upstream source remains authoritative for its own requirements, identifiers, terminology, and guidance. This document defines a **Proof Protocol mapping** and does not supersede, reproduce, modify, or certify conformance to the upstream source.

## 2. Scope

NIS2 supplies external context that can identify what should be examined or tested by an essential or important entity, a national competent authority, or a CSIRT. Proof Protocol supplies an independent evidence model for determining what happened during a test and whether a selected control performed as claimed.

NIS2 is a directive. Obligations on entities arise from the national law of each Member State that transposes it. This mapping references the Directive and Implementing Regulation (EU) 2024/2690 (which applies directly to the entity types it covers) and treats national transposing measures as jurisdiction-specific context that MUST be recorded when relevant.

The primary mapping targets are Article 21 (cybersecurity risk-management measures) and Article 23 (reporting obligations). Governance (Article 20), registration, supervision, and enforcement provisions are context only.

Independent witnessing, proof validity, evidence capture, packaging, anchoring, and efficacy semantics are defined elsewhere in the Proof Protocol specification family.

## 3. Core Question

Proof of efficacy asks:

> **Was there a control, and did it work?**

A framework requirement, criterion, principle, or obligation may identify a condition of interest. A product, architecture, policy, process, or safeguard may claim to satisfy or mitigate that condition. Proof Protocol binds the external context, test, control, observed behavior, downstream outcome, and evidence into a result that can be independently examined.

A Proof Protocol result does **not** by itself establish legal, audit, regulatory, or standards conformance unless the applicable authority separately determines that the evidence is sufficient.

A Proof Protocol result is **not a legal or regulatory determination** and does **not** establish compliance with NIS2, Implementing Regulation (EU) 2024/2690, or any national transposing law. Determinations of compliance rest with entities' management bodies, national competent authorities, and courts.

## 4. Metric Definitions

Against a defined corpus or test condition, each applicable empirical case is recorded as **blocked**, **detected**, **missed**, or **INVALID** where those verdicts are meaningful.

Relevant measurements can include containment rate, detection rate, miss rate, false-positive rate, robustness under bypass or failure conditions, version-level results, and **INVALID** when required evidence is incomplete or broken.

Not every upstream requirement is empirical. Governance, documentation, organizational, legal, and procedural requirements MUST NOT be converted into efficacy scores merely because they can be referenced by a proof record.

## 5. Evidence Produced

Mapped tests can produce:

- **Proof records** binding external context, test case, control, system/version, verdict, timestamp, and evidence references;
- **ProofStamp™** trusted timestamps bound to evidence/verdict objects;
- **ProofBundle™** packages containing proof records, metrics, corpus manifests, and environment/context;
- **ProofRegister™** records for issued proof artifacts; and
- corpus and environment manifests identifying the tested conditions.

## 6. Mapping to NIS2

Exact upstream identifiers and titles SHOULD be taken from the authoritative version being mapped and recorded in the ProofBundle™ where licensing permits. This specification does not redefine upstream requirements.

NIS2 provisions SHOULD be cited by instrument, article, paragraph, and point (for example, "Directive (EU) 2022/2555, Article 21(2)(d)"). Implementing Regulation (EU) 2024/2690 requirements SHOULD be cited by Annex section number. Where national law applies, the transposing measure and its version SHOULD also be cited.

| NIS2 context | Proof Protocol treatment | Evidence |
|---|---|---|
| Instrument, Member State, and transposing measure | Bind the Directive, the Implementing Regulation where applicable, the Member State, and the national measure and version to the proof record. | Requirement metadata |
| Entity category (essential or important) and sector | Record entity category and sector as context only. | Requirement metadata |
| Governance and management body accountability (Article 20) | Non-empirical context. Do not score. | Non-empirical annotation |
| Article 21(2) measure point (letters (a) to (j)) | Bind the specific point to test conditions only where the measure describes an observable technical behavior (for example, incident handling, business continuity, supply chain security, vulnerability handling, cryptography, access control, multi-factor authentication). Policy and training points remain non-empirical. | Proof record; corpus manifest |
| Implementing Regulation (EU) 2024/2690 Annex requirement | Bind the Annex section number for in-scope entity types and record the asserted implementation separately from observed behavior. | Control descriptor |
| Measure operation | Exercise the defined condition and capture whether the measure operated at the protected network and information system. | Execution evidence |
| Downstream outcome | Establish whether the protected service or asset was actually protected, contained, or recovered when efficacy is claimed. | Target/outcome evidence |
| Exception/failure condition | Exercise negative, bypass, misuse, or failure cases where applicable. | Proof records; robustness evidence |
| Significant incident criteria (Article 23(3); Implementing Regulation (EU) 2024/2690) | Record significance criteria as context. Whether an exercised condition would meet them is a determination for the entity and authority, not a Proof Protocol verdict. | Requirement metadata; non-empirical annotation |
| Reporting stages (Article 23(4): early warning, incident notification, final report) | Treat as procedural context. Bind only observable facts, such as detection time and evidence that an exercised incident was detected and recorded. Reporting timeliness is not an efficacy score. | Detection result; timestamps |
| System/version context | Bind material system, policy, configuration, supplier, and environment versions. | Environment descriptor |
| Evidence export for supervisory review | Package evidence and provenance for independent examination. | ProofBundle |

## 7. Interoperability Rules

1. The authoritative upstream source, edition/version, and applicable identifier SHOULD be recorded.
2. Upstream identifiers and terminology MUST NOT be silently redefined.
3. Proof Protocol verdicts are Proof Protocol results; they are not upstream certifications, audit opinions, legal determinations, or endorsements.
4. A control's presence, configuration, activation, detection, and efficacy are distinct facts.
5. A policy decision, alert, log entry, or control trigger does not by itself establish efficacy when the claim concerns a downstream protected outcome.
6. Target, application, tool, SIEM, vendor, service, resource, or equivalent evidence SHOULD complete the evidence round trip when required to establish the result.
7. Missing required evidence MUST yield **INVALID**, not PASS.
8. Material changes to the tested system, policy, control, environment, mapping, or corpus SHOULD trigger retesting where they can affect the result.
9. Non-empirical requirements MUST remain distinguishable from empirically tested efficacy assertions.

## 8. Framework-Agnostic Architecture

> **Threat, control, audit, and regulatory frameworks are pluggable inputs to Proof Protocol. Proof Protocol is framework-agnostic.**

External frameworks can identify **what to test or examine**. Proof Protocol independently establishes **whether the control worked and what evidence proves that result**.

No external framework is required for Proof Protocol to operate. An implementation MAY use NIS2, another recognized framework, a proprietary threat model, several frameworks simultaneously, or no external framework when the test condition is otherwise sufficiently defined.

Adding, replacing, muting, or removing a framework mapping does not alter the Proof Protocol architecture, evidence model, Proof of Efficacy determination, ProofBundle™, ProofStamp™, ProofRegister™, or independent corroboration requirements.

A framework mapping therefore establishes **interoperability**, not architectural dependency.

## 9. Relationship to Proof Protocol

This mapping is part of the Proof Protocol specification family maintained by Nebulonium, Inc.

The relationship is intentionally asymmetric:

> **NIS2 supplies legal cybersecurity risk-management and reporting obligations. Proof Protocol supplies the evidence model for independently examining whether a selected technical measure performed as claimed.**

No affiliation, endorsement, certification, or sponsorship by the European Union, the European Commission, ENISA, or any national competent authority or CSIRT is implied.

## 10. Source Framework, Attribution, and License

NIS2 and Implementing Regulation (EU) 2024/2690 are public law of the European Union. The authoritative source is EUR-Lex, the official website of EU law:

- Directive (EU) 2022/2555: https://eur-lex.europa.eu/eli/dir/2022/2555/oj/eng
- Implementing Regulation (EU) 2024/2690: https://eur-lex.europa.eu/eli/reg_impl/2024/2690/oj/eng

Only the versions published in the Official Journal of the European Union are authentic and legally binding.

Implementation status as confirmed for this draft: the transposition deadline was 17 October 2024. On 8 July 2026, the European Commission decided to refer Ireland, Spain, France, and the Netherlands to the Court of Justice of the European Union for failing to notify full transposition (https://digital-strategy.ec.europa.eu/en/policies/nis2-directive; https://ec.europa.eu/commission/presscorner/detail/en/ip_26_1499). On 20 January 2026, the Commission proposed targeted amendments to NIS2 as part of a cybersecurity package; their adoption status as of October 8, 2026 was not confirmed. The transposition status of each other Member State was not individually confirmed and SHOULD be checked against the Commission's transposition records and national official journals before reliance.

EU reuse policy: the European Commission's reuse policy is implemented by Commission Decision 2011/833/EU of 12 December 2011 on the reuse of Commission documents. The Commission states that, unless otherwise indicated, content owned by the EU on its website Licensed under the Greater Good Commercial License 1.0 (see LICENSE.md); text CC BY 4.0 under its Part S. Original inventor: Craig Thomas Ellrod (ORCID 0009-0004-1058-7666).

This Proof Protocol mapping is independently authored and Licensed under the Greater Good Commercial License 1.0 (see LICENSE.md); text CC BY 4.0 under its Part S. Original inventor: Craig Thomas Ellrod (ORCID 0009-0004-1058-7666).

Where upstream material is copyrighted or access-controlled, contributors MUST NOT copy protected normative text into this repository merely to make the mapping self-contained. Reference identifiers and independently authored descriptions should be used where legally appropriate.

### Required attribution

EU legislation does not impose a specific notice for citation by instrument number and article. Reuse of EU-owned content requires appropriate credit and indication of changes. The recommended attribution line used in this repository is:

> Source: EUR-Lex, https://eur-lex.europa.eu, © European Union. Directive (EU) 2022/2555 (NIS2 Directive), OJ of 27 December 2022, and Commission Implementing Regulation (EU) 2024/2690. Reused under Commission Decision 2011/833/EU. Only the Official Journal versions are authentic.

What this specification reproduces: instrument titles and numbers, article and point references, the entity types listed in the title of Implementing Regulation (EU) 2024/2690, short names of reporting stages, dates, and short factual statements. It does not reproduce article text, recitals, or annex content. Any future inclusion of EUR-Lex text MUST credit the source and indicate changes.

## 11. Versioning

This mapping is versioned independently of NIS2. Material upstream changes, including adoption of amendments to NIS2, amendments to Implementing Regulation (EU) 2024/2690, or changes in national transposition, SHOULD trigger a mapping review and, where necessary, a new version identifying the upstream revision mapped.

---

*Proof Protocol · proofprotocol.io · CC BY 4.0*
