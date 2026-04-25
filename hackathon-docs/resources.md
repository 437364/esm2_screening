This resources page provides curated reading material, tools, and project ideas organized by hackathon track. You do not need to read everything here. Start with the "Essential Reading" section for your chosen track, explore the tools you plan to use, and dive deeper into specific papers as your project takes shape.

**Readings for All Tracks**
---------------------------

*   ["Biosecurity in the Age of AI"](https://www.belfercenter.org/publication/biosecurity-age-ai-whats-risk) (Belfer Center, 2024) - Overview of how AI capabilities intersect with biological risk, covering both offensive and defensive applications.
    
*   [NTI | bio "Developing Guardrails for AI Biodesign Tools"](https://www.nti.org/analysis/articles/developing-guardrails-for-ai-biodesign-tools/) - Recommends built-in guardrails (screening I/O, curated training data) and managed access paradigms.
    
*   [JHU Center for Health Security "Biosecurity Guide to AI Action Plan"](https://centerforhealthsecurity.org/our-work/aixbio/biosecurity-guide-to-the-ai-action-plan) (2025) - Recommends prioritizing biosecurity risks, formal governance for models enabling pandemic-level risks.
    
*   [CSIS "Eight Commonsense Actions for Biosafety and Biosecurity"](https://www.csis.org/analysis/eight-commonsense-actions-biosafety-and-biosecurity) (2025) - Bipartisan recommendations including integrating biosurveillance into infrastructure and establishing AI-powered threat forecasting.
    

**Track 1: DNA Screening & Synthesis Controls** (sponsored by [CBAI](https://www.cbai.ai/))
-------------------------------------------------------------------------------------------

Build better tools for screening DNA synthesis orders from commercial providers, detecting dangerous sequences, and creating guardrails for AI-powered biological design tools. For benchtop synthesizer-specific projects, see Track 4.

Current screening infrastructure has critical gaps. AI-designed protein variants can evade sequence-based screening. False positive rates at short sequence lengths drive up manual review costs. Regulatory frameworks for synthesis screening remain incomplete, and approximately 20% of global synthesis capacity operates outside voluntary screening frameworks.

### Essential Reading

*   [SecureDNA Documentation](https://securedna.org/) - Free, open-source screening platform using cryptographic DOPRF. Detects sequences as short as 30bp.
    
*   [IBBIS Common Mechanism (commec)](https://github.com/ibbis-screening/common-mechanism) - Free, open-source HMM-based biorisk screening. Best performance above 150bp.
    
*   ["Strengthening nucleic acid biosecurity screening against generative protein design tools"](https://www.science.org/doi/10.1126/science.adu8578) (Microsoft et al., Science, Oct 2025) - AI-designed synthetic variants slipped through screening undetected. Cross-sector team developed patches.
    
*   [OSTP Framework for Nucleic Acid Synthesis Screening](https://bidenwhitehouse.archives.gov/ostp/news-updates/2024/04/29/framework-for-nucleic-acid-synthesis-screening/) (April 2024) - Federal guidance requiring compliant providers for funded research. Effective April 29, 2025.
    
*   [Biosecurity Modernization and Innovation Act of 2026 (S.3741)](https://www.congress.gov/bill/119th-congress/senate-bill/3741/text) (Jan 2026) - Bipartisan bill mandating screening by gene synthesis providers and establishing NIST biotechnology governance sandbox.
    

### Further Reading

*   [NTI "Framework for Managed Access to Biological AI Tools"](https://www.nti.org/analysis/articles/a-framework-for-managed-access-to-biological-ai-tools/) - Proposes tiered access from open-source to closed, with screening at each level.
    
*   ["A Biosecurity Agent for Lifecycle LLM Biosecurity Alignment"](https://arxiv.org/abs/2510.09615) (2025) - Four-mode framework (dataset sanitization, preference alignment, runtime guardrails, automated red teaming). Reduced attack success from 59.7% to 3.0%.
    
*   [Responsible AI x Biodesign](https://responsiblebiodesign.ai/) - 180+ AI developers and 150+ scientists from 28 countries signed commitments on responsible use.
    
*   [Global Risk Index for AI-enabled Biological Tools](https://www.rand.org/pubs/external_publications/EP71093.html) (RAND/CLTR, Sep 2025) - Framework assessing biodesign tools by capability, misuse potential, accessibility, and maturity.
    

### Example Projects

*   Build function-prediction-based screening that flags sequences by predicted biological function rather than sequence similarity alone
    
*   Build a biosecurity screening layer for biology-focused LLM interfaces (input/output filtering)
    
*   Prototype a managed access wrapper for an open-source biodesign tool (e.g., ProteinMPNN) with tiered permissions based on user vetting
    
*   Create an ML-based system to reduce false positive rates in short-sequence screening, cutting manual review burden
    
*   Develop a pipeline to identify and flag hazardous sequences in biological training datasets
    

**Track 2: Pandemic Early Warning** (sponsored by [Measuring AI Progress](https://measuringaiprogress.org/))
------------------------------------------------------------------------------------------------------------

### Essential Reading

*   [SecureBio / Nucleic Acid Observatory](https://securebio.org/detection/) - Pathogen-agnostic metagenomic surveillance. 31 sites, 19 cities.
    
*   ["Pandemic monitoring with global aircraft-based wastewater surveillance networks"](https://www.nature.com/articles/s41591-025-03501-4) (Nature Medicine, Feb 2025) - Modeled global pandemic monitoring via airplane wastewater.
    
*   [CDC National Wastewater Surveillance System (NWSS)](https://www.cdc.gov/nwss/index.html) - COVID-19, influenza, RSV, mpox monitoring. Critical funding issues with COVID supplemental expiring.
    
*   [Go.Data](https://www.who.int/tools/godata) (WHO) - Open-source outbreak response and contact tracing platform. Went open-source April 2024.
    
*   [SORMAS](https://sormas.org/) (HZI) - Open-source surveillance and outbreak response system. Built during 2014 Ebola outbreak.
    

### Further Reading

*   [WaSPP (Wastewater Surveillance for Pandemic Prevention)](https://www.waspp.org/) - International network launched mid-2025 standardizing methods across Africa, Asia, Europe.
    
*   [Biobot Analytics](https://biobot.io/) - Commercial wastewater surveillance measuring 51 substances. Detects trends 2 weeks before hospital data.
    
*   "Biothreat Radar" CDC FY2026 Budget Proposal - $52M for metagenomic sequencing at 5 wastewater sites and 13 airports. Could detect novel pathogens before 12 in 100,000 infected.
    
*   [ProMED-mail](https://www.promedmail.org/) - Qualitative outbreak reporting system, ~80,000 subscribers in ~200 countries, 24/7 staff from 30+ countries.
    

### Example Projects

*   Build an ML anomaly detection system for metagenomic sequence data from wastewater surveillance
    
*   Develop a classifier that flags sequences with engineering hallmarks (foreign material, cloning scars, resistance cassettes) in metagenomic data
    
*   Build an open-source disease intelligence platform using public data (WHO reports, ProMED, news APIs, flight data) as an alternative to proprietary tools like BlueDot
    
*   Create an automated alert pipeline: sequence data in, actionable notification out, with confidence scoring
    
*   Build a data integration dashboard aggregating surveillance from multiple sources (NWSS, clinical, news, social media)
    
*   Prototype privacy-preserving data sharing protocol for cross-jurisdictional surveillance using differential privacy or federated learning
    
*   Add an ML-based anomaly detection or forecasting module to an open-source tool like SORMAS or Go.Data
    

**Track 3: AI Biosecurity Tools** (sponsored by [Fourth Eon Bio](https://fourtheon.bio/))
-----------------------------------------------------------------------------------------

### Essential Reading

*   [CSIS "Eight Commonsense Actions for Biosafety and Biosecurity"](https://www.csis.org/analysis/eight-commonsense-actions-biosafety-and-biosecurity) (2025) - Bipartisan recommendations for integrating biosurveillance, strengthening cyber-bio infrastructure, establishing AI threat forecasting.
    
*   [Global Risk Index for AI-enabled Biological Tools](https://www.rand.org/pubs/external_publications/EP71093.html) (RAND/CLTR, Sep 2025) - Structured framework for assessing biodesign tool risks. First attempt at repeatable, scalable methodology.
    
*   [Biosecurity Vulnerability Scan](https://biosecurityvulnerabilityscan.nl/en/) - Web tool for identifying organizational biosecurity gaps across eight pillars.
    
*   [NTI BIRRI Project](https://www.nti.org/about/programs-projects/project/fostering-biosecurity-innovation-and-risk-reduction/) (2025, Amsterdam) - Global experts on DNA synthesis screening, AIxBio capabilities, and mirror life risks.
    

### Further Reading

*   [BioRAMs](https://github.com/sandialabs/BioRAM) (Sandia National Labs) - Laboratory biosafety and biosecurity risk assessment models.
    
*   [NIEM (National Information Exchange Model)](https://www.niemopen.org/) - Common vocabulary for cross-agency data exchange.
    
*   [WHO Outbreak Toolkit](https://www.who.int/emergencies/outbreak-toolkit) - Comprehensive guides for field investigators in resource-limited settings.
    
*   [ASPR TRACIE](https://asprtracie.hhs.gov/) - HHS technical resources for health emergency management.
    

### Example Projects

*   Build a unified biosecurity dashboard pulling from surveillance, news, synthesis screening, and policy feeds
    
*   Create a rapid risk assessment tool: input a new AI model or capability, output a structured threat assessment based on existing frameworks (RAND, Sandia, IBBIS)
    
*   Build an open-source threat intelligence aggregator for biosecurity (like "VirusTotal for bio")
    
*   Prototype a biosecurity policy tracker monitoring regulatory changes across jurisdictions
    
*   Develop a lightweight, offline-capable screening or risk assessment tool for low-resource settings
    
*   Build a cyberbiosecurity vulnerability scanner for lab information systems and sequence databases
    
*   Create a gamified lab biosecurity self-assessment tool that institutions can run quarterly
    

Track 4: Benchtop Synthesizer Security (co-sponsored by [Sentinel Bio](https://sentinelbio.org/))
-------------------------------------------------------------------------------------------------

Benchtop DNA synthesizers are approaching the capability to synthesize significant portions of viral genomes in the next few years. Today, no mandatory sequence or customer screening exists beyond export controls, but recent legislative momentum in the US and EU is opening a window to change this. This track focuses on building the security infrastructure needed to secure benchtops, such as phone-home screening, hardware security, and split order detection. [Sentinel Bio](https://sentinelbio.org/) is a non-profit philanthropic fund that supports and incubates projects in biotech governance, including AI-enabled biology and nucleic acid synthesis screening.

### Example Projects

*   Design an on-device record-keeping system for benchtop synthesizers: compress synthesis logs for secure on-device storage and later auditing, like an aircraft black box for DNA synthesis. See Baker & Church in "Protein design meets biosecurity" and Jonas Sandbrink on record-keeping for strong attribution.
    
*   Build on-device split order detection: given a device's synthesis history, flag when sequences could be assembled into a sequence of concern. A valid finding may be that local-only detection is insufficient and sequences need to be checked against a shared online database.
    
*   Research tamper-evident or tamper-proof approaches for benchtop devices: survey the most tamper-proof laboratory devices available today, assess viability and cost for benchtop synthesizers. See the tamper-proofing mitigations in the [IFP report on Securing Benchtop DNA Synthesizers](https://ifp.org/securing-benchtop-dna-synthesizers/).
    
*   Map the reagent supply chain for know-your-customer feasibility: determine which current benchtop devices use generic vs. proprietary dNTPs, whether enzymatic or chip-based synthesis changes the picture, and whether standardized customer screening for reagent purchases is viable. See IFP recommendations and UK screening guidance on reagent tracking.
    
*   Prototype on-device authentication and authorization for researchers approved to work with sequences of concern: address spoofing and privilege escalation threats. See [SecureDNA Exemption Certificates](https://securedna.org/) for one approach using hardware keys and biosafety officer approvals.
    

Project ideas contributed by [Tessa Alexanian](https://www.linkedin.com/in/tessaalexanian), with additions by [Lucas Boldrini](https://www.linkedin.com/in/lucas-boldrini?originalSubdomain=fr).

### Essential Reading

*   [Securing Benchtop DNA Synthesizers](https://ifp.org/securing-benchtop-dna-synthesizers/) (IFP) - Covers benchtop biosecurity risks and technical mitigations including tamper-proofing, phone-home screening, and reagent supply chain controls.
    
*   [SecureDNA Documentation](https://securedna.org/) - Free, open-source screening platform using cryptographic DOPRF. Detects sequences as short as 30bp.
    
*   [IBBIS Common Mechanism (commec)](https://github.com/ibbis-screening/common-mechanism) - Free, open-source HMM-based biorisk screening. Best performance above 150bp.
    
*   ["Strengthening nucleic acid biosecurity screening against generative protein design tools"](https://www.science.org/doi/10.1126/science.adu8578) (Microsoft et al., Science, Oct 2025) - AI-designed synthetic variants slipped through screening undetected. Cross-sector team developed patches.
    
*   [OSTP Framework for Nucleic Acid Synthesis Screening](https://bidenwhitehouse.archives.gov/ostp/news-updates/2024/04/29/framework-for-nucleic-acid-synthesis-screening/) (April 2024) - Federal guidance requiring compliant providers for funded research. Effective April 29, 2025.
    
*   [Biosecurity Modernization and Innovation Act of 2026 (S.3741)](https://www.congress.gov/bill/119th-congress/senate-bill/3741/text) (Jan 2026) - Bipartisan bill mandating screening by gene synthesis providers and establishing NIST biotechnology governance sandbox. First US legislation with enforcement teeth ($500K individual / $750K org penalties).
    
*   ["Regulatory Gaps in Benchtop Nucleic Acid Synthesis Create Biosecurity Vulnerabilities"](https://www.armscontrol.org/blog/2025-11-24/regulatory-gaps-benchtop-nucleic-acid-synthesis-create-biosecurity-vulnerabilities) (Arms Control Association, Nov 2025) - How current regulations fail to address benchtop synthesizers, worsened by the expired OSTP revision deadline.
    
*   ["Benchtop DNA Synthesis Devices: Capabilities, Biosecurity Implications, and Governance"](https://www.nti.org/analysis/articles/benchtop-dna-synthesis-devices-capabilities-biosecurity-implications-and-governance/) (NTI, 2023) - The foundational report calling for customer vetting, built-in screening software, and mandatory government regulations for benchtop devices.
    
*   ["Assembling unregulated DNA segments bypasses synthesis screening: regulate fragments as select agents"](https://www.nature.com/articles/s41467-025-67955-3) (Edison, Toner & Esvelt, Nature Communications, Jan 2026) - MIT researchers acquired unregulated DNA fragments from dozens of providers sufficient for a skilled individual to generate 1918 influenza. Demonstrates that fragment-level regulation is needed.
    
*   ["Analysis of the Security Design, Engineering, and Implementation of the SecureDNA System"](https://www.ndss-symposium.org/ndss-paper/analysis-of-the-security-design-engineering-and-implementation-of-the-securedna-system/) (Sherman et al., NDSS 2026) - First formal security analysis of SecureDNA. Found that the mutual authentication protocol achieves only one-way authentication, enabling rate-limit circumvention. Relevant for anyone building on-device screening.
    
*   ["AI Can Already Evade DNA Synthesis Screening. Congress's New Bill Doesn't Address That."](https://thecounterfactual.substack.com/p/s3741-and-the-art-of-not-dying-of) (Sophie Kim, Mar 2026) - Gap analysis of S.3741. The bill mandates homology-based screening but doesn't address AI-designed functional variants or benchtop devices adequately.
    

### Further Reading

*   ["Why We're Doubling Down on Synthesis Screening"](https://sentinelbio.org/why-were-doubling-down-on-synthesis-screening/) (Sentinel Bio, Feb 2026) - After evaluating 200+ physical chokepoints, Sentinel Bio concludes synthetic DNA remains the best intervention point. Also identifies pathogen repositories, CROs, and cloud labs as promising complementary chokepoints.
    
*   ["Guidelines for Nucleic Acid Synthesis Screening in Europe"](https://www.pourdemain.ngo/en/post/guidelines-for-nucleic-acid-synthesis-screening-in-europe) (Pour Demain, Mar 2026) - Policy brief on the EU Biotech Act's mandatory screening proposal, the most ambitious screening legislation globally.
    
*   [DNA Synthesis Screening: The Critical Chokepoint](https://biosecurityhandbook.com/biotechnology/dna-synthesis-screening.html) (Biosecurity Handbook, Bryan Tegomoh, 2025) - Educational overview of how screening works, key gaps (oligonucleotides, benchtop, unscreened capacity), and the regulatory timeline from 2010 to present.
    

**Tools and Platforms**
-----------------------

### Screening

*   [SecureDNA](https://securedna.org/) - Free, open-source DNA sequence screening.
    
*   [IBBIS Common Mechanism (commec)](https://github.com/ibbis-screening/common-mechanism) - Free, open-source HMM-based biorisk screening.
    

### Surveillance and Outbreak Response

*   [Go.Data](https://www.who.int/tools/godata) (WHO) - Open-source contact tracing and outbreak response.
    
*   [SORMAS](https://sormas.org/) (HZI) - Open-source surveillance and outbreak management.
    
*   [STEM](https://projects.eclipse.org/projects/technology.stem) - Open-source spatiotemporal epidemiological modeler (archived, but codebase still available).
    
*   [ProMED-mail](https://www.promedmail.org/) - Global disease outbreak reporting.
    
*   [GenBank / NCBI](https://www.ncbi.nlm.nih.gov/genbank/) - Sequence data repositories.
    

### Biodesign Tools (for building guardrails around)

*   [ProteinMPNN](https://github.com/dauparas/ProteinMPNN) - Protein sequence design. Track 1 participants may build screening or access controls for tools like this.
    
*   [RFdiffusion](https://github.com/RosettaCommons/RFdiffusion) - Protein structure generation.
    
*   [AlphaFold 3](https://github.com/google-deepmind/alphafold3) (DeepMind) - Protein structure prediction.
    

### Community Tools

*   [BINTEX](https://bintex.life/) - AI-powered drug discovery and literature analysis platform. Queries PubMed, OpenTargets, ChEMBL, [ClinicalTrials.gov](http://clinicaltrials.gov/), and UniProt with multi-perspective LLM synthesis.