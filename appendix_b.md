# Appendix B: Ethical Hacking Essential Concepts - II

## Information Security Management Program

... designed to enable a business to operate in a state of reduced risk.

## Enterprise Information Security Architecture (EISA)

... is a set of requirements, processes, principles, and models that determines the structure and behavior of an organization's information systems.

Goals:

- monitor and detect network behaviors in real time
- detect and recover from security breaches
- monitor various threats
- benefits organization's budget in cost prospective
- identify assets
- helps to perform risk assessment

## Information Security Controls

### Administrative Security Controls

... are the administrative access controls implemented by the management to ensure the safety of the organization.

Examples:

#### Regulatory Framework Compliance

... a collaborative effort between governments and private bodies to encourage voluntary improvements to cybersecurity.

#### Information Security Policy

... is the foundation of security infrastructure.

... defines the basic security requirements and rules to be implemented in order to protect and secure an organization's information systems.

Types of...:

- promiscuous
- permissive
- prudent
- paranoid

Examples:

- access control
- remote access
- firewall management
- network connection
- passwords
- user account
- information protection
- special access
- email security
- acceptable use

Privacy policies at the Workplace

HR implications of Security Policy Enforcement

Legal Implications of Security Policy Enforcement

#### Employee Monitoring and Supervising

None

#### Information Classification

None

#### Security Awareness and Training

![Security Awareness and Training](img/security_training.png "Security Awareness and Training")

![Security Awareness and Training: security policy](img/security_policy.png "Security Awareness and Training: security policy")

![Security Awareness and Training: physical security](img/training_physical_security.png "Security Awareness and Training: physical security")

![Security Awareness and Training: social engineering](img/training_social_engineering.png "Security Awareness and Training: social engineering")

![Security Awareness and Training: data classification](img/training_data_classification.png "Security Awareness and Training: data classification")

#### Separation of Duties (SoD)

Conflicting responsibilities create unwanted risks

Regulations such as GDPR insist on paying attention to the roles and duties of your security team.

#### Principle of Least Privileges (PoLP)

Believes in providing employees with tje minimum necessary access they need.

### Physical Security Controls

A set of security measures taken to prevent unauthorized access to physical devices.

Examples:

- locks
- fences
- badge systems
- security guards
- mantrap doors
- biometric systems
- lighting
- motion detectors
- closed-circuit TVs
- alarms

... is the first layer of protection.
It involves the protection of organizational assets from environmental (floods and eartquakes) and man-made (terrorism, wars, explosion, dumpster diving and theft, vandalism) threats.

Types:

- preventive
- detective
- deterrent
- recovery
- compensating

### Technical Security Controls

A set of security measures taken to protect data and systems from unauthorized personnel.

Examples:

- access controls
- authentication
- authorization
- auditing
- security protocols
- network security devices

#### Access control

... is the selective restriction of access.
... protects information assets.
... involves user identification.

Types:

- discretionary (DAC) permits the user to decide
- mandatory (MAC) does not permit the end user to decide
- role-based

#### Identity and Access Management (IAM)

... is a framework to manage user digital identities and access.
The services provided by IAM are classified into four (n.4) distinct components:

1. authentication
2. authorization
3. user management
4. enterprise directory services (Central User Repository)

#### Types of authentication

Authentication involves validating the identity of an individual.

- password
- two-factor
- biometrics
- smart card authentication
- single sign-on (SSO)

#### Types of authorization

Authorization involves controlling individual's access of information.

- centralized or decentralized
- implicit or explicit

#### Accounting

... is a method of keeping track of user actions on the network.
It keeps track of the who, when, and how of user access to the network.

## Network segmentation

... is the practice of splitting a network into smaller network segments and separating groups of systems or applications from each other.

![Network segmentation](img/network_segmentation.png "Network segmentation")

It defeat the drawback of the traditional flat network.

### Network Security Zoning

... allows an organization to manage a secure network environment by selecting the appropriate security levels for **different zones of Internet and Intranet networks**.

It helps in monitoring and controlling **inbound and outbound traffic**.

### Demilitarized Zone (DMZ)

A computer sub-network is placed between the organization's private network such as LAN, and an outside public network such as the Internet, and acts as an additional security layer.

Contains the servers that need to be accessed from an outside network:

- web server
- email server
- DNS server

Hosts in the DMZ can connect to external networks but hosts in the DMZ can not connect to internal networks.

### Network virtualization (NV)

pag. 3359
