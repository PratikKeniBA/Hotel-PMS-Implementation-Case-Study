# Business Requirements Document (BRD)

## Hotel PMS Implementation & Client Onboarding Case Study

**Client:** Azure Grand Business Hotel  
**Location:** Pune, Maharashtra, India  
**Property:** 4-Star Business Hotel  
**Room Inventory:** 120 Rooms  
**Project Type:** Simulated PMS Implementation  
**Role:** Implementation Analyst  

---

# 1. Document Purpose

This Business Requirements Document defines the business
requirements for implementing a centralized Property
Management System (PMS) for Azure Grand Business Hotel.

The document focuses on the operational requirements of
Front Office, Reservations, Housekeeping, Food & Beverage,
Finance and Management.

The objective is to establish a common understanding of
business needs before functional design and PMS configuration.

---

# 2. Current Business Environment

The hotel currently uses a combination of:

- Excel spreadsheets
- Manual registers
- Email/phone-based reservation coordination
- Standalone POS
- Manual operational reports

The current environment creates dependency on manual data
entry and communication between departments.

---

# 3. Business Challenges

## 3.1 Reservation Management

Current challenges:

- Manual reservation recording
- Difficulty maintaining real-time availability
- Manual reservation confirmation
- Duplicate guest information
- Difficulty tracking cancellations and no-shows

### Business Need

The hotel requires a centralized reservation process with
real-time visibility of room inventory and reservation status.

---

## 3.2 Front Office Operations

Current challenges:

- Manual room allocation
- Limited visibility of room readiness
- Manual check-in and checkout
- Manual guest billing
- Risk of room-status mismatch

### Business Need

The hotel requires a PMS-supported Front Office workflow
covering room allocation, check-in, guest stay management,
billing and checkout.

---

## 3.3 Housekeeping

Current challenges:

- Room status is updated manually
- Front Office may not have immediate visibility of room
  readiness
- Communication between Housekeeping and Front Office is
  dependent on manual coordination

### Business Need

The PMS should support standardized room-status workflows
and provide relevant room readiness information to Front
Office.

---

## 3.4 Food & Beverage

Current challenges:

- Restaurant transactions are handled through a standalone
  POS
- Guest room charges may require manual posting
- Manual posting creates a risk of errors and delays

### Business Need

The hotel requires a PMS-POS integration approach that can
transfer eligible restaurant charges to the guest folio.

---

## 3.5 Finance & Billing

Current challenges:

- Manual guest billing
- Manual recording of advance payments
- Manual reconciliation
- Limited visibility of outstanding balances

### Business Need

The PMS should maintain a centralized guest folio containing
room charges, service charges, taxes, payments, deposits and
outstanding balances.

---

## 3.6 Management Reporting

Current challenges:

- Reports require manual consolidation
- Different departments may maintain different versions of
  operational data
- Management has limited real time visibility

### Business Need

The PMS should provide standardized operational reports for
management decision making.

---

# 4. Business Requirements

## BR 001: Centralized Reservation Management

The hotel requires a centralized system to create, modify,
cancel and search guest reservations.

### Priority
High

### Business Value
Improves reservation accuracy and provides a single source of
reservation information.

---

## BR 002: Room Availability

The hotel requires visibility of room availability based on
room inventory, reservations, allocations and applicable room
statuses.

### Priority
High

### Business Value
Reduces the risk of incorrect room commitments and improves
front office decision-making.

---

## BR 003: Room Allocation

The hotel requires the ability to assign rooms to arriving
guests based on room type, availability and operational
conditions.

### Priority
High

### Business Value
Improves room allocation efficiency and guest handling.

---

## BR 004: Guest Check-In

The hotel requires a standardized check-in process including:

- Guest identification
- Reservation verification
- Room assignment
- Deposit/advance recording where applicable
- Guest registration

### Priority
High

---

## BR 005: Guest Check-Out

The hotel requires a standardized checkout process including:

- Review of guest folio
- Posting of final charges
- Payment settlement
- Receipt/invoice generation
- Room status update

### Priority
High

---

## BR 006: Guest Folio

The hotel requires a centralized guest folio to maintain
financial transactions associated with a guest stay.

