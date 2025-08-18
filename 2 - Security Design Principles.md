## Security Design Principles

**_Good Enough Security_**
Every system has some appropriate level of required security; and it's important to determine this level early in the design process.
It's a trade-off between security and other aspects of a system.

**_Least Privilege_**
Least privilege means that a subject should have only the necessary rights and privileges to perform its current task with no additional rights and privileges. All programs, scripts, and batch files run inder the security context of specific user on an operating system.

**_Separation of Duties_**
Separation of Duties ensure that for any given task, more than one individual needs to be involved. the critical path of tasks is split into multiple items, which are then spread across more than a single party.

_**Defense in Depth**_ **&rarr;** **_Layered Security_**
For the layers to be diverse, they should be dissimilar in nature so that if an adversary makes it past one layer, another layer may still be affective in maintaining the system in a secure state. Defense in Depth provide security against many attack vector.

![Diagramma di Venn](Resources/DefenseInDepth.svg?raw=true)

_**Fail-Safe**_
The Fail-Safe design principle is that when a system experiences a failure, it should fail to a safe state. One form of implementation is to use the concept of __explicit deny__. Any function that is not specifically authorized is denied by default.

_**Economy of Mechanism**_
The KISS (Keep-It-Simple-Stupid) principle tells us to eliminate those that we don't need. The general rule of thumb should be to always eliminate all nonessential services and protocol.

_**Complete Mediation**_
This principle states that when a subject's authorization is verified with respect to an object and an actions, this verification occurs every time the subject requests access to an object.

_**Open Design**_
This principles state that the security of a system must be indipendent from the secrecy of the design. Like the modern criptographic alghoritms that the security depends upon the secrecy of the key instead of the secrecy of the alghoritm.

_**Least Common Mechanism**_
Refers to a design method designed to prevent inadvertent sharing of information. Instead of have a single procces that operates on a range of objects implement a specialized procces for all of them.
This principles create a conflict with the Leverage Existing Components principles. The designer must choose  the correct balance 
between the two.

_**Psychological Acceptability**_
Too much security could push the user to circumvent it to perform prohibited actions.

_**Weakest Link**_
A system can be considered only as strong as its weakest link.

_**Leverage Existing Components**_
Component reuse has many business advantages, including increases in efficency and security. This is a semplicistic form of reducing attack surface area. The downside of a massive reuse is associated with a monocolture environment, which is where a failure has a larger footprint.

_**Single Point of Failure**_
A single point of failure is any aspect of a system that, if it fails, means the entire system fails. It is imperative for a secure system to **NOT** have any single point of failure. The design of a software system should be such that all points of failure are analyzed and a single feature does not result in system failure.

### X.509 Certificates & PKI (Public Key Infrastructure)

-**X.509**: In cryptography, X.509 is an International Telecommunication Union (ITU) standard defining the format of public key certificates. An X.509 certificate binds an identity to a public key using a digital signature. A certificate contains an identity (a hostname, or an organization, or an individual) and a public key (RSA, DSA, ECDSA, ed25519, etc.), and is either signed by a certificate authority or is self-signed. When a certificate is signed by a trusted certificate authority, or validated by other means, someone holding that certificate can use the public key it contains to establish secure communications with another party, or validate documents digitally signed by the corresponding private key.

-**PKI - Public Key Infrastructure**: is a set of roles, policies, hardware, software and procedures needed to create, manage, distribute, use, store and revoke digital certificates and manage public-key encryption. 

A trusted pki is used to implement all the fundamental security goals: Confidentiality,Integrity,Authenticity and Non-Repudiation.

![Diagramma di Venn](Resources/CIA+.png?raw=true)

![Diagramma di Venn](Resources/MITM.png?raw=true)

![Diagramma di Venn](Resources/PKIEntities.png?raw=true)

![Diagramma di Venn](Resources/CErtificateSchema.png?raw=true)
la signature è una cifratura (tramite private-key della CA) dell'hash del certificato

- **End-entities**: User or subject of X.509 certificate. Can be natural persons (e.g., Alice), legal persons (e.g., IBM), machines or applications and services (e.g., IoT devices, web servers)

- **Registration Authorities (RA)**: System delegated by a CA to perform identification of users applying for X.509 certificate. An RA is mostly accessed via user-friendly GUIs or APIs.

- **Certificate Authorities (CA)**: Collections of HW, SW, personnel and operating procedures delegated to create, issue, and revoke X.509 certificates

- **Repository**: System storing X.509 certificates and CRLs and providing means for access and distribution

openssl req x509 -newkey rsa:4096 -days 3650 -keuout RootCA.key -out RootCA.crt -subj '/C=CH/ST=Zurich/O=ExampleOrg/CN=ExampleOrg Root CA' -addext "keyUsage=cRLSign,keyCertSign"

openssl x509 --in RootCA.crt -text

openssl rsa -in RootCA.key -noout --text

Confidentiality --> Encription
Integrity --> Cripthographic Hash Function
Authenticity --> HMAC, Message authentication codes, authenticated encryption
Non-Repudiation --> Digital Signature


***
### Security Model

_**Access Control Model**_:
Access controls define what actions a subject can perform on specific objects. There are a variety of different access control models that emphasize different aspects of protection scheme.

- **ACL - Access Control List**: is a list that contains the subjects, but also the specific access that subject has for the object. Usually also the specific access that subject has for the object.
&nbsp;

-  **MAC - Mandatory Access Control**: restricts access based on the sensitivity of the information and whether the user has the authority to access that information. The owner or the subject CANNOT determine whether accesss is to be granted to another subject. It is the job of the S.O. This mechanism requiring that all objects and subjects relationships be defined before use in a system.
&nbsp;

