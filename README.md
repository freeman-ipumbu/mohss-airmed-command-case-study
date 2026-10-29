# MOHSS AIRMED COMMAND — National Coordination Ecosystem

![MOHSS AIRMED COMMAND](assets/airmed-command.svg)

**A governed national air-medical coordination and shared Government mobility system for Namibia.**

[Open the live demonstration](https://mohss-airmed.pages.dev/) · Private operational source repository

> The public deployment uses synthetic demonstration data. It is not approved for live dispatch, clinical operations, aviation release or production patient information.

## Executive summary

MOHSS AIRMED COMMAND turns a fragmented, multi-institution mission process into one controlled operational record. It coordinates intake, clinical validation, aircraft and crew readiness, receiving-facility acceptance, aviation review, authorization, dispatch and audit evidence without replacing the accountable people who make those decisions.

The v0.7 ecosystem release extends that foundation beyond emergency transfers. When approved capacity is available, Government institutions can request governed transport for specialist outreach, intern and clinical-team rotations, medical logistics, laboratory transfers and disaster support. Emergency readiness remains the overriding priority, and every secondary request accepts pre-emption.

## My role

**Freeman Ipumbu — systems designer, design researcher and product engineer**

I led the problem framing, operational model, command experience, Government ecosystem architecture and working software foundation across:

- React and TypeScript command-centre design and engineering.
- Kotlin and Spring Boot domain, API and authorization design.
- PostgreSQL, PostGIS and Flyway persistence.
- Human decision gates, role separation and audit evidence.
- Cross-Ministry integration boundaries and pilot-readiness planning.
- Executive narrative, demonstration design and assurance positioning.

## The coordination problem

Air-medical missions cross clinical, aviation, hospital, dispatch and executive boundaries. If requests, readiness checks and approvals live in disconnected calls, messages and documents, teams can lose time, ownership and evidence precisely when all three matter most.

A national system needs to answer five questions continuously:

1. What is the current mission state?
2. Which readiness gate is incomplete?
3. Who owns the next authorized action?
4. Why did the state change?
5. Can the decision history be reconstructed later?

## Implemented product response

The v0.7 development foundation implements:

- National command-centre visibility for active missions and priorities.
- Structured mission intake and guarded lifecycle progression.
- Clinical validation, aircraft selection, crew assignment and hospital acceptance.
- Aviation review and flight authorization as named human actions.
- Aircraft, crew and receiving-facility resource registries.
- Role-restricted consequential actions and optimistic concurrency.
- Correlation-aware API errors and attributable audit events.
- Mock and authenticated API data modes.
- Versioned PostgreSQL/PostGIS migrations.
- Governed Government mobility from request through completion or cancellation.
- Authenticated ecosystem capability discovery for approved partner systems.
- Automated repository checks for backend, frontend and dependency quality.

## Government mobility between emergencies

Secondary capacity becomes a public-service capability rather than an informal arrangement.

| Service | Illustrative national use |
| --- | --- |
| Specialist outreach | Move specialist teams to scheduled regional clinics and surgical programmes |
| Intern rotation | Support approved placements where road travel consumes productive time |
| Clinical-team rotation | Move multidisciplinary teams between national and regional facilities |
| Medical logistics | Transport approved supplies or critical equipment |
| Laboratory transfer | Move time-sensitive samples under an approved handling process |
| Disaster response | Support national surge and coordinated public-service response |

Every request records the institution, cost centre, purpose, route, timing, people, cargo and acceptance of emergency pre-emption. Operational review, executive approval and aircraft scheduling remain separate authorized actions.

## Shared-capacity scenario

A specialist team needs to travel from Windhoek to Rundu for an outreach clinic. Interns are due for a supervised rotation in Katima Mulilo, while approved laboratory material must return to Windhoek inside a handling window.

AIRMED records each purpose separately. Flight Operations assesses feasibility against demand and readiness. An authorized executive records approval. Dispatch can schedule only an eligible aircraft. If an emergency transfer arises, the planned service is pre-empted and replanned, with the reason and outcome retained in the audit history.

## Architecture

```text
Government and health partner systems
                 │
      managed identity and API gateway
                 │
       versioned AIRMED REST domains
                 │
       Kotlin / Spring modular API
                 │
 mission · mobility · resources · audit
                 │
       PostgreSQL + PostGIS + Flyway
                 │
      React / TypeScript command centre
```

The backend is a modular monolith: operationally simple to deploy while keeping mission, mobility, identity, resources and audit boundaries explicit.

## Integration model

The target ecosystem supports purpose-limited integration with:

- MOHSS hospitals, EMS and regional health directorates.
- Aircraft operators, flight operations and approved landing sites.
- The Office of the President and participating line ministries.
- Training institutions and regional councils.
- Central medical stores, laboratories and blood services.
- Authorized executive oversight and programme evaluation.

Partner access is designed around federated identity, organization and scope. Executive analytics receives approved operational facts rather than unrestricted clinical records.

## Authority and safety

AIRMED coordinates decisions; it does not assume statutory authority.

- Clinicians retain clinical decision rights.
- Pilots and operators retain aviation release authority.
- Receiving facilities retain acceptance authority.
- Authorized Government officials retain institutional approval.
- Secondary use never creates an entitlement to an aircraft.
- Emergency demand can pre-empt planned mobility.
- Clinical mission details remain separated from the Government mobility domain.

## Ninety-day pilot proposition

| Period | Focus | Decision evidence |
| --- | --- | --- |
| Days 0–15 | Mandate, owners, corridors, services and governance | Signed charter and responsibility matrix |
| Days 16–30 | Identity, privacy, security, clinical, aviation and hosting review | Gap register and acceptance criteria |
| Days 31–50 | Sandbox, reference data, partner contracts and training | Approved test environment and contract tests |
| Days 51–70 | Emergency, pre-emption, downtime and recovery exercises | Exercise results and corrected procedures |
| Days 71–90 | Controlled pilot and evaluation | Benefits, risk and proceed-adjust-stop recommendation |

Proposed measures cover coordination time, readiness confidence, clinical handover, accountability, public-service utilization, regional access, cost governance and reliability. Baselines and targets must be formally approved before benefits are claimed.

## Production-readiness boundary

Before live use, the programme requires:

- Executive mandate and named accountable owners.
- Approved clinical and aviation operating procedures.
- Federated OIDC identity, MFA and account-lifecycle controls.
- Approved hosting, TLS, secret management and network segmentation.
- Privacy, retention and data-sharing agreements.
- Partner contract testing, reconciliation and failure handling.
- Monitoring, incident response, backup, restore and downtime procedures.
- Role-based training, exercises and formal go-live acceptance.

## Engineering stack

- React, TypeScript, React Router and Vite
- Kotlin, Spring Boot and Java 21
- PostgreSQL, PostGIS and Flyway
- Development RBAC and role-restricted backend actions
- Docker Compose for the local operational foundation
- GitHub Actions quality automation
- Cloudflare Pages for the synthetic public demonstration

## Repository boundary

This public case study deliberately excludes deployable operational source, credentials, environment configuration, patient information, private records and sensitive infrastructure detail. The application source remains in a private repository.

Security concerns should be reported privately to the project owner.

---

© 2026 Freeman Ipumbu. Shared for portfolio evaluation; no operational-use licence is granted.

<p align="center"><strong>A Digital Experience by <a href="https://www.solarspin-namibia.xyz/">SolarSpin Technologies</a>.</strong></p>
