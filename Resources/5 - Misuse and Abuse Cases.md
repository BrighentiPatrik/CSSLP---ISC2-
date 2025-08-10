# Misuse and Abuse Cases
Use case have been used for years to contextualize how software is to be used, conveying requirements with respect to function to developers. <u>Misure Case</u> provide the opposite case, a set of requirements that should specifically not be allowed.
The Misuse Case is when a user attempts to do something that should be prohibited. They can be considered a form of use case illustrating specifically prohibited actions ensuring that these issues are also tested as another form of defense. Misuse Cases can examine a system from an attacker's point of view, whether the attacker is an inside threat or an outside one. Properly constructed misuse cases can trigger specific test scenarios to ensure known weaknesses have been recognized and dealt with appropiately before deployment.

SAFECode has made an useful document describing "[Practical Security Stories and Security Task for Agile Development Environments](..\SAFECode_Agile_Dev_Security0712.pdf)"

Security failures occur whenever software performs a function that is not authorized, whether by bad input (hostile attacker) or environment conditions (errors or unseen conditions). Some threats are caused bu things that are not necessary intelligent. Such causes include human error, storms, design errors (e.g. software bugs), interference or noise across communication links. Misuses Cases provide a means to model these conditions and test them during the course of software development.
It is important for all misuse cases to be properly mitigated, else they represent a threat and potential risk to the system.

### Requirements Traceability Matrix (RTM)
The Rquirements Traciability Matrix (RTM) is a grid that assits the development team in tracking and managing requirements and implementation details. 