The folio should support:

- Room charges
- F&B charges
- Laundry
- Other services
- Taxes
- Discounts
- Deposits
- Payments
- Outstanding balance

### Priority
High

---

## BR 007 : Housekeeping Room Status

The hotel requires standardized room-status management.

Example workflow:

**Occupied → Vacant/Dirty → Cleaning → Clean → Inspected/Ready**

### Priority
High

### Business Value
Improves coordination between Housekeeping and Front Office.

---

## BR 008: POS Integration

The hotel requires integration between the restaurant POS
and PMS so eligible restaurant charges can be posted to the
correct guest folio.

### Priority
High

### Business Value

- Reduces manual entry
- Reduces posting errors
- Improves billing efficiency
- Supports smoother checkout

---

## BR 009: Guest Profile Management

The hotel requires centralized guest profiles containing
relevant guest information and stay history.

### Priority
Medium

### Business Value
Improves guest recognition, data quality and operational
efficiency.

---

## BR 010: Data Migration

The hotel requires migration of relevant existing data from
Excel and legacy records.

Potential data includes:

- Guest master
- Room master
- Reservations
- Corporate accounts

### Priority
High

---

## BR 011:  Role Based Access

The PMS should provide access based on user responsibilities.

Example:

| Role | Required Access |
|---|---|
| Front Office | Reservations, check in, checkout |
| Housekeeping | Room status |
| Finance | Billing and payments |
| F&B | POS related transactions |
| Management | Reports |
| IT | Technical administration |

### Priority
High

---

## BR 012: Operational Reporting

The hotel requires standardized reporting for:

- Occupancy
- ADR
- RevPAR
- Arrivals
- Departures
- Cancellations
- No-shows
- Room status
- Revenue
- Outstanding balances

### Priority
Medium

---

# 5. Business Rules

## BRULE 001: Room Assignment

A room should only be assigned when it meets the hotel's
configured availability and readiness conditions.

---

## BRULE 002: Room Status

Room status should reflect the operational condition of the
room according to the hotel's configured workflow.

---

## BRULE 003: Guest Folio

Charges and payments associated with a stay should be
recorded against the appropriate guest folio.

---

## BRULE 004:POS Posting

Restaurant charges posted to a guest room should be associated
with the correct room/guest folio.

---

## BRULE 005: User Access

Users should only access functions appropriate to their
assigned role.

---

# 6. Non Functional Business Requirements

## Performance

The PMS should provide timely responses during normal hotel
operations.

## Availability

The system should be available during hotel operating hours
and support business continuity requirements.

## Security

Guest and financial information should be protected through
appropriate authentication and role-based access.

## Usability

The system should be usable by hotel employees with
appropriate role-based training.

## Auditability

Important transactions and changes should be traceable
through appropriate system records.

---

# 7. Assumptions

- Hotel users will participate in requirements workshops.
- Existing hotel data can be extracted from current files.
- Hotel management will provide required approvals.
- Relevant users will participate in UAT.
- POS integration requirements will be provided by the
  relevant stakeholders.
- Training will be provided before go-live.

---

# 8. Constraints

- Existing data may contain quality issues.
- Users may have limited experience with centralized PMS
  systems.
- Hotel operations must continue during implementation.
- Data migration must be carefully planned to minimize
  operational disruption.
- Integration dependencies may affect implementation timelines.

---

# 9. Success Measures

The project will measure success through:

- Completion of critical PMS workflows
- Successful UAT
- Acceptable data migration accuracy
- Successful POS-PMS integration testing
- User training completion
- Reduction in manual operational activities
- Successful go-live
- Controlled post-go-live support

---

# 10. Traceability to Implementation

The business requirements will be carried forward into:

**BRD → FRD → GAP Analysis → Configuration → UAT → Training → Go-Live**

Each high-priority requirement should have corresponding
functional requirements and UAT test coverage.

---

# 11. Portfolio Disclaimer

This BRD is part of a simulated portfolio case study.

It demonstrates the approach an Implementation Analyst could
use when analyzing and preparing a hotel PMS implementation.

It does not represent an actual client implementation or
configuration of a specific PMS vendor product.
