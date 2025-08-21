#### *** FREE TO USE ***
Still Working on this document
Inspiration and reference coming soon.

# Non-Functional Requirements Document

## 1. Objective

The following Non-Functional Requirements (NFRs) define the expected quality attributes of the system. These requirements are binding, yet the Bidders have the opportunity to propose the most suitable means of compliance. Bidders are encouraged to propose innovative solutions, provided that they meet or exceed the outcomes described herein.

## 2. Requirements

### 2.1. Product Requirements

Intrinsic quality attributes of the system, ensuring its reliability, performance, security, usability, maintainability, and architectural integrity.

#### NFR-PROD-001: System Resilience and Performance

The system shall exhibit exceptional resilience and performance, ensuring continuous operation, rapid response times, and efficient resource utilization under varying load conditions. Bidders are encouraged to outline their approach to resilience (e.g., redundancy, monitoring, scaling strategies) and to explain how performance will be sustained over time.

**Aspects:** Reliability, Availability, Performance, Scalability, Caching.

*   **Reliability:** The system shall achieve a Mean Time Between Failures (MTBF) of no less than 1,500 hours, calculated quarterly, excluding pre-notified scheduled maintenance windows (maximum 4 hours/month, 1-week advance notice).
*   **Availability:** The system shall maintain an operational availability of 99.9% during defined operational hours (06:00 to 22:00, Monday to Friday), measured by continuous 24/7 monitoring of key endpoints.
*   **Performance under Normal Load:** The system shall support 10,000 concurrent users with an average response time of less than 1.5 seconds for 95% of critical transactions (e.g., user login, data retrieval, transaction submission) and less than 3 seconds for all other transactions.
*   **Performance under Peak Load:** Under peak load conditions (defined as 15,000 concurrent users), the system shall maintain an average response time of less than 3 seconds for 95% of critical transactions and less than 5 seconds for all other transactions.
*   **Scalability:** The system shall demonstrate linear scalability, whereby a doubling of hardware resources yields at least a 60% increase in transaction throughput.
*   **Caching:** An effective caching strategy (client-side, application-level, database query) shall be implemented to optimize performance and reduce database load, achieving a cache hit ratio of no less than 90% for frequently accessed data, with robust and configurable invalidation policies to ensure data freshness.

#### NFR-PROD-002: Comprehensive System Security

The system shall implement a robust, multi-layered security architecture that safeguards data integrity, confidentiality, and availability, and protects against unauthorized access, use, disclosure, disruption, modification, or destruction. Bidders should describe their layered security model, including approaches to encryption, access management, vulnerability handling, and secure coding practices. Alignment with recognized industry standards (e.g., ISO, OWASP) is encouraged but specific technologies are at the vendor’s discretion.

**Aspects:** Data Protection, Access Control, Logging and Auditability, Vulnerability Management, Secure Coding.

*   **Data Protection:** All data in transit shall be secured using TLS 1.3. All sensitive data at rest shall be encrypted using AES-256 or a stronger encryption standard.
*   **Access Control:** The system shall implement robust access control mechanisms, supporting both Role-Based Access Control (RBAC) or Attribute-Based Access Control (ABAC). RBAC shall define granular permissions based on predefined roles and the principle of least privilege. ABAC shall enable dynamic, context-aware access decisions based on attributes of the user, resource, and environment. A comprehensive access control matrix detailing roles, attributes, and corresponding permissions shall be maintained and auditable.
*   **Logging and Auditability:** All user actions and critical system events shall be comprehensively logged, with logs stored securely and immutably for a minimum of 12 months to facilitate forensic analysis and compliance.
*   **Vulnerability Management:** The system shall undergo annual penetration testing and vulnerability assessments by a party selected by the Procuring Authority. All critical and high-severity vulnerabilities identified shall be remediated within 7 and 14 calendar days, respectively.
*   **Secure Coding:** The codebase shall be developed using secure coding practices, adhering to industry-standard guidelines (e.g., OWASP Secure Coding Practices, CERT Secure Coding Standards). All input shall be validated, output encoded, and sensitive data handled securely. The code shall be free from known security vulnerabilities as identified by Static Application Security Testing (SAST) and Dynamic Application Security Testing (DAST) tools. All critical and high-severity findings from these tools must be remediated prior to deployment.

#### NFR-PROD-003: Usability and User Experience

