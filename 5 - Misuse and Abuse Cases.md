# Misuse and Abuse Cases
Use case have been used for years to contextualize how software is to be used, conveying requirements with respect to function to developers. <u>Misure Case</u> provide the opposite case, a set of requirements that should specifically not be allowed.
The Misuse Case is when a user attempts to do something that should be prohibited. They can be considered a form of use case illustrating specifically prohibited actions ensuring that these issues are also tested as another form of defense. Misuse Cases can examine a system from an attacker's point of view, whether the attacker is an inside threat or an outside one. Properly constructed misuse cases can trigger specific test scenarios to ensure known weaknesses have been recognized and dealt with appropiately before deployment.

SAFECode has made an useful document describing "[Practical Security Stories and Security Task for Agile Development Environments](./SAFECode_Agile_Dev_Security0712.pdf)"

Security failures occur whenever software performs a function that is not authorized, whether by bad input (hostile attacker) or environment conditions (errors or unseen conditions). Some threats are caused bu things that are not necessary intelligent. Such causes include human error, storms, design errors (e.g. software bugs), interference or noise across communication links. Misuses Cases provide a means to model these conditions and test them during the course of software development.
It is important for all misuse cases to be properly mitigated, else they represent a threat and potential risk to the system.

### Requirements Traceability Matrix (RTM)
The Requirements Traciability Matrix (RTM) is a grid that assits the development team in tracking and managing requirements and implementation details. The RTM assists in the documentation of the relationships between security requirements, controls, and test/verification efforts.

| **Requirement ID** | **Requirement Description**                                  | **Source**        | **Module/Component**    | **Use Case** | **Test Case ID**    | **Status**       |
|--------------------|---------------------------------------------------------------|-------------------|--------------------------|--------------|----------------------|------------------|
| REQ-001            | The user must be able to log in                               | Stakeholder A     | Authentication           | UC-01        | TC-001               | Verified         |
| REQ-002            | The system must send a registration confirmation email        | Requirements Doc  | Notifications            | UC-02        | TC-002               | In Progress      |
| REQ-003            | The system must allow product search                          | Stakeholder B     | Product Search           | UC-03        | TC-003, TC-004       | Not Started      |
| REQ-004            | The system must work on mobile devices                        | UX Guidelines     | All                      | -            | TC-005               | Verified         |
| REQ-005            | User data must be encrypted                                   | Security Policy   | Security                 | UC-04        | TC-006               | In Progress      |



### Contractual Terms and Service Level Agreements
Contractual tems and service and service level agreements are used to estabilish expectations with respect to future performance. Contractual terms when purchasing software should include references to security controls or stndards that are expected to be implemented. Specific ISO standards or NIST standards that are desired by a supplier should be included in these mechanisms to ensure clear communication of expectations. Service level agreements can include acceptance criteria that software is expected to pass prior to integration.

### Terminology
- COTS = Commercial Off-The-Shelf
This term describes an element that is readily available for purchase and integration into a system.
- GOTS = Governament Off-The-Shelf
This term refers to software that is specifically developed for governament use.
- SBOM = Software Bill Of Materials
A movement where software vendors provide documentation of what is in their software. As companies become more risk aware of software vulnerabilities and dependencies, theey are incorporating language into their purchasing contracts that bring requirements with respect to many aspects of software development. The Open Web Application Security Project (OWASP) has some model contract information covering the elements that need to be determined as part of a contract negotiation. 

| Principle                                   | Description                                                                                                                                   |
|---------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| **Security Decisions Will Be Based on Risk** | Decisions about security will be made jointly by both Client and Developer based on a firm understanding of the risks involved.              |
| **Security Activities Will Be Balanced**    | Security effort will be roughly evenly distributed across the entire software development lifecycle.                                          |
| **Security Activities Will Be Integrated**  | All the activities and documentation discussed herein can and should be integrated into Developer’s software development lifecycle and not kept separate from the rest of the project. Nothing in this Annex implies any particular software development process. |
| **Vulnerabilities Are Expected**            | All software has bugs, and some of those will create security issues. Both Client and Developer will strive to identify vulnerabilities as early as possible in the lifecycle. |
| **Security Information Will Be Fully Disclosed** | All security-relevant information will be shared between Client and Developer immediately and completely.                                     |
| **Only Useful Security Documentation Is Required** | Security documentation does not need to be extensive in order to clearly describe security design, risk analysis, or issues.                 |

Testing requirements and code bases can be very sensitive contractual issues as it can expose the source code, which in most cases is sensitive intellectual property.
