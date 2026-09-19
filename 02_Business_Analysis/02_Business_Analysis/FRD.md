# Functional Requirements Document (FRD)

## Hotel PMS Implementation & Client Onboarding Case Study

**Client:** Azure Grand Business Hotel  
**Location:** Pune, Maharashtra, India  
**Property:** 4-Star Business Hotel  
**Room Inventory:** 120 Rooms  
**Document Type:** Functional Requirements Document  
**Project Type:** Simulated PMS Implementation

---

# 1. Document Purpose

This Functional Requirements Document translates the approved
business requirements into functional system requirements for
the proposed Property Management System (PMS).

The document describes how the PMS should support hotel
operations across Reservations, Front Office, Housekeeping,
F&B, Finance and Management.

---

# 2. Functional Scope

The functional scope includes:

- Reservation Management
- Room Inventory and Availability
- Front Office
- Guest Profile Management
- Housekeeping
- Guest Folio and Billing
- POS-PMS Integration
- Data Migration
- User Access
- Reporting

---

# 3. Reservation Management

## FR 001 Create Reservation

The PMS shall allow authorized users to create a reservation.

The reservation should capture, where applicable:

- Guest name
- Contact information
- Arrival date
- Departure date
- Number of guests
- Room type
- Rate plan
- Rate
- Special requests
- Payment/deposit information
- Reservation source
- Reservation status

### Validation

The system should validate required fields before saving the
reservation.

---

## FR 002 Room Availability Check

The PMS shall display applicable room availability based on:

- Room inventory
- Stay dates
- Existing reservations
- Room allocation
- Room status
- Blocked rooms
- Out-of-order rooms
- Configured availability rules

The availability calculation should be consistent with the
hotel's configured inventory model.

---

## FR 003  Reservation Modification

Authorized users shall be able to modify permitted
reservation information.

Examples:

- Stay dates
- Room type
- Number of guests
- Rate
- Special requests

The system should recalculate applicable availability when
dates or room type are changed.

---

## FR 004 Reservation Cancellation

Authorized users shall be able to cancel reservations.

The system should:

- Update reservation status
- Release applicable inventory
- Record cancellation information
- Apply configured cancellation rules where applicable

---

## FR 005 Reservation Confirmation

The PMS should generate or trigger a reservation confirmation
after a reservation is successfully created, according to
configured notification settings.

---

# 4. Front Office

## FR 006 Guest Check-In

The PMS shall support guest check-in.

The workflow should include:

1. Locate reservation
2. Verify guest information
3. Verify room availability/readiness
4. Assign or confirm room
5. Record required registration information
6. Record deposit/advance where applicable
7. Complete check-in

---

## FR 007 Room Assignment

Authorized Front Office users shall be able to assign a room
based on:

- Reservation room type
- Room availability
- Room readiness
- Guest requirements
- Hotel operational rules

The system should prevent inappropriate assignment according
to configured business rules.

---

## FR 008  Room Change

The PMS should allow authorized users to move a guest from one
room to another.

The system should maintain the guest stay information and
record the room change.

---

## FR 009 Early Check-In

The PMS should support the hotel's configured early
check-in rules.

Possible validation conditions may include:

- Room readiness
- Availability
- Guest reservation
- Payment/deposit requirements

The exact rule should be confirmed during implementation
workshops.

---

## FR 010  Guest Check-Out

The PMS shall support checkout by:

1. Reviewing the guest folio
2. Posting final charges
3. Applying payments
4. Calculating outstanding balance
5. Settling the folio
6. Generating applicable receipt/invoice
7. Updating the room status

---

# 5. Guest Profile Management

## FR 011 Guest Profile

The PMS shall maintain a centralized guest profile.

Potential fields include:

- Guest name
- Contact details
- Identification information
- Guest preferences
- Stay history
- Corporate relationship where applicable

The system should support appropriate duplicate prevention or
duplicate identification processes.

---

# 6. Housekeeping

## FR 012 Room Status

The PMS shall support configured room statuses.

Example workflow:

**Occupied**
→ **Vacant/Dirty**
→ **Cleaning**
→ **Clean**
→ **Inspected/Ready**

The actual status model will be confirmed during PMS
configuration workshops.

---

## FR 013 Housekeeping Update

Authorized housekeeping users shall be able to update room
status.

The updated status should be available to relevant Front
Office users according to system configuration.

---

## FR 014  Room Discrepancy

The implementation should define a process for handling
differences between physical room condition and PMS status.

Example:

PMS: Ready

