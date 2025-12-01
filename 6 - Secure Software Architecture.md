## Secure Software Architecture

### Threat Modeling
Threat Modeling is a process used to identify and document all of the threats to a system. Part of the description will include the mitigation actions that resolve the exposure. Performing Threat Modeling from the beginning of the development process helps highligth the issues that need to be resolved early in the process. Threat Modeling is an entire team effort, with everyone having a role in the complete documentation of the threatsand issues associated with the software.

#### Threat Model Development
Theat Model development process is a team-based process. It has several phases:
- **Identify Security Objectives**: These requirements can come from a number of sources, including legal, contractual, and corporate standards and objectives.
Leaving the decision of what data to protect and how to protect it to a development team is a mistake, as they may not have the breadth or depth of knowledge with the respect to these requirements to catch all of the possible associated threats. <u>Laws, regulations, contractual requirements, and even corporate standards</u> can be complex and byzantine, yet if they are to be properly covered, they need to be enumerated as a list of requirements for the development effort.
&nbsp;
- **System Decomposition**: Once the security objectives are definend for a system, designers need to ensure they are covered in the actual design of the system. Numerous modeling system are used in the design of a system (UML,use cases,misuse cases, DFD, ... ) When using DFD (Data Flow Diagrams) it is important to identify and include all process, data stores, and data flows between elements. Special attention should be given to **trust boundaries**, where data crosses from one zone of trust to another. In large, complex systems, **breaking down the DFD into scenario-based pieces may make documentation easier**. Every assumprion and every dependency should be enumerated and described.
<u>As the development process progresses, any changes to the items in the Threat Model should be documented and updateted</u>.
&nbsp;
  > **DFD elements for Threat Modeling**
  The following are examples of elements to identify as part of the threat modeling process:
  **External Entities**
  -Users (by type)
  -Other Systems
  **Data Stores**
  -Files
  -Databases
  -Registries
  -Shared Memory
  -Queues/Stacks
  **Trust boundares**
  -Users
  -File Systems
  -Process Boundares
  **Data Flows**
  -Function Calls
  -Remote Procedure calls (RPCs)
  -Network Traffic

&nbsp;
- **Threat Identification** 
&nbsp;
Once the system is well documented, the the process of identifying threats begins. The use of the STRIDE method can be repeated across processes, data flows, trust boundaries and enywhere. Using the elements of the STRIDE, the threat model is documented as to what happens as a result of each element of the **STRIDE** acronym.
  | Threat                 | Security Property |
  |------------------------|-------------------|
  | Spoofing               | Authentication    |
  | Tampering              | Integrity         |
  | Repudiation            | Nonrepudiation    |
  | Information Disclosure | Confidentiality   |
  | Denial of service      | Aviability        |
  | Elevation of privilege | Authorization     |
&nbsp;

- **Mitigation Analysis**
&nbsp;
  - <u>Redesing to eliminate vulnerability</u>: If it may be in the early parts of the development process, this is the best method. For the threat that is documented late in the development cycle, elements such as redesign may not be pratical for this release. But the information can still documented, and on the next release of the software, redesign may be an option that improves the security.
  - <u>Apply a Standard Mitigation</u>: are common security functions, such as access control list (ACL), and have several advantages. First, they are well understood and are known to be effective. Second, they will apply across large number odf specific vulnerability points, making them an <u>economical choise</u>.
  - <u>Developing new mitigation methods</u>: is riskier and more costly, as it will require more extensive testing.
  - <u>Accepting the Vulnerabilities</u>: is the least desired solution, but may on occasion be the only option.

  &nbsp;

  To picking the appropriate mitigation method a useful tool is an **Attack Tree** as shown in the figure belowe.
  &nbsp;

  ```mermaid
  graph TD
  A[Obtain authentication coockie to spoof identity] --> B{Scenario A}
  B --> C[Coockie travel over Unencrypted HTTP]
  B --> D[Attacker uses sniffer to monitor HTTP traffic]

  A --> F{Scenario B}
  F --> G[Attacker possesses means and knowledge]
  F --> H[Application is vulnerable to XSS attacks]
  ```
  &nbsp;
  When describing a threat, it is a useful to gauge the priority with risk management methodology. **Probability** <u>represents the likelihood that the attack will have success</u>. **Impact** <u>represents the loss or risk faced by a successful attack</u>. After this, you could perform a **Probability Impact Modeling** like **Risk Total= Probability X Impact**. The resulting scores will be between 9 and 1.
  &nbsp; 
  **DREAD**&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Nothing-->Moderate-->Severe] 
  &nbsp;
  - **D**amage potential &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[0-->5-->10] 
  - **E**xploitability &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[0-->5-->10] 
  - **R**eproducibility &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[0-->5-->10] 
  - **A**ffected users &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[0-->5-->10] 
  - **D**iscoverability &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[0-->5-->10] 
  &nbsp;
  
  - Then the **Risk Total** can be obtained by summing and dividing by 5, which will yeld a score from 0 to 10.
  - Antoher way is to set the discoverability to 10, assuming discovery when doing the analysis.
  - DREAD can be mapped into the probability impact mo0del by taking the following factors into account: **Probability = (Reproducibility + Exploitability + Discoverability)** and **Impact = (Damage Potential + Affected Users)** 

&nbsp;
- **Theat Modeling Validation**
The purpose of the validation phase is to assess the quality of the threats and mitigations.

---

### Attack Surface Evaluation
