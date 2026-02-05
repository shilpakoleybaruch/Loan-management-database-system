# Loan-management-database-system
Requirements Gathering Document of Database Management System
_____________________________________________________________________________
Project: Loan Origination & Servicing DBMS
Prepared for: Local Bank
Prepared by: Team 2 and Project 7
Date: September 23, 2025

1) Purpose & Scope
Design and implement a relational DBMS to support a local bank’s loan lifecycle for both
individuals and organizations
In Scope
1. A relational database
2. Unstructured data upload and storage
3. Writing and editing functionality
4. Roles and access limitations
Not in scope
1. Front end application
2. Cybersecurity

2) Stakeholders & Roles
- Applicant (Individual or organization): register/login, submit application, attach documents,
specify collateral, view status, make payments.
- Bank Officer: review application & documents, validate/approve collateral, value/approve
loan, record collateral decision, record loan request decision.
- System Admin: user/role management, configurations, changes to database tables (i.e., for
new collateral types), audit access.

3) Key Business Rules
1. Loans must have collateral
2. Customers submit collateral
3. Collateral must cover ≥ 80% of the requested loan amount.
a. Only one type of collateral is allowed for one loan
4. Collateral must be approved by a member of the bank

5. Property and Vehicle collaterals must have insurance.
6. Maintain annual income history for Individual and Organizations
7. Loans are requested by customers
8. Loans are reviewed and approved/declined by bank staff
a. Approved loan → visible to Individual with payments enabled.
b. Declined loan → visible with reason for denial.
9. Approved loans will appear to the customer who can make payments towards the loan

4) High-Level Processes (Functional Requirements)
1. Registration & Login: profile & KYC on file.
Attributes for registration (Individual):
Customer full Name (Individuals/Organizations)
Customer ID (Individuals/Organizations)
DOB (Individual)
Nationality
Customer Phone number (Nome, Office or personal)
Emergency contact number
Customer email address
Employment status (Employed, Self-employed, Unemployed, Retired)
Occupation/Job title
Employer name
Monthly or Annual income
Attributes for Organization:
Organization Name
Organization ID
Organization Contact details (Email and Office)
Organization country
Annual Revenue
Organization address
2. Loan Application: request amount, purpose, terms, upload docs, and save inprogress
loan request
Loan Amount Requested
Loan Purpose
Loan Period
Interest Rate Type (Fixed or variable)
(Applicant’s information is already put in the registration attributes –Fetch from the
registration table.)

(Financial information and Employment details are also mentioned in the registration
process.)
Government issued ID type or number
Proof address
Proof of income
Document Upload
Document type
File Name
File format
Document Status: Approved/reject
Applicants IDs

3. Collateral Submission: one or many items; insurance proof (when required)
Collateral Details:

Collateral Type (Vehicle, House, and Account)
Collateral value
Proof of ownership
4. Loan Review: Approved/Rejected
5. Loan Booking (if approved): amortization schedule generated
6. Repayments: Manual payments
Loan ID
Payment Amount
Payment Date
Balance
7. Denial Visibility: Customers and certain bank staff see request & denial reasons.

5) Core Entities
1. Individual/organization
2. Address
3. Income History
4. User Account
5. Loan Application
6. Collateral
7. Document
8. Loan
9. Payment
10. Reference Tables

6) Non-Functional Requirements
Security (encryption), Performance (Number of queries), Availability (99.9%), Scalability
(Number of Individual/organization).

7) Role-Based Access
Individual/organization: own data only
Bank Officer: approve/decline collateral, approve/decline loan
Admin: all access

8) Sample Acceptance Criteria
1. Collateral coverage < 80% → Approval blocked
2. Vehicle without insurance → Approval blocked
3. Declined → Reason visible to Individual
4. Approved → Loan created + visible
5. Decisions logged in audit

Impact Analysis of the Loan DBMS Project

1) Community (Individual & Local Businesses)
Benefits
• Easier Access to Loans: Individuals and organizations can apply online, track progress,
and avoid repeated branch visits.
• Transparency: Individual can view approval/denial reasons, improving trust in the
bank’s decision-making.
• Financial Inclusion: Even small businesses or lower-income families can apply with
documented income and collateral, supporting local entrepreneurship and home
improvement.
• Faster Loan Disbursement: Automated processes and digital documentation reduce
waiting times, helping Individual get funds when they need them most.
• Security of Data: Personal and financial information is securely stored and managed,
reducing risks of paper-based records being lost or misused.
Challenges
• Learning Curve: Some community members (elderly, less tech-savvy) may struggle with
online systems.
• Data Privacy Concerns: Individual may worry about storing sensitive documents
digitally.
• Dependence on Internet Access: Applicants in rural areas with poor connectivity may
face difficulties.
2) Organization (Bank)
Benefits
• Efficiency & Productivity: Automated workflows (loan application, collateral
verification, payment tracking) reduce manual paperwork and staff overhead.
• Regulatory Compliance: Built-in checks (collateral coverage, insurance validation, audit
logs) minimize risk of fraud and regulatory violations.
• Better Risk Management: Access to structured income histories and collateral data
improves underwriting decisions, reducing defaults.
• Individual Satisfaction & Retention: Transparent and faster services improve the bank’s
reputation and competitive edge.

