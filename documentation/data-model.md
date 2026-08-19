# DriveCare360 Data Model

## Overview

The DriveCare360 data model is designed to manage customers,
vehicles, service requests, technicians, spare parts, and
customer feedback.

## Core Salesforce Objects

### Account
Represents the customer.

### Vehicle
Stores customer vehicle information including:
- VIN
- Make
- Model
- Year
- Fuel Type
- Mileage
- Insurance
- Vehicle Status

### Service Request
Tracks vehicle service activity including:
- Service Date
- Service Type
- Status
- Priority
- Assigned Technician
- Issue Description
- Estimated Cost
- Actual Cost
- Completion Date

### Technician
Stores technician information including:
- Name
- Email
- Phone
- Specialization
- Experience
- Certification Level
- Hourly Rate
- Availability

### Spare Part
Manages automotive spare parts and inventory.

### Service Part Used
Tracks spare parts consumed during a Service Request.

### Customer Feedback
Captures customer ratings and feedback after service completion.

## Relationships

Account
↓ Lookup
Vehicle
↓ Lookup
Service Request
↓ Master-Detail
Service Part Used
↓ Master-Detail
Spare Part

Service Request
↓ Master-Detail
Customer Feedback

Service Request
↓ Lookup
Technician

## Relationship Design

The Account object represents the customer base.

Each Account can have multiple Vehicles.

Each Vehicle can have multiple Service Requests.

Each Service Request can contain multiple Service Part Used records.

Each Service Part Used record is linked to a Spare Part.

Customer Feedback is linked to the Service Request.

Technicians are assigned to Service Requests through a lookup relationship.

## Salesforce Features Used

- Custom Objects
- Custom Fields
- Lookup Relationships
- Master-Detail Relationships
- Roll-Up Summary Fields
- Formula Fields
- Schema Builder
- Auto-Number Fields
