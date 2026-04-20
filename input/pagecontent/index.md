<!-- <br/>
<span style="background-color: LightYellow;">NOTE: Information on this page is [informative content](https://hl7.org/fhir/versions.html#std-process).</span>
<br/> -->

<img src="logo-eahp.svg" alt="Eahp Logo" width="300px" style="float:none; margin: 0px 0px 0px 0px;" />

### Background

Hospital pharmacies across Europe increasingly rely on automation 
devices — Whole Pack Robots (WPR), Automated Dispensing Cabinets 
(ADC), Unit Dose Robots (UDR) — to manage medication storage, 
dispensing, and traceability. These devices are typically procured 
from different vendors and are expected to operate as an integrated 
system within the hospital pharmacy.

In practice, communication between devices from different vendors 
requires bespoke, point-to-point integrations. Each integration is 
developed and maintained independently, creating significant cost, 
fragility, and barrier to procurement flexibility. No shared standard 
has existed for the exchange of supply and inventory information 
between pharmacy automation devices.

The EAHP Special Interest Group (SIG) on Interoperability in Pharmacy 
Automation was established to address this gap. The SIG brings together 
hospital pharmacists, automation vendors, and standards experts from 
across Europe. Its mandate is to define a vendor-neutral, 
pharmacist-validated standard for communication between automation 
devices — enabling plug-and-play interoperability across competing 
products.

The SIG operates in two phases. Phase 1 established governance 
structures, shared definitions, and functional Standard Operating 
Procedures (SOPs) for each target use case. Phase 2, of which this 
Implementation Guide is the primary output, translates those SOPs 
into a FHIR-based technical specification.

At the EAHP Congress in Barcelona (March 2026), ten vendors 
demonstrated live multi-vendor interoperability using the protocol 
defined in this IG — covering 14 devices and 56 device-to-device 
combinations — with zero per-vendor customisation. This IG formalises 
that protocol.

### Motivations for the EAHP interoperability implementation guide

Fragmented integrations. Automation devices typically communicate with the Pharmacy Management System (PMS) through point-to-point, proprietary connectors — one per device. Each new connector is usally specific to the combination of device and PMS, and has to be  updated when either system is upgraded or replaced. Across a market with dozens of device vendors and multiple PMS platforms, this creates a large and fragmented integration landscape with no shared components, no portability, and no economies of scale.

Integration cost and complexity. In the absence of a shared standard, the cost of connecting automation devices falls entirely on the hospital — through middleware procurement, bespoke development, and ongoing maintenance. This cost is a barrier to automation adoption, particularly for smaller institutions, and diverts pharmacy IT resources away from higher-value work.

Traceability gaps. Without standardised message exchange, audit trails for medication movements between automation devices are fragmented. Reconstructing the chain of custody for a medication across a multi-vendor environment is manual, error-prone, and incomplete.

Regulatory alignment. The European Health Data Space (EHDS) and evolving national frameworks increasingly require structured, traceable, interoperable data from clinical systems — including systems managing medication stock. A shared FHIR standard for pharmacy automation positions hospitals to meet these requirements without per-system customisation.

### Integration Overview
An overview of the integration with some sample messages is available here:
[Overview and sample messages](Overview.html)

### About FHIR Shorthand

The FSH IG includes the following information:

1. This page, providing introductory material  _(informative content)_.
1. [FHIR Shorthand Overview](overview.html) -- Introduction to FSH language and SUSHI (a reference implementation and _de facto_ standard FSH compiler) _(informative content)_.
1. [FHIR Shorthand Language Reference](reference.html) -- The syntax and usage of the FHIR Shorthand language _(formal content)_.
1. [Quick Reference Card](FSHQuickReference.pdf) -- A cheat sheet for FSH syntax and examples _(informative content)_.
1. [FSH Grammar](https://github.com/FHIR/sushi/tree/v3.8.0/antlr/src/main/antlr) -- An [ANTLR v4](https://www.antlr.org/) representation of the FSH syntax _(informative content)_.
1. [Change Log](change_log.html) -- A history of changes to the FHIR Shorthand specification _(informative content)_.
1. [Full Implementation Guide Zip File](full-ig.zip) -- A downloadable zip file containing the HTML and supporting files for this full specification.


The following materials, useful for learning and applying FHIR Shorthand but not part of the language specification, are found on [FSHSchool.org](https://fshschool.org/):

1. [SUSHI User Guide](https://fshschool.org/docs/sushi/) -- SUSHI ("SUSHI Unshortens ShortHand Inputs") is a reference implementation and _de facto_ standard interpreter/compiler for FHIR Shorthand. SUSHI produces [Health Level Seven (HL7®) Fast Healthcare Interoperability Resources (FHIR®)](https://hl7.org/fhir/R5/overview.html) profiles, extensions, and other artifacts needed to create FHIR Implementation Guides (IG).
1. [GoFSH User Guide](https://fshschool.org/docs/gofsh/) -- GoFSH is a tool that turns FHIR artifacts into FSH. Using GoFSH, existing FHIR artifacts or complete Implementation Guides can be transformed into FSH, automatically.
1. [FSH Visual Studio Code Extension Overview](https://fshschool.org/docs/vscode/) -- The FSH Visual Studio Code extension provides syntax highlighting, code snippets, path completion, and other features that improve FSH authoring efficiency. 
1. [FHIR Shorthand Tutorials](https://fshschool.org/docs/tutorials/) -- A step-by-step hands-on introduction to producing an Implementation Guide (IG) with FHIR Shorthand and SUSHI.
1. [FHIR Shorthand Seminar](https://fshschool.org/courses/) -- A comprehensive overview of FHIR IG authoring basics for people who are interested in being able to independently create FHIR IGs.
1. [FSH Online](https://fshschool.org/FSHOnline/#/) -- A coding playground for FSH, an online environment that allows you to write FSH and convert it to FHIR artifacts, convert FHIR artifacts to FSH, access examples, and share FSH code with others.
1. [FSH Finder](https://fshschool.org/fsh-finder/) -- A list of public GitHub repositories that contain FSH code, refreshed daily.

Note that the [Language Reference](reference.html) is the formal specification, and if there is any conflict between that and any other written or programmatic materials, the former is considered the source of truth.

#### Version Number

FHIR Shorthand follows the same modified [semantic versioning](https://semver.org/) approach as FHIR. See the documentation on versioning in [FHIR Releases and Versioning](https://hl7.org/fhir/R5/versions.html#versions) for more detail. Implementers are encouraged to clearly indicate what version or versions of the FSH specification they implement.


<!-- The following are hidden since they are irrelevant in a documentation-only IG but are required by IG Publisher -->
<!-- See: https://chat.fhir.org/#narrow/stream/179252-IG-creation/topic/Orphaned.20xhtml.20fragments.3F/near/370611655 -->
<div style="display:none" markdown="1">

#### Cross Version Analysis
{% include cross-version-analysis.xhtml %}
#### Dependency Table
{% include dependency-table.xhtml %}
#### Globals Table
{% include globals-table.xhtml %}
#### IP Statements
{% include ip-statements.xhtml %}

</div>

### Issue Reporting and Contributions

* FSH language issues and suggestions can be made [in the HL7 Jira](https://jira.hl7.org/issues/?jql=project%20%3D%20FHIR%20AND%20Specification%20%3D%20%22Shorthand%20(FHIR)%20%5BFHIR-shorthand%5D%22). When filing FSH language or IG issues, use project="FHIR" AND Specification = "Shorthand (FHIR) [FHIR-shorthand]".

* SUSHI bugs, issues, and suggestions can be made [here](https://github.com/FHIR/sushi/issues).

* GoFSH bugs, issues, and suggestions can be made [here](https://github.com/FHIR/GoFSH).

* If your FSH project is not listed in FSH Finder, log an issue [here](https://github.com/FSHSchool/fsh-finder/issues) or submit a pull request on the list of organizations in [settings.yml](https://github.com/FSHSchool/fsh-finder/tree/v1.1).

* FSH examples for inclusion in FSH Online can be contributed [here](https://github.com/FSHSchool/FSHOnline-Examples).


### Participants

| Organization | Role |
|----|----|
| Alphatron | Reviewer |
| Sinteco | Contributor |
| BD | Contributor |
| Deenova | Contributor |
| JVM | Contributor |
| GPI | Contributor |
| Grifols | Contributor |
| Omnicell | Contributor |
| Stockart | Contributor |
| Swisslog | Contributor |
{: .grid } 