• Scalability: Supports growth in Individual base without requiring proportional increases
in staff.
• Data Insights: Analytics on loan trends, repayment patterns, and portfolio risks help in
strategic planning.
Challenges
• Initial Investment: Resource cost, training, and infrastructure setup.
• Maintenance & Security: Ongoing costs for IT support, database maintenance, and
cybersecurity safeguards.
• Integration with Legacy Systems: Existing systems may require costly upgrades or
connectors.
3) Technical Risks
• System Downtime: Outages could block Individual from applying for or repaying loans
on time.
• Data Loss / Corruption: Hardware failure, bugs, or improper backups could risk sensitive
loan data.
• Integration Issues: Difficulty connecting the new DBMS with existing systems (e.g.,
accounting, payment gateways).
• Cybersecurity Threats: Potential for hacking, phishing, or ransomware attacks on
sensitive financial and personal data.

4) Organizational Risks
• High Initial Costs: Budget overruns in development (Database).
• Staff Resistance: Employees accustomed to manual workflows may resist adopting the
new system.
• Training Gaps: Inadequate training could lead to errors in collateral approvals, loan
decisioning, or repayment recording.
• Regulatory Non-Compliance: Failure to configure rules correctly (e.g., 80% collateral
requirement, insurance checks) could expose the bank to fines or lawsuits.

5) Community/ Individual Risks
• Privacy Concerns: Individual may hesitate to upload personal documents online due to
fear of misuse.
• Exclusion by Automation: Rigid rule enforcement (like collateral coverage) might
exclude applicants who could have been approved under more flexible, manual
judgment.

• Individual Frustration: If the system is not user-friendly or has frequent technical
glitches, trust in the bank may decline.

6) Strategic Risks
• Competitive Pressure: Other banks may implement more advanced digital lending
platforms faster.
• Lock-in vendor: If the bank relies on external software vendors, switching costs or
dependency risks could arise.
• Scalability Risks: If the system is not built to scale, growth in loan volume could slow
down performance and Individual service.

7) Overall cost estimation
The estimated cost of developing a database system for a Bank’s loan management
project. The rational cost estimation depends on the software development, testing and
deployment, maintenance of a secure database system, and server costs.
Breakdown of cost:
• Requirement analysis and design (2-3 weeks)

§ Business analysis and database architectures to define schemas and
workflow and compliances needed.
§ Cost: $8,000 – $12,000 (One analyst and one architect at $100/hour
which is approximately 120 hours)
• Database Development: (Approximately 1 month)

§ Relational database (SQL) for customer data, loan details, collateral
information, and transactional history. Includes schema for individuals or
organizations, Loan type, collateral type, and payment tracking.
§ Security: Encryption for sensitive data.
§ Cost: Approximately $13,600 (One database developer, 85/hour which is
approximately 160 hours (about 13 days) total)

• Document management system (2 weeks)

§ Integration of secure file storage system for documents like collateral
proofs and incurrence records.
§ Cost: $4,000 - $8,000 (development and cloud storage setup)

• Quality analyst/ Testing (Approximately 1 month)

§ Functional testing (loan request, approval/denial workflows), security
testing (penetration testing), and performance testing.
§ Cost: Approximately $9,600 (One QA tester, 60/hour which is
approximately 160 hours)
• Compliance and Security (2-3 weeks)

§ Compliance with financial regulations and data protection laws.
§ Cost: Approximately $10,000 (If bank takes a third-party security service)

• Training and Documentation (1 week)

§ Training for bank staff and user guides for customers.
§ Cost: $5,000

• Cloud services setup (2 weeks): $1000 per month

Total Rational Cost:
• Requirement Analysis and Design: $8,000 – $12,000
§ Midpoint: ($8,000 + $12,000) / 2 = $10,000

• Database Development: $13,600
• Document Management System: $4,000 – $8,000
§ Midpoint: ($4,000 + $8,000) / 2 = $6,000

• Quality Analyst/Testing: $9,600
• Compliance and Security: $10,000
• Training and Documentation: $5,000
• Cloud services setup: $1000 per month
Total Rational Cost Calculation: $10,000 (Requirement Analysis) + $13,600 (Database
Development) + $6,000 (Document Management) + $9,600 (QA/Testing) + $10,000
(Compliance) + $5,000 (Training) + (Cloud services cost) $1000 = $55,200
Final Answer: The total rational cost is approximately $55,200.
The total estimated timeline would be approximately 6 months.
8) Mitigation Strategies (briefly)
• System reliability: Regular backups, disaster recovery planning, load testing.
• Security: Strong encryption, multi-factor authentication, intrusion detection, and audits.
• Staff enablement: Structured training and phased rollouts to reduce resistance.
• Customer support: Provide assisted digital services (branch kiosks, call center help) for those
less tech-savvy.
