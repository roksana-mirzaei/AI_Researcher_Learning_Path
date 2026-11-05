# AI Governance, Regulation, Frontier-Lab Safety Frameworks, Agent Security, Misuse and Incidents (2019 to Nov 2026)

Notes for the "paper atlas". Current date: 2026-11-04.

**Legend.** **V** = checked this session against a primary page, or against several consistent search results that cite the primary. **U** = from prior knowledge or a single secondary source; not re-checked this session. Check every U item before publishing. Org type: I = industry, A = academia, N = non-profit/standards/multistakeholder, X = government/intergovernmental. Contribution types: Prod (production/operational guidance), Eval (evaluation/measurement), Pol (policy/regulation), Std (standard), Data (dataset/database), Thr (threat intel).

---

## Q1. What does each framework say? Concrete obligations, principles, numbers and dates

### Takeaway
The governance stack has three layers. (1) Binding law: the EU AI Act (with a 2026 "Digital Omnibus" delay to high-risk dates), California SB 53 and New York RAISE. (2) Voluntary standards and codes: NIST AI RMF and its GenAI profile, ISO/IEC 42001, and the UK AI Cyber Security Code, which became ETSI TS 104 223 and then EN 304 223. (3) Lab self-governance: Anthropic RSP, OpenAI Preparedness, GDM FSF and Meta FAF, all of which iterated quickly in 2025-2026. Agent-security guidance came together during 2025 around a small set of ideas: limit privileges, keep humans in control, make agents observable, and assume prompt injection cannot be fully fixed.

### Cited Findings (entries)

#### A. UK / ETSI AI security code