Actual: Dirty

The issue should be recorded, investigated and corrected
before the room is assigned where hotel policy requires it.

---

# 7. Guest Folio and Billing

## FR 015  Guest Folio

The PMS shall maintain a folio for each applicable guest stay.

The folio may contain:

- Room charges
- F&B charges
- Laundry
- Other services
- Taxes
- Discounts
- Deposits
- Payments
- Adjustments
- Outstanding balance

---

## FR 016  Advance / Deposit

The PMS shall allow authorized users to record advance or
deposit payments against the appropriate guest account or
reservation.

The amount should be reflected during final settlement.

---

## FR 017 Folio Settlement

At checkout, the system should calculate:

**Total Charges - Payments/Deposits = Outstanding Balance**

The system should support the configured payment and
settlement methods.

---

# 8. POS-PMS Integration

## FR 018 Restaurant Charge Posting

The proposed integration should allow eligible restaurant
transactions to be posted to the correct guest folio.

Example:

**POS**
→ Transaction
→ Integration/API
→ PMS
→ Room 205 Folio

---

## FR 019 Integration Validation

The implementation team should test:

- Correct room number
- Correct guest association
- Correct transaction amount
- Correct transaction date/time
- Successful posting
- Failed transaction handling
- Duplicate transaction prevention/reconciliation

---

# 9. Data Migration

## FR 020  Guest Data Migration

Existing guest records should be prepared for migration.

The implementation process should include:

1. Data extraction
2. Data profiling
3. Field mapping
4. Data cleansing
5. Duplicate identification
6. Format standardization
7. Validation
8. Test migration
9. Reconciliation
10. Final migration

Data migration planning is critical because future reservations,
guest profiles, room/rate structures and other operational data
must remain accurate during transition. :contentReference[oaicite:1]{index=1}

---

## FR 021  Room Master Migration

Room information should be mapped to the PMS, including:

- Room number
- Room type
- Floor
- Room status
- Operational attributes

Room types and inventory should be configured before
reservation migration so that reservations have valid
destination inventory. :contentReference[oaicite:2]{index=2}

---

# 10. User Access

## FR 022 Role Based Access

The PMS should provide role-based access.

Example:

| Role | Functional Access |
|---|---|
| Front Office | Reservations, room allocation, check-in/out |
| Housekeeping | Room status |
| F&B | POS transactions |
| Finance | Billing and payments |
| Management | Reports |
| IT/Admin | System administration |

Access should follow the principle of providing users with
the functions required for their responsibilities.

---

# 11. Reporting

## FR 023 Operational Reports

The PMS should provide or support reports covering:

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

Reports should be validated during UAT against agreed
business calculations and source data.

---

# 12. Audit and Traceability

## FR 024 Transaction Traceability

Where supported by the PMS, important transactions and
changes should retain appropriate user/date/time information
for operational investigation and audit purposes.

---

# 13. Error Handling

## FR 025 User Validation

The system should provide meaningful validation messages when
required information is missing or invalid.

Example:

> "Room number is required."

---

## FR-026 — Integration Failure

If a POS transaction fails to reach the PMS, the implementation
team should have a defined process to:

1. Identify the failed transaction
2. Check the integration status/log
3. Prevent duplicate posting
4. Retry or reprocess where supported
5. Reconcile the transaction
6. Escalate if unresolved

---

# 14. UAT Functional Coverage

The following functional areas require UAT coverage:

- Reservation creation
- Reservation modification
- Cancellation
- Room availability
- Room allocation
- Check-in
- Room change
- Guest folio
- Advance payment
- POS posting
- Housekeeping status
- Checkout
- Payment settlement
- Reports
- User access

---

# 15. Requirement Traceability

Each functional requirement should be traceable to:

**Business Requirement**
→ **Functional Requirement**
→ **Configuration**
→ **UAT Test Case**
→ **Defect (if applicable)**
→ **UAT Sign-Off**

This ensures that requirements are not lost between
business discovery and implementation.

---

# 16. Configuration Dependencies

The following areas require confirmation during configuration
workshops:

- Room types
- Room inventory
- Rate plans
- Tax rules
- Payment methods
- Room-status workflow
- User roles
- Folio rules
- POS integration
- Notification/confirmation settings
- Reporting requirements

---

# 17. Portfolio Disclaimer

This FRD is part of a simulated portfolio case study.

It demonstrates functional analysis and implementation
planning for a hotel PMS.

It does not represent configuration of a live PMS product or
a claim of implementation experience with a specific vendor.
