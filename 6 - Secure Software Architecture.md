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
The attack surface of software is the code within the system that can be accessed by unauthorized parties. This is not just the code itself bu also can include a wide range of resources associated with the code, including user input fields, protocols, interfaces, resource files, and services.

One measure of the attack surface is the number or the weigthed number of accessible items. The more elements that can be attacked, the greater the risk. The attack surface of the software does not represent the quality of the code, it does not mean where are flaws; it is merely a measure of how many features/items are available for attack.

A long-standing security practice is not to enable functionality that is not used or needed. By turning off uneccessary functionality, there is a smaller attack surface, and there are fewer security risks. Attack surface evaluation is a means of measuring and determining the risks associated with the implications of design and development.

### Attack Surface Measurement
To understand a product's attack surface, you need to measure the number of ways it can be "accessed".

 - Opens Sockets
 - Open RPC endpoints
 - Open named pipes
 - Services
 - Services running by defaults
 - Services runnin as SYSTEM
 - Active web handlers (ASP files, HTR files, and so on)
 - Active Internet Server Application Programming Interface (ISAPI) filters
 - Dynamic webpages (ASP ans such)
 - Executable virtual directories
 - Enabled accounts
 - Enabled accounts in admin group
 - Null sessions to pipes and shares
 - Guest account enabled
 - Weak ACLs in the file system
 - Weak ACL in the registry
 - Weak ACL on shares

Another source of information is in the history of known vulnerabilities associated with previous developments. Determining the root cause of old vulnerabilities is good for fixing them and preventing future occurrences, and it is also valuable informatyion that can be used in determining the attack surface.
The items on the list are not neccesesary vulnerabilities, but they are items that attackers will attempt to compromise.
Different elements may have different scoring values, as a service running as a system is riskier than a nonprivileged service. Services that are run by default are riskier than those on the same level running only on the demand.

### Attack Surface Measurement

This can done by turning off elements not needed by most users. Services that are used can be on or off bu default, only on when needed, run as system, or without privilege. The lower the priviolege, the less a service is running, so these factors can reduce the attack surface. Some elements may be off for most users, yet on for specific users under appropiate circumstances. Minimization is a form of **least privilege**, and the application of it works in the same manner. If the application is network aware, restricting access to a set number of endpoints or a restricted IP range reduces the surface.

As with all changes, the earlier in the development process a change is made, the lesser the impact will be to surrounding elements. Attack surface minimization should be considered with design efforts.

### Threat Intelligence

Threat Intelligence is the actionabale information about malicious actors, their tools, infrastructure and methods. Threat Intelliogence combined with the concepty of kill chain (the attacker's most likely path) means you can prioritize actions against most meaningful threats. The vast majority of attacks on software upon a ten vulnerabilities (97% of attacks against companies in 2014).

As developers include third-party, open source, and commercial libraries into their projects, these resources must be watched for newly discovered vulnerabilities. Understanding what is beign attacked, and how, is important infromation for the development team.

### Threat Hunting &nbsp;&nbsp; ![White Paper](Resources\38710.pdf)

Threat hunting is an interactive process of proactively searching out threats inside the network. One of the most effective is based on creating a hypothesis and then examining that hypothesis. A typicqlal hypothesis woul be something like "an adversary is using stolen credentials to mimic authorized users during nonworking hours".
&nbsp;

---

## Security Architecture

The new system is designed to meet requirements and then joins the other systems in the enterprise. Cross-integration between architectures allows data reuse and significantly increases the overall utility of the enterprise architecure as a whole. Getting the true benefit of a security architecture requires that it be a planned element to support the desired security outcomes. This is important in both new greenfield projects and updates and exapansions of existing systems.


