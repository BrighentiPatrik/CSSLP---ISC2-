# Data Classification
Data can be classified as to its state, its use, or its importance from a security prospective. Data classification is a risk management  tool, with the objective to reduce the costs associated with proteccting data. In large enterprised, it may be desirable to actually determine separate, differing protection needs based on data attributes such as confidentiality, integrity, and availability.

### Data States
Data can be considered a static item that exists in a particular state at any given time:
- At rest, or being stored
- Being created
- Being transmitted from one location to another
- Being changed or deleted

When considering data states, it is easy to expand this idea to the information lifecycle model (ILM), which includes generation, retention, and disposal.

### Data Usage
Data can be classified as to how it is going to be used in a system. This is meant to align the data with how it is used in the business. The classificaation includes:
- **Internal Data**: initialized in the application, used in an internal representation, or computed within the application itself.
- **Input Data**: read into a system and possibly stored in an internal representation or used in a computation and stored.
- **Output Data**: written to an output destination following processing.

In addition, data can be considered security sensitive, marked as containing personally identifiable information (PII) or to be hidden. These categories include:
- **Security-sensitive data**: A subset of data of high value to an attacker.
- **PII data**: that contains PII elements.
- **Hidden data**: that should be concealed to protect it from unauthorized disclosure using obfuscation techniques. 

### Data Risk Impact
Data can be classified as to the specific risk associated with the loss of the data. Usually labeled:
- **High**: Data that is labaled high risk is data that if disclosed or lost could result in severe adverse effect on assests, operations, or people.
- **Medium**: Data that is labeled medium risk is data that if disclosed would have serious consequences.
- **Low**: Low-Risk data is data that has limited, if any, consequences if disclosed.

Each firm, as part of its data management plan, needs to determine the appropriate definitions of severe, serious, and limited, both from a <u>dollar loss point of view</u> and from an <u>operational impact</u> and <u>people impact</u> point of view.

Additional labels, such as PII, compilance-related, or for official use only, can be used to alert the development team as to specialized requirements associated with data elements.

<u>NIST FIPS 199</u> and <u>SP 800-18</u> provide a framework for classifing data based on impacts across the three standard dimensions: confidentiality, integrity and avaiability.

### Data Lifecycle
Data in the enterprise has a lifecycle. It can be created, used, stored, and even destroyed. Although data storage devices have come down in price, <u>the total cost of storing data in a system is still a significant resource issue</u>. Data that is stored must also be managed from a backup and business continuity/disaster recovery prospective. Managing the data lifecycle is a <u>data owner's</u> responsibility.

### Generation
If the data is going to be persistent, then it needs to be classified and have the appropiate protection and destruction policies assigned.

### Data Ownership
Data does not really belong to people in the enterprise; it is actually the property of the enterprise or company itself. For practical reasons, data will be assigned to people in a form of an ownership or stewardship role.

### Data Owner
Data owners act in the interests of the enterprise when managing certain aspects of data. The <u>data owner</u> is the party who determines who has specific levels of access associated with specific data elements; who can read, who can write; who can change, delete, and so on.
The owner of the data for the master chart of accounts in the accounting system may be the chief financial officer (CFO), but the ability to directly change it may reside with a database administrator (DBA).
Data owners are responsible for defining data classification, defining authorized users and access criteria, defining the appropiate security controls, and making sure the controls are implemented and operational.
Data owner define the requirements, while  data custodians are responsible for implementing the desired actions.

### Data Custodian
Data custodians support the business use of the data in the enterprise. As such, they are responsible for ensuring that the process safely transport, manipulate, and store the data. Data custodians are aware of the data management policies issued by the data owners and are responsible for ensuring that during operations these rules and regulations are followed. Data custodians are responsible for maintaning defined security controls, managing authorized users and access controls, and performing operational tasks such as backups and data retention and disposal.

Data custodians may not require access to read the data elements. They do need appropriate access to apply policies to the data elements. Wwithout appropiate segregation of data controls to ensure custodians can only manage the data without actually reading the data, confidentiality is exposed to a larger set of people, a situation that may or may not  be desired.

### Labeling
Because data can exist in the enterprise for an extended period of time, it is important to label the data in a manner that can ensure  it is properly handled.


## Privacy
Privacy is the principle of controlling information about one's self: who it is shared with, for what purpose, and how it is used and transferred to other parties.

### Privacy Policy
The  privacy policy is the high-level document that describes the principles associated with the collection, storage, use, and transfer of personal information, within the scope of business.
A customer-facing privacy policy, commonly referred to as privacy disclosure statements, is provided to customers to inform them of how data is protected, used and disposed of in the course of business. In the financial sector the <u>Gramm-Leach-Bliley Act</u> mandates that firms provide clear and accurate information as to how customer information is shared.

### Personally Identifiable Information
Informations that can be used to specifically identify an individual. One of the primary challenges associated with PII is the effect of data aggregation. Obtaining several pieces from different sources, a record can be constructed that permits the identification of a specific individual.

<u>Common PII Elements</u>:
- Full Name
- National Identification Number
- IP Address
- Home Address
- Motor Vehicle Registration Plate Number
- Driver's License or State ID number
- Face, Fingerprints, or Hardwriting
- Credit Card and Bank Account Number
- Date of Birth
- Birthplace
- Genetic Information