### uk-ai-cyber-code — Code of Practice for the Cyber Security of AI | DSIT (UK) | 2025-01 (31 Jan 2025) | voluntary code | DSIT (X) | https://www.gov.uk/government/publications/ai-cyber-security-code-of-practice | Prod, Std
- **Problem:** AI systems bring security risks that general software codes do not cover: data poisoning, model obfuscation, indirect prompt injection and supply-chain issues.
- **New:** A lifecycle-based baseline that assigns each security duty to a named stakeholder role. It is meant to seed a global ETSI standard.
- **Why it matters for agent deployers:** If you deploy an agent you are a "System Operator". The code gives you duties around human responsibility (P4), monitoring (P12), and infrastructure and access control (P6).
- **Key specifics:**
  - Published 31 Jan 2025 (V, [gov.uk](https://www.gov.uk/government/publications/ai-cyber-security-code-of-practice/code-of-practice-for-the-cyber-security-of-ai)).
  - **5 lifecycle phases:** secure design, secure development, secure deployment, secure maintenance, secure end of life (V).
  - **13 principles (verbatim titles, V):**
    1. Raise awareness of AI security threats and risks
    2. Design your AI system for security as well as functionality and performance
    3. Evaluate the threats and manage the risks to your AI system
    4. Enable human responsibility for AI systems
    5. Identify, track and protect your assets
    6. Secure your infrastructure
    7. Secure your supply chain
    8. Document your data, models and prompts
    9. Conduct appropriate testing and evaluation
    10. Communication and processes associated with End-users and Affected Entities
    11. Maintain regular security updates, patches and mitigations
    12. Monitor your system's behaviour
    13. Ensure proper data and model disposal
  - Principles 1-4 fall under secure design; 5-9 under development; 10 under deployment; 11-12 under maintenance; 13 under end of life (U; this follows from the document's structure but was not re-checked line by line).
  - **Stakeholder roles (V):**
    - Developers: create or adapt a model or system, proprietary or open-source.
    - System Operators: embed or deploy a model or system, including contracted providers.
    - Data Custodians: control data permissions and integrity.
    - End-users: employees and UK consumers.
    - Affected Entities: individuals or technologies affected by outputs without interacting with the system.
    - AI Vendors are described as "unlikely to be in scope" (V).
  - The code says the UK will submit the Code and its Implementation Guide to ETSI to build a global standard. The gov.uk page itself does not cite TS 104 223 (V).
  - Published alongside an Implementation Guide (V, mentioned on the page).
- **Lineage:**
  - NCSC/CISA "Guidelines for Secure AI System Development" (Nov 2023; same four lifecycle stages minus end of life) → this: lifecycle framing (U).
  - This → ETSI TS 104 223 (Apr 2025) → ETSI EN 304 223 (Jan 2026): near-verbatim 13 principles and 5 phases (V that EN builds on TS and keeps 13 principles and 5 phases; U for the TS date).
- **Accuracy notes:** P10's title is not imperative ("Communication and processes associated with…"). Keep it verbatim.

### etsi-ts-104-223 / etsi-en-304-223 — Securing Artificial Intelligence (SAI): Baseline Cyber Security Requirements for AI Models and Systems | ETSI TC SAI | TS 2025-04 (U); EN 2026-01 (press release 15 Jan 2026, V via secondary) | standard | ETSI (N) | https://www.etsi.org (search "EN 304 223") | Std, Prod
- **Problem:** Turn the UK code into an internationally recognised standard.
- **New:**
  - TS (technical specification) first. Then an EN (European Norm), which goes through national standards bodies.
  - The EN references the EU AI Act (Reg. 2024/1689) as a complementary cybersecurity baseline (V, secondary: [TelecomTV/ETSI release](https://www.telecomtv.com/content/etsi/etsi-releases-world-leading-standard-for-securing-ai-54664/); [arc42](https://quality.arc42.org/standards/etsi-en-304-223)).
- **Key specifics:**
  - 13 principles, 5 phases (V).
  - Scope: AI systems that incorporate deep neural networks, including generative AI (V, secondary).
  - Companion guide ETSI TR 104 128 (U).
- **Lineage:** UK code → TS 104 223 → EN 304 223 (V).
- **Accuracy notes:** arc42 gives Dec 2025 for the EN; ETSI's press release is 15 Jan 2026. The Dec 2025 date may be formal approval. The EN is not a harmonised standard under the AI Act unless cited in the OJ (U). This session did not confirm that.

#### B. Regulation and standards

### eu-ai-act — Regulation (EU) 2024/1689 (Artificial Intelligence Act) | EU Parliament & Council | 2024-06 (signed 13 Jun; OJ 12 Jul 2024) | regulation | EU (X) | https://eur-lex.europa.eu/eli/reg/2024/1689/oj | Pol
- **Problem:** Harmonised, risk-based rules for AI on the EU market.
- **New:**
  - Four risk tiers: prohibited, high-risk, transparency (Art. 50), minimal.
  - A separate regime for GPAI models, plus "systemic risk" GPAI. Systemic risk is presumed above 10^25 training FLOP (U).
- **Why it matters:**
  - An agent built on a GPAI model inherits the provider's documentation duties.
  - An agent used in an Annex III domain (employment, credit, etc.) becomes high-risk.
- **Key specifics (original timeline, U from prior knowledge, widely known):**
  - Entry into force 1 Aug 2024.
  - Prohibitions and AI literacy apply from 2 Feb 2025.
  - GPAI obligations, governance and penalties apply from 2 Aug 2025.
  - General application, including Annex III high-risk, from 2 Aug 2026.
  - Art. 6(1)/Annex I product high-risk from 2 Aug 2027.
  - GPAI models placed on the market before 2 Aug 2025 must comply by 2 Aug 2027.
- **Digital Omnibus on AI (2025-2026):**
  - Commission proposal 19 Nov 2025 (U).
  - Provisional agreement about 7 May 2026, with Council confirmation 13 May (secondary).
  - EP vote 16 Jun 2026; Council 29 Jun 2026 (secondary).
  - Published in the OJ as **Regulation (EU) 2026/1744** on 24 Jul 2026; in force 27 Jul 2026 (secondary: [Orrick](https://www.orrick.com/en/Insights/2026/07/EU-AI-Act-Update-Digital-Omnibus-Finalizes-8-Compliance-Changes), [CSA](https://labs.cloudsecurityalliance.org/research/csa-research-note-eu-ai-act-omnibus-vii-deadline-delay-20260/), [artificialintelligenceact.eu](https://artificialintelligenceact.eu/ai-act-explorer/digital-omnibus/)).
  - **Annex III high-risk moves to 2 Dec 2027. Annex I/Art. 6(1) moves to 2 Aug 2028.** Art. 50(2) watermarking for systems already on the market gets a grace period to 2 Dec 2026.
  - New prohibitions on AI that generates non-consensual intimate imagery or CSAM. SME/small mid-cap simplifications.
  - Mark all omnibus specifics **U+** (consistent across several law-firm and secondary sources, but EUR-Lex was not fetched). Confirm the regulation number on EUR-Lex.
- **Lineage:**
  - OECD AI Principles (2019) definition of AI system → AI Act Art. 3 definition (U).
  - AI Act Art. 56 → GPAI Code of Practice (V in concept).
- **Accuracy notes:** Do not write "high-risk applies Aug 2026" without noting the omnibus deferral.

### eu-gpai-code — General-Purpose AI Code of Practice | independent chairs/experts, facilitated by EU AI Office | 2025-07 (published 10 Jul 2025, U) | voluntary code (Art. 56) | European Commission (X) | https://digital-strategy.ec.europa.eu/en/policies/contents-code-gpai | Pol, Prod
- **New:**
  - Three chapters. Transparency (with a Model Documentation Form) and Copyright apply to all GPAI providers. Safety & Security applies only to systemic-risk GPAI providers (U for structure details; widely reported).
  - Safety & Security requires a "Safety and Security Framework", systemic-risk assessment, serious-incident reporting, and so on. This closely mirrors lab frontier frameworks.
- **Signatories:**
  - Full signatories include Amazon, Anthropic, Google, IBM, Microsoft, Mistral, OpenAI and Aleph Alpha.
  - **xAI signed only the Safety & Security chapter.**
  - **Meta declined to sign at all** (Joel Kaplan: obligations go "beyond the scope" of the Act).
  - Counts are reported as roughly 26-28 (secondary, consistent: [Euronews 1 Aug 2025](https://www.euronews.com/2025/08/01/some-26-tech-companies-sign-up-to-eu-commissions-ai-code); [freevacy](https://www.freevacy.com/news/european-commission/eu-commission-publishes-gpai-code-of-practice-assessment-and-signatory-list/6621)).
- **Lineage:** RSP/PF/FSF "frontier safety frameworks" → S&S chapter's "Safety and Security Framework" concept (U, inference widely made by commentators).
- **Accuracy notes:** Exact count unverified. Use the Commission's rolling list.

### nist-ai-rmf — AI Risk Management Framework 1.0 (NIST AI 100-1) | NIST | 2023-01 (26 Jan 2023) | voluntary framework | NIST (X) | https://www.nist.gov/itl/ai-risk-management-framework | Prod, Std
- **Key specifics:**
  - Four functions: **Govern, Map, Measure, Manage**. Govern is cross-cutting (U, well known).
  - Seven trustworthiness characteristics: valid & reliable; safe; secure & resilient; accountable & transparent; explainable & interpretable; privacy-enhanced; fair with harmful bias managed (U).
- **Lineage:** RMF → NIST AI 600-1 GenAI Profile: cross-sectoral profile mapping actions onto the RMF functions (U, explicit in 600-1).

### nist-ai-600-1 — AI RMF: Generative Artificial Intelligence Profile | NIST | 2024-07 (26 Jul 2024) | profile | NIST (X) | https://doi.org/10.6028/NIST.AI.600-1 | Prod
- **Origin:** Mandated by EO 14110 (U).
- **12 risks (U, from prior knowledge of the text):**
  1. CBRN information or capabilities
  2. Confabulation
  3. Dangerous, violent, or hateful content
  4. Data privacy
  5. Environmental impacts
  6. Harmful bias and homogenization
  7. Human-AI configuration
  8. Information integrity
  9. Information security
  10. Intellectual property
  11. Obscene, degrading, and/or abusive content
  12. Value chain and component integration
- About 200 suggested actions (U).
- **Lineage:** EO 14110 §4.1 → this (U). AI RMF → this (U).

### iso-42001 — ISO/IEC 42001:2023 AI management systems | ISO/IEC JTC 1/SC 42 | 2023-12 | certifiable management-system standard | ISO (N) | https://www.iso.org/standard/81230.html | Std
- Plan-Do-Check-Act management system (Annex SL structure, like ISO 27001), with Annex A controls (U).
- Companion standard: ISO/IEC 23894 on AI risk management (U).

### us-eo-14110 — EO 14110 "Safe, Secure, and Trustworthy Development and Use of AI" | White House | 2023-10 (30 Oct 2023) | executive order | US Gov (X) | Pol
- Reporting duties for dual-use foundation models trained above 10^26 FLOP; tasks for NIST/AISI (U).
- **Revoked** 20 Jan 2025 by EO 14148. Then EO 14179 "Removing Barriers to American Leadership in AI" (23 Jan 2025) (U).

### us-ai-action-plan — "Winning the Race: America's AI Action Plan" | White House OSTP | 2025-07 (23 Jul 2025) | policy plan | US Gov (X) | https://www.ai.gov | Pol
- Three pillars: accelerate innovation; build American AI infrastructure; lead in international diplomacy and security (U).
- Renamed US AISI to CAISI (Center for AI Standards and Innovation, Jun 2025) (U).
- **Lineage:** EO 14179 → Action Plan (U).

### ca-sb-53 — Transparency in Frontier Artificial Intelligence Act (SB 53) | California Legislature (Sen. Wiener) | 2025-09 (signed 29 Sep 2025) | state law | California (X) | Pol
- Applies to frontier developers training above 10^26 FLOP. "Large frontier developers" also have >$500M revenue (U).
- Large frontier developers must publish a frontier AI framework (U).
- Critical safety incidents go to Cal OES within 15 days, or 24 h when there is imminent risk (U).
- Whistleblower protections; CalCompute; civil penalties up to $1M per violation (U).
- Effective 1 Jan 2026 (U).
- **Lineage:** SB 1047 (vetoed Sep 2024) → Joint California Policy Working Group report (Jun 2025) → SB 53 (U).

### ny-raise-act — Responsible AI Safety and Education (RAISE) Act | NY Legislature (Bores/Gounardes) | signed 19 Dec 2025, chapter amendment S8828 signed 27 Mar 2026 | state law | New York (X) | Pol
- Amended to resemble SB 53 more closely.
- Revenue threshold >$500M.
- AG enforcement with penalties up to $1M for a first violation and $3M for later ones (secondary, consistent: [Mondaq](https://www.mondaq.com/unitedstates/new-technology/1725500/new-york-enacts-raise-act-for-ai-transparency-amid-federal-preemption-debate), [NatLawReview](https://natlawreview.com/article/new-yorks-raise-act-what-frontier-model-developers-need-know)).
- **Effective date conflict:** most sources say 1 Jan 2027; JD Supra says 1 Jul 2027 (unresolved).
- **Lineage:** SB 53 → RAISE amendments (secondary).

### seoul-commitments — Frontier AI Safety Commitments | UK & Republic of Korea governments + companies | 2024-05 (21 May 2024) | voluntary commitments | (X+I) | https://www.gov.uk/government/publications/frontier-ai-safety-commitments-ai-seoul-summit-2024 | Pol
- 16 companies at launch (later about 20) committed to publish safety frameworks with risk thresholds before the Paris AI Action Summit (Feb 2025). They also committed to not develop or deploy a model if risks cannot be kept below thresholds (U).
- **Lineage:** Anthropic RSP (2023) → Seoul commitments: the "if-then" threshold framework was generalised to industry (U, widely stated). Seoul → Meta FAF, Amazon, Microsoft, etc. frameworks (U).

### bletchley-declaration — The Bletchley Declaration | 28 countries + EU | 2023-11 (1 Nov 2023) | declaration | (X) | https://www.gov.uk/government/publications/ai-safety-summit-2023-the-bletchley-declaration | Pol
- Shared understanding of "frontier AI" risks. Launched the State of the Science report, which became the International AI Safety Report (U).

### uk-aisi — UK AI Safety Institute → AI Security Institute | DSIT | renamed 14 Feb 2025 | institution | (X) | https://www.aisi.gov.uk | Eval
- The rename signals a security/crime focus (U).
- Co-ran agent-hijacking red-teaming with US AISI (V, via the [NIST blog](https://www.nist.gov/news-events/news/2025/01/technical-blog-strengthening-ai-agent-hijacking-evaluations) summary).

### intl-ai-safety-report — International AI Safety Report (2025; 2026) | chair Yoshua Bengio + Expert Advisory Panel | 2025-01 (29 Jan 2025, U); 2026-02 (3 Feb 2026, V/secondary) | scientific assessment | UK AISI secretariat (X) | https://internationalaisafetyreport.org/publication/international-ai-safety-report-2026 | Eval
- 2025: 96 experts; 30 countries plus EU, OECD, UN (U).
- 2026: "over 100" independent experts (V). It notes that some models can distinguish evaluation from deployment contexts (secondary).
- **Lineage:** Bletchley → interim report (May 2024) → 2025 → 2026 (U/V).
- **Accuracy notes:** Bengio's own site lists 6 Feb 2026. The official site and press say 3 Feb.

### oecd-ai-principles — OECD Recommendation on AI | OECD | 2019-05; revised 2024-05 | intergovernmental recommendation | OECD (X) | https://oecd.ai/en/ai-principles | Pol
- Five values-based principles and five recommendations to governments. The 2024 revision updated the AI-system definition (U).
- Also adopted as the G20 AI Principles (Jun 2019) (U).

### china-measures — China's AI rules (brief) | CAC et al. | 2022-2025 | regulations | (X) | Pol
- Algorithmic Recommendation Provisions (Mar 2022) (U).
- Deep Synthesis Provisions (Jan 2023) (U).
- Interim Measures for Generative AI Services (effective 15 Aug 2023) (U).
- Measures for Labelling AI-Generated Content (effective 1 Sep 2025) (U).
- Algorithm filing/registry (U).

#### C. Frontier lab frameworks

### anthropic-rsp — Responsible Scaling Policy | Anthropic | 2023-09 (v1, 19 Sep 2023); v2 2024-10 (15 Oct 2024); v3.0 2026-02 (effective 24 Feb 2026) | lab policy | Anthropic (I) | https://www.anthropic.com/responsible-scaling-policy | Prod, Eval
- **New:** AI Safety Levels (ASL-1..4+) modelled on biosafety levels. "If-then" capability thresholds trigger required safeguards.
- **Key specifics:**
  - v2 added Capability Thresholds and Required Safeguards, covering CBRN and autonomous AI R&D (U).
  - **ASL-3 protections activated 22 May 2025** with Claude Opus 4 (U).
  - v2.1 Mar 2025 and v2.2 May 2025 (U).
  - **v3.0 effective 24 Feb 2026** (V, Anthropic URL title). It was a rewrite that split Anthropic's own commitments from industry recommendations and added Frontier Safety Roadmaps and Risk Reports (secondary, [GovAI](https://www.governance.ai/analysis/anthropics-rsp-v3-0-how-it-works-whats-changed-and-some-reflections)). Critics say the earlier unilateral pause commitment was dropped ([Zvi](https://thezvi.substack.com/p/anthropic-responsible-scaling-policy)); this is contested.
  - v3.1 (2 Apr 2026), v3.2 (29 Apr 2026), v3.3 (26 May 2026), v3.4 (8 Jul 2026), as listed on Anthropic's RSP page per search (U+). Contents of 3.2-3.4 not verified.
- **Lineage:**
  - BSL biosafety levels → ASL (U).
  - ARC Evals/METR "responsible scaling policies" concept (Sep 2023) → RSP (U).
  - RSP → OpenAI PF → GDM FSF (U, chronological; all three cite the if-then structure).

### openai-preparedness — Preparedness Framework | OpenAI | 2023-12 (beta, 18 Dec 2023); v2 2025-04 (15 Apr 2025) | lab policy | OpenAI (I) | https://cdn.openai.com/pdf/18a02b5d-6b67-4cec-ab64-68cdfbddebcd/preparedness-framework-v2.pdf | Prod, Eval
- **Beta version:** categories were Cybersecurity, CBRN, Persuasion and Model Autonomy, scored Low/Medium/High/Critical. Deploy only at post-mitigation Medium or below; develop only at High or below (U).
- **v2:**
  - Tracked Categories: **Biological & Chemical, Cybersecurity, AI Self-improvement**, each with High and Critical thresholds (V via consistent secondary sources and the PDF title/date).
  - Research Categories: Long-range Autonomy, Sandbagging, Autonomous Replication & Adaptation, Undermining Safeguards, Nuclear & Radiological (U; sources disagree on Nuclear & Radiological).
  - Persuasion was dropped from tracked categories (U).
  - The Safety Advisory Group reviews Capabilities Reports and Safeguards Reports (U).
- **Accuracy notes:** The OpenAI web page returned 403. Read PDF §2.3 directly.

### gdm-fsf — Frontier Safety Framework | Google DeepMind | v1 2024-05 (17 May 2024); v2 2025-02 (4 Feb 2025); v3 2025-09 (22 Sep 2025); v3.1 2026-04 (17 Apr 2026) | lab policy | Google DeepMind (I) | https://deepmind.google/discover/blog/strengthening-our-frontier-safety-framework/ | Prod, Eval
- **New:** Critical Capability Levels (CCLs) in CBRN, cyber, ML R&D and autonomy (v1, U).
- v2 added security levels per CCL and deceptive-alignment approaches (U).
- **v3 (V):**
  - Adds a **harmful manipulation CCL**: "powerful manipulative capabilities" that could substantially change beliefs and behaviours in high-stakes contexts.
  - Covers misaligned models that "might interfere with operators' ability to direct, modify or shut down their operations", handled through ML R&D CCL protocols. This is **not** a standalone "shutdown resistance" CCL.
  - Safety case reviews extend to large-scale internal deployments.
- **Accuracy notes:** The brief's "shutdown resistance CCL" wording is inaccurate. The post was updated 17 Apr 2026 for FSF 3.1 (V); 3.1 contents not checked.

### meta-faf — Frontier AI Framework | Meta | 2025-02 (3 Feb 2025) | lab policy | Meta (I) | https://ai.meta.com/static-resource/meta-frontier-ai-framework/ | Prod
- Outcome-based thresholds for cybersecurity and chemical/biological risks. Models are classed as moderate/high/critical risk; development stops at critical (U).
- **Lineage:** Seoul commitments → FAF (U).

### metr-common-elements — Common Elements of Frontier AI Safety Policies | METR | 2024-08; updated 2025-03 (U) | analysis | METR (N) | https://metr.org/common-elements | Eval
- Compares lab policies across capability thresholds, model weight security, deployment mitigations, conditions for halting, full capability elicitation, eval timing, accountability and updating (U).

#### D. Misuse and threat intelligence

### openai-disrupting — Disrupting malicious uses of AI (report series) | OpenAI Intelligence & Investigations | 2024-02 (with Microsoft) → periodic (May/Oct 2024; Feb/Jun/Oct 2025) | threat report | OpenAI (I) | https://openai.com/global-affairs/ | Thr
- State actors and covert influence operations mostly used models for incremental productivity, not novel capabilities (U).

### anthropic-threat-reports — Anthropic threat intelligence | Anthropic Threat Intelligence | 2025-03; 2025-08; 2025-11 | threat report | Anthropic (I) | https://www.anthropic.com/news/disrupting-AI-espionage | Thr
- **Mar 2025:** "Detecting and countering malicious uses of Claude", covering influence-as-a-service and similar (U).
- **Aug 2025:** "vibe hacking" GTG-2002 data-extortion operation using Claude Code against about 17 organisations (U).
- **Nov 2025, AI-orchestrated espionage (V):**
  - Chinese state-sponsored group, assessed "with high confidence".
  - Detected mid-September 2025.
  - Used Claude Code (with MCP tools) against "roughly thirty global targets"; succeeded "in a small number of cases".
  - AI performed **80-90%** of the campaign, with about 4-6 human decision points per campaign.
  - The news page does not use the label "GTG-1002"; that label is in the full PDF report (U).
- **Why it matters:** This is the first documented case of an agentic coding tool used as an autonomous intrusion operator. The attackers jailbroke it by splitting tasks and role-playing as a pentester (U).

### google-gtig — Adversarial Misuse of Generative AI (Jan 2025) / Advances in Threat Actor Usage of AI Tools (Nov 2025) | Google Threat Intelligence Group | 2025-01 (29 Jan, U); 2025-11 (5 Nov 2025, V/secondary) | threat report | Google (I) | https://cloud.google.com/blog/topics/threat-intelligence/threat-actor-usage-of-ai-tools | Thr
- **Jan 2025:** APTs from Iran, China, North Korea and Russia used Gemini mainly for research and productivity. No novel capabilities seen (U).
- **Nov 2025:** first "just-in-time" AI malware.
  - PROMPTFLUX: VBScript dropper that queries the Gemini API to rewrite and obfuscate itself.
  - PROMPTSTEAL: used by Russian government-backed actors; queries an LLM via the Hugging Face API to generate commands. Described as "first LLM-querying malware observed in live operation" (secondary, consistent).

### model-cards — Model Cards for Model Reporting | Mitchell, Wu, Zaldivar, Barnes, Vasserman, Hutchinson, Spitzer, Raji, Gebru | 2019-01 (FAT* 2019; arXiv Oct 2018) | paper | Google (I) | https://arxiv.org/abs/1810.03993 | Prod
- Standardised documentation: intended use, factors, metrics, disaggregated evaluation, ethical considerations (U).
- **Lineage:** Datasheets for Datasets (Gebru et al. 2018) → Model Cards → lab "system cards", which now carry RSP/PF/FSF evaluation results → GPAI CoP Model Documentation Form / UK code P8 "Document your data, models and prompts" (U).

### wmdp — The WMDP Benchmark | Li et al. (CAIS + Scale AI + ~50 co-authors) | 2024-03 | benchmark | CAIS (N)/Scale (I) | https://arxiv.org/abs/2403.03218 | Eval
- 3,668 multiple-choice questions on biosecurity, cybersecurity and chemistry as hazardous-knowledge proxies. Introduces RMU unlearning (U).
- Contrast with lab bio-uplift trials (human-uplift RCTs in RSP/PF system cards) (U).

#### E. Incident tracking and threat taxonomies

### aiid — AI Incident Database | Sean McGregor (Partnership on AI → Responsible AI Collaborative) | 2020-11 (arXiv 2011.08512; IAAI-21) | database | (N) | https://incidentdatabase.ai | Data
- Crowdsourced incident records modelled on aviation and safety databases (U).

### oecd-aim — OECD AI Incidents Monitor (AIM) | OECD.AI | 2023 (U) | database | OECD (X) | https://oecd.ai/en/incidents | Data
- Automated news-based incident detection. Also feeds an OECD common incident-reporting framework (2025) (U).

### mitre-atlas — Adversarial Threat Landscape for AI Systems | MITRE (+ Microsoft origin) | 2021 (from the 2020 Adversarial ML Threat Matrix) (U) | knowledge base | MITRE (N) | https://atlas.mitre.org | Thr, Prod
- ATT&CK-style tactics and techniques for ML. Agent techniques added in 2025 (U).

### google-saif — Secure AI Framework and SAIF Risk Map | Google | 2023-06 (SAIF); risk map ~2024-10 (U) | framework | Google (I) | https://saif.google | Prod
- Six core elements, including "extend detection and response" and "automate defenses" (U).
- The risk map lists risks such as prompt injection, rogue actions and sensitive data disclosure, with controls (U).
- **Lineage:** SAIF → CoSAI (OASIS, launched Jul 2024) (U). SAIF → the Google secure agents paper (U).

### Inferences
- Three lineages are well supported:
  - UK code → ETSI TS → ETSI EN (V).
  - NIST AI RMF → AI 600-1 (U, explicit in the docs).
  - RSP → Seoul commitments → every frontier framework → EU GPAI CoP S&S chapter → SB 53 / RAISE, all requiring a published framework and incident reporting (U+, but structurally obvious).
- The 2025-2026 trend is a move from voluntary lab policies to mandated transparency, meaning a published framework plus incident reporting. Hard capability-gated pauses were not mandated.

### Gaps
- EUR-Lex text of Reg. (EU) 2026/1744 not fetched.
- GPAI CoP official signatory count not checked.
- OpenAI PF v2 Research Categories not read from the PDF (the page returned 403).
- RSP v3.2-3.4 contents not checked.
- RAISE effective date conflict (1 Jan vs 1 Jul 2027).
- ETSI TS 104 223 exact date not checked on etsi.org.

---

## Q2. Agent-security principles: origin and best primary source

### Takeaway
Most principles are older security ideas applied to LLM agents:
- Zero trust: NIST SP 800-207.
- Least privilege: Saltzer & Schroeder, 1975.
- Confused deputy: Hardy, 1988.
- OAuth token exchange: RFC 8693.

The agent-specific primary statements come from four places: NCSC's Dec 2025 "inherently confusable deputy" blog, Google's 2025 "human controllers / limited powers / observable actions" paper, Meta's Oct 2025 "Agents Rule of Two", and the OpenID Foundation's Oct 2025 identity whitepaper. "Privileges no higher than the least-trusted input" has **no single canonical primary source**.

### Cited Findings (entries)

### ncsc-prompt-injection — "Prompt injection is not SQL injection (it may be worse)" | David C, NCSC Technical Director for Platforms Research | 2025-12 (8 Dec 2025) | blog | NCSC (X) | https://www.ncsc.gov.uk/blog-post/prompt-injection-is-not-sql-injection | Prod
- **Key specifics (V, via search summaries of the NCSC page and PDF):**
  - LLMs cannot distinguish data from instructions, so there's "a good chance prompt injection will never be properly mitigated" the way parameterised queries fix SQLi.
  - Treat it as exploitation of an "**inherently confusable deputy**". The post does not say "confused deputy" verbatim.
  - Reduce impact through secure design, data marking and monitoring.
  - Be wary of vendors claiming they can "stop" prompt injection.
- **Lineage:** Hardy (1988) confused deputy → this: reframing (V for phrase, U for explicit citation).

### google-secure-agents — An Introduction to Google's Approach for Secure AI Agents | Santiago Díaz, Christoph Kern, Kara Olive | 2025 (May 2025 per brief; the page says only "2025") | whitepaper | Google (I) | https://research.google/pubs/an-introduction-to-googles-approach-for-secure-ai-agents/ | Prod
- **Three principles (V):**
  - "agents must have well-defined human controllers"
  - "their powers must be carefully limited"
  - "their actions and planning must be observable"
- Hybrid defense-in-depth: "traditional, deterministic security controls" combined with "dynamic, reasoning-based defenses" (V).

### meta-rule-of-two — Agents Rule of Two | Meta AI security team | 2025-10 (31 Oct 2025) | blog | Meta (I) | https://ai.meta.com/blog/practical-ai-agent-security/ (U URL) | Prod
- In one session, an agent should satisfy at most two of three properties: [A] processes untrustworthy inputs, [B] has access to sensitive systems or private data, [C] can change state or communicate externally (secondary, consistent: [Simon Willison](https://simonw.substack.com/p/new-prompt-injection-papers-agents)).
- **Lineage:** Chromium "Rule of 2" + Willison's "lethal trifecta" (Jun 2025) → this (secondary).

### openid-agentic-identity — Identity Management for Agentic AI | OpenID Foundation AI Identity Management Community Group (Tobin South et al.) | 2025-10 (7 Oct 2025) | whitepaper | OIDF (N) | https://openid.net/new-whitepaper-tackles-ai-agent-identity-challenges/ ; arXiv 2510.25819 | Prod
- Recommends building on OAuth 2.0, using MCP, and treating agents as full IAM participants with lifecycle governance (V/secondary).
- Gaps it names: agent identity fragmentation, user impersonation, consent fatigue, recursive delegation, and browser agents bypassing API controls (secondary).

### nist-agent-hijacking — Technical Blog: Strengthening AI Agent Hijacking Evaluations | US AISI (now CAISI) technical staff | 2025-01 (17 Jan 2025) | blog/eval | NIST (X) | https://www.nist.gov/news-events/news/2025/01/technical-blog-strengthening-ai-agent-hijacking-evaluations | Eval
- Fixed AgentDojo (ETH Zurich) scenarios and added Inspect integration, released as usnistgov/agentdojo-inspect.
- Red-teamed upgraded Claude 3.5 Sonnet with UK AISI (V/secondary).
- Lesson: evaluate attack success per task and use adaptive attacks (U).

### owasp-agentic — OWASP Agentic AI – Threats and Mitigations (Feb 2025, U) and Top 10 for Agentic Applications 2026 (9 Dec 2025) | OWASP GenAI Security Project | 2025 | guidance | OWASP (N) | https://genai.owasp.org | Prod
- ASI01 Agent Goal Hijack; ASI02 Tool Misuse & Exploitation; ASI03 Identity & Privilege Abuse; ASI04 Agentic Supply Chain; ASI09 Human-Agent Trust Exploitation; ASI10 Rogue Agents (secondary). ASI05-08 not confirmed.

### csa-maestro — MAESTRO agentic threat-modelling framework | Ken Huang, Cloud Security Alliance | 2025-02 (U) | framework | CSA (N) | https://cloudsecurityalliance.org/blog/2025/02/06/agentic-ai-threat-modeling-framework-maestro | Prod
- Seven-layer reference architecture for threat modelling (U).

### Agent security principle → best primary source → quote

| Principle | Origin (earliest) | Best primary source for agents | Brief quote / substance | V/U |
|---|---|---|---|---|
| Zero trust for agents | NIST SP 800-207 *Zero Trust Architecture* (Aug 2020); Kindervag/Forrester 2010 | NIST SP 800-207 + OWASP ASI03 / OpenID whitepaper for agent application | 800-207: no implicit trust based on network location; access "granted on a per-session basis" | U (800-207 quote from memory) |
| Least privilege | Saltzer & Schroeder 1975 | Google Secure AI Agents (2025) | "their powers must be carefully limited" | V |
| Identity per agent (non-human identity) | Workload identity (SPIFFE, 2017+) | OpenID Foundation, *Identity Management for Agentic AI* (Oct 2025); Microsoft Entra Agent ID (Build, May 2025, U) | Treat agents as full participants in IAM with lifecycle controls; explicit on-behalf-of delegation | V (OIDF, secondary detail), U (Entra) |
| Temporary / short-lived credentials | OAuth 2.0 Token Exchange RFC 8693 (Jan 2020); SPIFFE SVIDs | OpenID whitepaper (builds on OAuth 2.0); RFC 8693 | Delegation via scoped, exchanged tokens rather than standing secrets | U (RFC detail) |
| Human approval for high-impact actions | UK code P4 "Enable human responsibility for AI systems" (Jan 2025) | Google Secure AI Agents | "agents must have well-defined human controllers" | V |
| Independent log monitoring | UK code P12 "Monitor your system's behaviour" | Google Secure AI Agents; NCSC blog ("better monitoring") | "their actions and planning must be observable" | V |
| LLM as confusable/confused deputy | Norm Hardy, "The Confused Deputy" (1988) | NCSC, "Prompt injection is not SQL injection" (8 Dec 2025) | exploitation of an "inherently confusable deputy" | V (phrase), U (Hardy citation) |
| Deterministic safeguards (policy outside the model) | Reference monitors (Anderson 1972) | Google Secure AI Agents; CaMeL (Debenedetti et al., Mar 2025, U) | hybrid of "traditional, deterministic security controls" and "reasoning-based defenses" | V (Google) |
| Privileges no higher than the least-trusted input | Information-flow / taint tracking (Biba integrity, 1977) | No canonical primary. Closest: Meta "Agents Rule of Two" (Oct 2025); Prompt Flow Integrity (arXiv 2503.15547); practitioner phrasing (Hacker News "The Least Trusted Author Sets the AI Agent's Privilege", Oct 2026) | Rule of Two: at most two of {untrusted input, sensitive access, state change/external comms} | U (attribution) |

### Inferences
- For deployers, the practical consensus is architectural. Assume injection succeeds, bound the blast radius (Rule of Two, least privilege, scoped credentials), and keep humans and logs outside the model's control.

### Gaps
- No primary source found for the exact wording "privileges no higher than the least-trusted input". The phrase appears mainly in vendor and commentary writing ([THN Oct 2026](https://thehackernews.com/expert-insights/2026/10/the-least-trusted-author-sets-ai-agents.html)).
- Microsoft Entra Agent ID, AWS and Anthropic agent guidance (e.g., Anthropic "framework for safe and trustworthy agents", Aug 2025) not fetched (U).
- Google paper's exact month not shown on its page.

---

## Q3. Lineage, contribution types, and corrections

### Takeaway
The lineages are well established. A few common claims are wrong: GDM v3 has no "shutdown resistance CCL"; NCSC says "confusable", not "confused"; high-risk AI Act dates are no longer Aug 2026/2027.

### Cited Findings (lineage edges)
- UK Code (Jan 2025) → ETSI TS 104 223 → ETSI EN 304 223 (Jan 2026): 13 principles and 5 phases carried over — V ([gov.uk](https://www.gov.uk/government/publications/ai-cyber-security-code-of-practice/code-of-practice-for-the-cyber-security-of-ai); [TelecomTV/ETSI](https://www.telecomtv.com/content/etsi/etsi-releases-world-leading-standard-for-securing-ai-54664/))
- NIST AI RMF 1.0 → NIST AI 600-1: GenAI profile mapped to Govern/Map/Measure/Manage — U
- EO 14110 → AI 600-1, US AISI; EO 14110 revoked → EO 14179 → AI Action Plan — U
- Anthropic RSP (Sep 2023) → OpenAI PF (Dec 2023) → GDM FSF (May 2024) → Seoul commitments (May 2024) → Meta FAF and others (Feb 2025): if-then thresholds — U
- Frontier frameworks → EU GPAI CoP Safety & Security chapter; → SB 53 "frontier AI framework" → RAISE amendments — U / secondary ([NatLawReview](https://natlawreview.com/article/new-yorks-raise-act-what-frontier-model-developers-need-know))
- Bletchley (Nov 2023) → International AI Safety Report 2025 → 2026 — V/U ([official site](https://internationalaisafetyreport.org/publication/international-ai-safety-report-2026))
- Chromium Rule of 2 + Willison lethal trifecta → Meta Agents Rule of Two — secondary ([Willison](https://simonw.substack.com/p/new-prompt-injection-papers-agents))
- AgentDojo (ETH) → NIST AgentDojo-Inspect — V/secondary ([NIST](https://www.nist.gov/news-events/news/2025/01/technical-blog-strengthening-ai-agent-hijacking-evaluations))
- GTIG Jan 2025 → GTIG Nov 2025: from productivity misuse to just-in-time malware — secondary ([GTIG](https://cloud.google.com/blog/topics/threat-intelligence/threat-actor-usage-of-ai-tools))
- Model Cards (2019) → system cards → GPAI CoP model documentation / UK P8 — U

### Inferences
- Contribution types:
  - Mostly Prod: UK code, ETSI, NIST RMF/600-1, SAIF, OWASP, Google agents paper, OIDF.
  - Eval: lab frameworks' threshold evals, WMDP, NIST hijacking, AISI, IASR.
  - Pol: EU AI Act, CoP, SB 53, RAISE, EOs, Seoul, Bletchley, OECD.
  - Thr/Data: OpenAI, Anthropic and GTIG reports; AIID; AIM; ATLAS.

### Gaps (Corrections & unverifiable items)
**Corrections to the brief:**
1. GDM FSF v3 adds a *harmful manipulation* CCL. Shutdown and modification interference is handled under ML R&D/misalignment protocols, not as a "shutdown resistance" CCL (V).
2. NCSC wording is "inherently confusable deputy", not "confused deputy" (V).
3. EU AI Act high-risk dates were deferred by the Digital Omnibus: Annex III to 2 Dec 2027, Annex I to 2 Aug 2028 (U+, secondary-consistent).
4. The UK code's gov.uk page does not name TS 104 223. The ETSI link comes from ETSI (V).
5. Anthropic's Nov 2025 news page does not say "GTG-1002". The label is reportedly in the full report (U).
6. Meta did not sign any chapter of the GPAI CoP. xAI signed only Safety & Security (secondary-consistent).
7. RSP had further versions in 2026 (v3.0 to v3.4) (V for 3.0, U for the rest).

**Unverifiable or unverified this session:**
- Reg. (EU) 2026/1744 number and OJ date.
- Official GPAI CoP signatory count.
- OpenAI PF v2 Research Category list (Nuclear & Radiological disputed).
- RSP 3.2-3.4 contents.
- ASL-3 activation date (22 May 2025, U).
- RAISE effective date (1 Jan vs 1 Jul 2027).
- ETSI TS 104 223 publication month.
- EN 304 223 date (Dec 2025 vs Jan 2026).
- IASR 2025 count (96 experts).
- NIST 600-1 risk list (from memory).
- SB 53 numeric thresholds and penalties.
- China measure dates.
- MITRE ATLAS and SAIF risk-map dates.
- Microsoft Entra Agent ID details.
- CSA MAESTRO date.
- OWASP ASI05-ASI08 names.
- Primary source for "least-trusted input" privilege rule (none found).