The system shall provide an intuitive, efficient, and accessible user experience, minimizing user effort and maximizing productivity. Vendors are encouraged to describe their user-centered design approach, usability testing methods, and accessibility compliance measures.

**Aspects:** Transaction Success Rate, Usability Heuristics, System Usability Scale.

*   **Transaction Success Rate:** The system shall achieve a first-attempt transaction success rate of no less than 98% for critical user workflows (e.g., user registration, data entry, report generation), as measured during User Acceptance Testing (UAT).
*   **Usability Heuristics:** The User Interface (UI) shall rigorously adhere to established usability heuristics (e.g., Nielsen's 10 Usability Heuristics).
*   **System Usability Scale (SUS):** The system shall achieve an average System Usability Scale (SUS) score of 75 or higher from a representative user group.

#### NFR-PROD-004: Maintainability and Code Quality

The system shall be highly maintainable, facilitating efficient defect resolution, future enhancements, and long-term sustainability. This necessitates adherence to stringent code quality standards. Bidders should set out their coding standards, documentation practices, and approaches to testing and code review.

**Aspects:** Defect Resolution, System Recovery, Code Complexity, Code Coverage, Coding Standards/Conventions, Documentation, Code Reviews, Static Analysis.

*   **Defect Resolution:** High-priority defects (Severity 1 and Severity 2, as classified by the procuring authority) shall be resolved within 2 business hours and 8 business hours, respectively. The Mean Time To Repair (MTTR) for Severity 1 defects shall not exceed 2 hours, and for Severity 2 defects, it shall not exceed 8 hours.
*   **System Recovery:** The Mean Time To Recover (MTTR) from a complete system failure shall not exceed 4 hours.
*   **Code Complexity:** The codebase shall maintain a cyclomatic complexity score of less than 10 for no less than 90% of its modules.
*   **Code Coverage:** Unit test code coverage shall be no less than 85%.
*   **Coding Standards:** The codebase shall rigorously adhere to established coding standards and conventions (e.g., PEP 8 for Python, Google Java Style Guide).
*   **Documentation:** Comprehensive inline comments and documentation shall be provided for complex logic.
*   **Naming Conventions:** A clear and consistent naming convention shall be applied for variables, functions, and classes.
*   **Code Reviews:** No less than 90% of all code changes shall undergo peer review.
*   **Static Analysis:** Static code analysis tools (e.g., SonarQube, ESLint) shall be integrated into the development workflow, with all critical and major code smells and bugs remediated prior to merging to main branches.

#### NFR-PROD-005: System Architecture and Portability

The system shall be designed with a modern, modular, and portable architecture, facilitating flexible deployment, future evolution, and vendor independence. Bidders should describe their architectural approach (e.g., modular services, containerization, use of APIs), how it supports portability, and how it enables adaptability to evolving requirements.

**Aspects:** Architecture Style, Service Mesh, Deployment Flexibility, Cloud Migration, Database Architecture.

*   **Architecture Style:** The system shall adopt a microservices architecture, characterized by independent, loosely coupled services with well-defined APIs. This architecture shall support containerization (e.g., Docker) and orchestration (e.g., Kubernetes).
*   **Service Mesh:** A service mesh (e.g., Istio, Linkerd) shall be implemented to manage inter-service communication, providing capabilities such as traffic management, observability, and security.
*   **Deployment Flexibility:** The system shall be deployable on Linux, and a container orchestration platform (e.g., Kubernetes) without requiring any code changes or recompilation. The deployment process shall be fully automated and documented, achieving a deployment success rate of 100% across all specified environments.
*   **Cloud Migration:** The system shall support migration to different cloud providers (e.g., from AWS to Azure) with minimal effort, demonstrated by a documented migration plan and successful execution in a test environment.
*   **Database Architecture:** The database architecture shall be robust, scalable, and performant, supporting high transaction volumes and efficient data retrieval. It shall be designed for horizontal scalability and ensure data consistency (e.g., ACID properties for transactional databases, eventual consistency for NoSQL where appropriate). The database shall support a minimum of 5,000 transactions per second (TPS) with an average latency of less than 50ms under normal load, and scale linearly with increased resources.

#### NFR-PROD-006: Interoperability

The system shall seamlessly and securely integrate with designated external systems, facilitating efficient data exchange and process automation. Bidders should describe their approach to API design, standards supported, and strategies for handling errors and failures.

**Aspects:** External System Integration, Communication Patterns, Integration Test Pass Rate, DataHub, NDI.

*   **External System Integration:** The system shall integrate with the national identification system (NIS) and the national payment gateway (NPG) using OAuth 2.0 for authentication, and RESTful APIs conforming to OpenAPI 3.0 specifications, utilizing JSON payloads over HTTP/2.
*   **Communication Patterns:** All integration points shall support asynchronous communication patterns (e.g., webhooks, message queues) to ensure resilience and scalability.
*   **Integration Test Pass Rate:** A 100% pass rate shall be achieved for all integration test cases, including performance under load, error handling, and security vulnerability testing.

### 2.2. Organisational Requirements

Organisational Requirements define the processes, procedures, and operational aspects related to the system's development, deployment, and maintenance, ensuring efficient project execution, quality assurance, and effective support.

#### NFR-ORG-01: Project Management and Quality Assurance

The supplier shall implement robust project management and quality assurance processes throughout the system's development and deployment lifecycle. Bidders should set out their methodology, quality management system, and documentation standards. They should also describe training, support, and knowledge transfer mechanisms.

**Aspects:** Project Management Methodology, Quality Management System, Documentation, Maintainability Planning, Modularity and Reusability, Traceability, Change Management, Training and Support, DevSecOps.

*   **Project Management Methodology:** A formal project management methodology (e.g., Agile Scrum, SAFe, Waterfall) shall be adopted and documented, ensuring clear roles, responsibilities, and communication channels. Regular progress reports shall be provided.
*   **Quality Management System:** A certified Quality Management System (e.g., ISO 9001) shall be in place, covering all aspects of software development, testing, and deployment.
*   **Documentation:** Comprehensive and up-to-date documentation shall be provided, including but not limited to: system design documents, API documentation, user manuals, administrator guides, and training materials. All documentation shall be clear, concise, and accurate, and updated with every system release.
*   **Maintainability Planning:** A detailed maintainability plan shall be provided, outlining strategies for long-term system support, including code refactoring, technical debt management, and knowledge transfer.
*   **Modularity and Reusability:** The system shall be designed with high modularity and reusability, promoting the use of standardized components and interfaces to facilitate future development and reduce redundancy.
*   **Traceability:** A robust traceability matrix shall be maintained, linking all requirements to design elements, code modules, test cases, and defects, ensuring comprehensive coverage and impact analysis.
*   **Change Management:** A formal change management process shall be implemented to control and track all changes to requirements, design, code, and documentation, ensuring proper authorization, impact assessment, and communication.
*   **Training and Support:** Comprehensive training programs shall be provided for end-users and administrators, covering system functionality, operation, and troubleshooting. Ongoing technical support shall be provided with defined Service Level Agreements (SLAs) for response and resolution times.
*   **DevSecOps:** A comprehensive DevSecOps approach shall be implemented throughout the entire software development lifecycle, integrating security practices into every phase from design and development to testing, deployment, and operations. This includes automated security testing (SAST, DAST, SCA) integrated into the CI/CD pipeline, infrastructure as code (IaC) with security best practices embedded, continuous monitoring of security posture in production environments, regular security training for all development and operations personnel, and a clear process for managing and responding to security incidents.

#### NFR-ORG-02: Warranty, Support & Maintenance

**Warranty**

The supplier shall provide a comprehensive warranty for the system, covering all software and hardware components (if applicable), for a period of at least [months] months from the date of final acceptance. The warranty shall cover defects in materials, workmanship, and functionality, ensuring the system performs according to the agreed-upon specifications and nonfunctional requirements. Any defects identified during the warranty period shall be rectified by the supplier at no additional cost to the procuring authority within agreed-upon service level agreement (SLA) timelines.

**Support and Maintenance**

The Bidders shall provide ongoing technical support and maintenance services for the system for a period of at least five years after the warranty period, with options for extension. This includes:

1.  **Helpdesk Support:** Multi-channel helpdesk support (phone, email, web portal) with guaranteed response and resolution times based on issue severity (as defined in NFR-ORG-).
2.  **Bug Fixing and Patch Management:** Proactive identification and resolution of software bugs, and timely application of security patches and updates to all system components.
3.  **Preventive Maintenance:** Regular maintenance activities to ensure optimal system performance, stability, and security, including system health checks, performance tuning, and data integrity checks.
4.  **Corrective Maintenance:** Rapid response and resolution to system failures or incidents, aiming to restore full functionality within agreed-upon RTOs and RPOs.
5.  **Evolutionary Maintenance:** Provision for minor enhancements and adaptations to the system to address evolving business needs or technological changes, as agreed upon with the procuring authority.
6.  **Version Upgrades:** Provision for major version upgrades of the system, including planning, testing, and deployment, to ensure the system remains current and supported.

#### NFR-ORG-03: Time Schedule and Deliverables

**Project Timeline**

The supplier shall propose a detailed project timeline, including key milestones, phases, and dependencies, from project initiation to final system acceptance. The timeline shall be realistic, achievable, and align with the overall project objectives.

**Deliverables**

The supplier shall provide a comprehensive list of deliverables for each project phase, including documentation, code, test reports, and training materials. All deliverables shall be of high quality and submitted according to the agreed-upon schedule.

### 2.3. External Requirements

External Requirements define the system's interactions with external entities, including regulatory compliance, third-party dependencies, and service level agreements.

#### NFR-EXT-01: Regulatory Compliance

The system shall comply with all applicable laws, regulations, and industry standards relevant to its operation and the data it processes. Bidders should identify relevant regulations and describe their approach to ensuring compliance.

**Aspects:** Data Privacy, Industry Standards, Accessibility Standards.

*   **Data Privacy:** The system shall comply with the General Data Protection Regulation (GDPR) and other relevant data privacy laws (e.g., CCPA), ensuring data minimization, purpose limitation, and data subject rights.
*   **Industry Standards:** The system shall adhere to relevant industry standards (e.g., PCI DSS for payment processing, HIPAA for healthcare data) as applicable.
*   **Accessibility Standards:** The system shall comply with Web Content Accessibility Guidelines (WCAG) 2.1 Level AA, ensuring accessibility for users with disabilities.

#### NFR-EXT-02: Legal and Contractual Requirements

The system shall comply with all legal and contractual obligations, including licensing agreements, intellectual property rights, and contractual terms with third-party vendors. Bidders should describe their approach to managing legal and contractual risks.

**Aspects:** Licensing, Intellectual Property, Contractual Obligations.

*   **Licensing:** All third-party software components used in the system shall be properly licensed, with clear documentation of license types (e.g., MIT, Apache, GPL) and compliance with their terms.
*   **Intellectual Property:** The procuring authority shall retain full intellectual property rights over all custom-developed software and configurations. The supplier shall indemnify the procuring authority against any claims of intellectual property infringement.
*   **Contractual Obligations:** The system shall meet all contractual obligations outlined in the master service agreement and any associated statements of work.

#### NFR-EXT-03: Environmental Requirements

The system shall operate efficiently within specified environmental conditions and adhere to relevant environmental regulations. Bidders should describe their approach to energy efficiency and environmental sustainability.

**Aspects:** Energy Efficiency, Environmental Regulations.

*   **Energy Efficiency:** The system shall be designed for optimal energy efficiency, minimizing power consumption and heat dissipation. Energy consumption metrics shall be monitored and reported.
*   **Environmental Regulations:** The system's operation and disposal shall comply with all applicable environmental regulations (e.g., RoHS, WEEE).

#### NFR-EXT-04: Third-Party Dependencies

The supplier shall identify and manage all third-party dependencies, including software libraries, APIs, and external services, ensuring their reliability, security, and compatibility. Bidders should describe their approach to third-party risk management.

**Aspects:** Third-Party Software, External APIs, Cloud Services.

*   **Third-Party Software:** All third-party software components shall be regularly updated to their latest stable and secure versions. A software bill of materials (SBOM) shall be provided and maintained.
*   **External APIs:** Reliance on external APIs shall be minimized where possible. For necessary external APIs, robust error handling, retry mechanisms, and fallback strategies shall be implemented.
*   **Cloud Services:** If cloud services are utilized, they shall adhere to industry best practices for security, reliability, and data privacy. Cloud service provider certifications (e.g., ISO 27001, SOC 2) shall be provided.

#### NFR-EXT-05: Service Level Agreements (SLAs)

Detailed Service Level Agreements (SLAs) will be agreed upon, specifying key performance indicators (KPIs) such as uptime, response times, resolution times, and availability of support personnel/channels. These SLAs will be legally binding and include provisions for penalties in case of non-compliance.

#### NFR-EXT-06: Future Compatibility

The system shall be designed to be compatible with future versions of operating systems, browsers, and other relevant technologies, ensuring long-term usability and reducing the need for costly re-development. Bidders should describe their strategy for future compatibility.

**Aspects:** Operating System Compatibility, Browser Compatibility, Technology Stack Evolution.

*   **Operating System Compatibility:** The system shall be compatible with the latest stable versions of major operating systems (e.g., Windows, macOS, Linux distributions) for at least five years from the date of deployment.
*   **Browser Compatibility:** The web-based components of the system shall be compatible with the latest two major versions of leading web browsers (e.g., Chrome, Firefox, Edge, Safari).
*   **Technology Stack Evolution:** The chosen technology stack shall have a clear roadmap for future evolution and be actively supported by its community or vendor.

## 3. Glossary

*   **ABAC:** Attribute-Based Access Control
*   **ACID:** Atomicity, Consistency, Isolation, Durability
*   **AES-256:** Advanced Encryption Standard with a 256-bit key
*   **Agile Scrum:** An iterative and incremental agile software development framework
*   **API:** Application Programming Interface
*   **AWS:** Amazon Web Services
*   **CCPA:** California Consumer Privacy Act
*   **CERT:** Computer Emergency Response Team
*   **CI/CD:** Continuous Integration/Continuous Delivery
*   **DAST:** Dynamic Application Security Testing
*   **DevSecOps:** Development, Security, and Operations
*   **Docker:** A platform for developing, shipping, and running applications in containers
*   **ELK Stack:** Elasticsearch, Logstash, Kibana (a suite of tools for log management and analysis)
*   **ESLint:** A static code analysis tool for identifying problematic patterns found in JavaScript code
*   **GDPR:** General Data Protection Regulation
*   **GPL:** GNU General Public License
*   **HIPAA:** Health Insurance Portability and Accountability Act
*   **HTTP/2:** Hypertext Transfer Protocol version 2
*   **IaC:** Infrastructure as Code
*   **ISO:** International Organization for Standardization
*   **Istio:** An open-source service mesh that layers transparently on existing distributed applications
*   **JSON:** JavaScript Object Notation
*   **JUnit:** A unit testing framework for the Java programming language
*   **KPI:** Key Performance Indicator
*   **Kubernetes:** An open-source container orchestration system
*   **Linkerd:** A service mesh for Kubernetes
*   **Linux:** A family of open-source Unix-like operating systems
*   **macOS:** A series of graphical operating systems developed by Apple
*   **MIT License:** A permissive free software license
*   **MTBF:** Mean Time Between Failures
*   **MTTR:** Mean Time To Repair / Mean Time To Recover
*   **NDI:** National Digital Identity
*   **NFR:** Non-Functional Requirement
*   **NIS:** National Identification System
*   **NPG:** National Payment Gateway
*   **OAuth 2.0:** An authorization framework that enables applications to obtain limited access to user accounts on an HTTP service
*   **OpenAPI 3.0:** A standard, language-agnostic interface description for REST APIs
*   **OWASP:** Open Web Application Security Project
*   **PCI DSS:** Payment Card Industry Data Security Standard
*   **PEP 8:** Python Enhancement Proposal 8 (Python style guide)
*   **Prometheus:** An open-source monitoring system
*   **RBAC:** Role-Based Access Control
*   **RHEL:** Red Hat Enterprise Linux
*   **RoHS:** Restriction of Hazardous Substances Directive
*   **RPO:** Recovery Point Objective
*   **RTO:** Recovery Time Objective
*   **SAFe:** Scaled Agile Framework
*   **SAST:** Static Application Security Testing
*   **SBOM:** Software Bill of Materials
*   **SIEM:** Security Information and Event Management
*   **SLA:** Service Level Agreement
*   **SLO:** Service Level Objective
*   **SonarQube:** An open-source platform for continuous inspection of code quality
*   **SOC 2:** Service Organization Control 2 (a type of audit report)
*   **SQL:** Structured Query Language
*   **SUS:** System Usability Scale
*   **TLS 1.3:** Transport Layer Security version 1.3
*   **TPS:** Transactions Per Second
*   **UAT:** User Acceptance Testing
*   **UI:** User Interface
*   **WEEE:** Waste Electrical and Electronic Equipment Directive
*   **WCAG:** Web Content Accessibility Guidelines
*   **Windows:** A series of graphical operating systems developed by Microsoft