To identify an individual, only a small subset may be needed. A study by Carnegie Mellon University found that nearly 90 percent of the U.S. population could be uniquely identified with only gender, date of birth, and ZIP code.

### Personal Health Information
Personal Health Information, also sometimes called <u>Protected Health Information</u>, is the set of data elements associated with an individual's healthcare that can also be used to identify a specific individual (demographic data, medical test data, biometric measurements, and medical history information). This data can have significant risk factors to an individual should it fall into the possession of unauthorized personnel. For this reason, as well as general privacy concers, PHI is protected by a series of statutes, including HIPAA and the HITECH Act.

### Breach Notifications
Data Breaches trigger a series of events. First is the internal incident response issue. In a separate vein, customers whose data was lost deserve to be informed.

### GDPR - General Data Protection Regulations
The Safe Harbor principles that once allowed the harmonization of U.S. and EU privacy rules no longer are sufficient. GDPR has made these methods obsolete, and GDPR rules must be followed for customers in the EU.
In the Charter of Fundamental Rights of the EU there is the foundamental right to the protection of personal data, including when such data elements are transferred outside the EU.
The GDPR brings many changes, one being the appointment of a data protection officer (DPO). This role may be filled by an employee or a third-party service provider (for example, consulting or law firm), and it must be a direct report to the highest management level. The DPO should operate with significant independence, and provisions in the GRPR restrict control over the DPO by management.
The GDPR specifies requirements regarding consent, and they are significantly more robust than previous regulations.

- Informed/affirmative consent to data processing. Specifically "a statement or a clear affirmative action" from the data subject must be "freely given, specific, informed and unambigous".

- Explicit consent to process special categories of data. Explicit consent is required for "special categories" of data, such a generic data, biometric data, and data concerning sexual orientation.

- Explicit parental consent for children's personal data.

- Consent must be specific to each data-processsing operation, and the data subject can withdraw consent at any time.

The GDPR provides protection for new individual rights, and these may force force firms to adopt new policies to address these requirements. The rights include:
- Right to Information
- Right to Access
- Right to Rectification
- Right to Restrict Processing,
- Right to Object
- Right to Erasure
- Right to Data Portability

The GDPR also recognizes the risks of international data transfer to other parties and has added specific requirements that data protection issues be addressed by means of appropriate safeguards, including binding corporate rules (BCR), model contract clauses (MCC), also knows as standard contractual clauses (SCC), and legally blinding documents.
GDPR demands that individuals must have full access to information on how their data is processed, and this information should be available in a clear and understandable way. When companies obtain data from an individual, some of the issues that must be made clear to the individual whose data is being collected are:
- The identity and contract details of the organization behind the data request (who is asking)
- The porpouse of acquiring the data and how it will be used (why they are asking)
- The period of which the data will be stored (how long will keep it)
- Whether the data will be transferred internationally (where else it can go)
- The individual's right to access, rectify, or erase the data (right to be forgotten)
- The individual's right to widthdraw consent at any time (even after collection)
- The individual's right to lodge a complaint

### Privacy-Enchancing Technologies (PET)
One principal connection beetween information security and privacy is that without information security, you cannot have privacy. Just as technology has enabled many privacy-impacting issues, technology also offers the means in many cases to protect privacy. An application or tool that assists in such protection is called a <u>privacy-enhancing technology</u>
For example: PGP and TOR.
Other PETs are for example <u>cookie cutters</u> that are designed to prevent the transfer of cookies between browser and web servers. Some cookie cutters block all coockies, while others can be configured to selectively block certain cookies. Some cookie cutters also block the sending of HTTP headers that might reveal personal information but might not be necessary to access a website, as well as block banner ads, pop-up windows. Other PET tools are designed specifically to look for invisible images that set cookies (called <u>web beacons</u> or <u>web bugs</u>).

### Data Minimization
Data Minimization is one of the most powerful privacy-enhacing technologies. Limiting the collectionn of personal information to that which is directly relevant and necessary to accomplish a specified purpose. It also reduces risk from future breached and disclosures by not keeping "excess" data.

### Data Masking
Data Masking involves the hiding of data by substituting altered values. A mirror version of a database is created, and data modification techniques such as character shuffling, encryption, and word or character substitution are applied to change the data. Data Masking makes reverse engineering or detection impossible. <u>Data Masking hides personal or sensitive data but does not render it unusable</u>.

### Tokenization
Tekenization is the use of a random value to take the place of a data element that has treaceable meaning. A good example is a credit card approval, the transaction agent returns an approval code, which is a unique token to that transaction. Tokenization is not an encryption step beacuse encrypted data can be decrypted. <u> Tokenization assigns a random value that can be traced back to the original data without reveal it</u>.

### Anonymization
Data anonymization is the process of protecting private or sensitive information by removing identifiers that connect the stored data to an individual. Data anonymization is easier said that done, beacuse data exists in many forms. Specially is difficult to prevent attack based on aggregation of this data.

### Pseudo-Anonymization
Pseudo-anonymization is tthe de-identifications method that replaces private identifier withy fake identifiers or pseudo-identifiers. That is import beacuse preserves statistical accuracy and data integrity, allowing the modified data to be used for training, development, testing, and analytics while protecting data privacy.