-  **DAC - Discretionary Access Control**: A means of restricting access to objects based on the identity of subjects and/or groups to which they belong. The owner of an object can decide which other subjects may have access to the object and what specific access they may have.
&nbsp;

- **RBAC - Role-Based Access Control**: Users are associated with a set of roles. each role, in turn, is assigned with spicific persions on specific objects. Users will thus be granted permissions necessary to perform the tasks associated with them.
&nbsp;

- **RBAC#2 - Rule-Based Access Control**: Less common, a series of rules is contained in the access control list, and the determination of whether to grant access will be made based on these rules.
&nbsp;

-  **Access Control Matrix**: is a semplified form of access control notation where the allowed actions a subject is permitted with an object are listed in a matrix format.
&nbsp;

-  **Attribute-Based Access Control**: is a schema based on the use of attributes associated with an identity. These can use any type of attributes (user attributes, resource attributes, enviornment attributes) such as location, time, activityy being requested, ecc...
XACML - eXtensible Access Control Markup Language is a standard that implements attribute- and policy - based access control schemes.
&nbsp;

- **Bell-LaPadula Confidentiality Model**: is a confidentiality preserving model based on mandatory (MAC) and discrectionary (DAC) model. It has two principles:
&nbsp;
     - _**Simple Security Rule (no-read-up)**_: no subject can read information from an object with a security classification higher than that possesed by the subject itself.
     &nbsp;

     - _***property (no-write-down)**_: A subject can write to an object only if its security classification is less than or equal to the object's security classification.
&nbsp;

- **Take-Grant Model**: is built upon graph theory. 
 &nbsp;![Diagramma di Venn](Resources/TakeGrantModel.png?raw=true)
***

### Integrity Model
Integrity-based models are designed to protect the integrity of the information. For some types of information, integrity can be as importants as, or even more important than, confidentiality. Public information, such as stock prices, is available to all, but the correctness of their valuen is crucial, leading to the need to ensure integrity.

- **Biba Integrity Model**: integrity levels are used to separate permissions.
It has two principles:
     - **low-water-markup-policy (no-write-up)**: This policy prevents subjects from writing to objects of a higher integrity level. 
     - **integrity\* property (no-read-down)**: A subject cannot read an object at a lower integrity level.

  In this model, the level of trust you can place in data cannot be higher than the level of subjeect creating the new data object.
&nbsp;

- **Clark-Wilson Model**: use _transaction_ as base of its rules. 
It defines two levels of _data_ based of they integrity constraint:
     - **CDI - Constrained Data Items**: which is subject to integrity control.
     - **UDI - Unconstrained Data Items**: which is NOT subject to integrity control.
  &nbsp;
  
  Changes to the data are performed by two types of _process_:
     - **IVP - Integrity Verification Processes**: ensure that CDI meets integrity constraints (to ensure the system is in a valid state)
     - **TP - Transformation Processes**: change the state of data from a valid one to another.
  &nbsp;
  > The Clark-Wilson model is a security model that focuses on ==data integrity rather than confidentiality==. It is particularly suited for commercial and financial environments, where it is essential to ensure that data is not altered in an unauthorized manner.
The Clark-Wilson model is designed specifically to prevent anyone from modifying data directly in the database.
In a system that follows the Clark-Wilson model:
-Direct SQL privileges on the DB are removed for users and developers.
-The only operations allowed are those via APIs, software, or approved procedures.
-There is control at the operating system, DB, and application levels to enforce this architecture.
-Manual changes are detected and reported as integrity violations.



&nbsp;
- **Brewer-Nassh Model (Chinese Wall)**: is a context-based access control model designed to handle situations where avoiding conflicts of interest is critical.
It is a dynamic security model that changes a user's access permissions based on the data they have already accessed. It is used for avoid conflicts of interest between different companies or customers in the same system.
&nbsp;
This is especially useful in environments such as:
  - Law firms
  - Consulting firms
  - Financial firms
  &nbsp;
  
  📋 Key principles
     - Dynamically controlled access
     - Access to certain data is blocked or allowed based on the user's past access.
     - Information is divided into conflict of interest classes (COI).
     
     &nbsp;
     If a user logs into a company in a COI, they can no longer access data from other companies in the same COI.
     Rights change over time: a user can initially access everything, but after the first login, constraints are activated.

  | Modello           | Focus principale           | Tipo di controllo |
  | ----------------- | -------------------------- | ----------------- |
  | **Bell-LaPadula** | Confidenzialità            | Statico           |
  | **Biba**          | Integrità                  | Statico           |
  | **Clark-Wilson**  | Integrità + separazione    | Statico           |
  | **Brewer-Nash**   | **Conflitti di interesse** | **Dinamico**      |


***
**Data Flow Diagrams - DFD**: are specifically designed tyo document the storage, movement and processing of data in a system.

**Use Case Model**: examines the system from a functional prospective model. Use cases are constructed to demonstrate how the system processes data for each of its defined functions. Use cases can be consteructed for both normal and abnormal (misuse cases) to facilitate the full description of how the system operates.

**Assurance Models**
The Committee on National Security Systems has defined ==software assurance== as the "level of confidence that software is free from vulnerabilities, either intentionally designed into the software or accidentally inserted at any time during its lifecycle, and that the software functions in the intended manner.


**Operational Model of Security**
| Prevention     | Detection                    | Response                |
| -------------- | ---------------------------- | ----------------------- |
| Access Control | Audit Logs                   | Backups                 |
| Firewalls      | Inbtrusion detection Systems | Incident Response teams |
| Encryption     | Honeypots                    | Computer Forensics      |

