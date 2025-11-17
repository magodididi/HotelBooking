# Testing Documentation for Hotel Booking Project

This directory contains all testing-related documentation for Lab Work #6: Testing the Hotel Booking Project.

## Documents Overview

### 📋 TEST_PLAN.md
The test plan includes:
- Objectives and scope of testing
- Test strategy and approaches
- Test items and quality attributes
- Risk assessment and mitigation
- Test tools and methodologies

### 📊 TEST_RESULTS.md
Contains detailed results of executed test cases:
- Pass / Fail metrics
- Test execution per component
- Defect tracking and analysis
- Notes on performance, reliability, and security

### 📝 TESTING_SUMMARY.md
Provides a high-level overview:
- Key findings from functional and non-functional testing
- Identified defects
- Recommendations and conclusions

## Quick Start Guide

### Running Tests

**Start Backend Services**


cd backend
./mvnw spring-boot:run

## Quick Start

### Start Frontend

cd frontend
npm install
npm run dev


## Access Applications

- **Backend API**: http://localhost:8080
- **Frontend**: http://localhost:3000
- **Health Check**: http://localhost:8080/actuator/health

## Test Environment Setup

- **Java**: 17+
- **Node.js**: 18+
- **PostgreSQL**: 15+
- **Docker & Docker Compose**
- **JUnit 5** for unit testing
- **Postman / REST Assured** for API testing

## Test Categories

### Functional Testing
✅ User Management (Registration, Login, Authentication)  
✅ Booking Management (CRUD for bookings)  
✅ Hotel & Room Management (CRUD for hotels and rooms)  
✅ Favorites Management  
✅ Availability Check  

### Integration Testing
✅ API Integration (Controllers ↔ Services ↔ Database)  
✅ Database Integrity  
✅ Cache / Repository Integration  

### Non-Functional Testing
✅ Performance Testing (API response < 1s)  
✅ Reliability & Fault Tolerance  
✅ Security Testing (Authentication & Authorization)  
✅ Usability Testing (User-friendly UI and messages)

# Test Case Example

| ID | Name | Scenario / Instructions | Expected Result | Actual Result | Pass/Fail |
|----|------|------------------------|-----------------|---------------|-----------|
| TC001 | Register New User | 1. Open registration form 2. Enter valid data 3. Submit | User successfully registered | User successfully registered | Pass |
| TC002 | Book Available Room | 1. Select room 2. Check availability 3. Book | Booking created, status confirmed | Booking created | Pass |
| TC003 | Book Occupied Room | Attempt to book already reserved room | Error "Room already booked" | Error displayed | Pass |
| TC004 | Add Hotel to Favorites | 1. Select hotel 2. Add to favorites | Hotel added to favorites list | Hotel added | Pass |
| TC005 | Invalid Registration (Empty) | 1. Open registration 2. Leave email empty 3. Submit | Error "Field is required" | Error displayed | Pass |

More detailed test cases can be found in TEST_RESULTS.md.

## Known Issues / Risks

- Race conditions when multiple users book the same room
- Data loss during database connection failures
- Form validation errors (e.g., booking date in the past)
- Data integrity violations when deleting linked entities

## Test Metrics

| Metric | Value |
|--------|-------|
| Total Test Cases | 30+ |
| Passed | 28+ |
| Failed | 2 |
| Critical Issues | 0 |
| High Priority Issues | 1 |
| Medium Priority Issues | 1 |

## Next Steps

### Fix Identified Issues
- Resolve validation edge cases
- Address booking concurrency issues

### Complete Remaining Tests
- End-to-end UI testing
- Full performance and security testing

### Update Documentation
- Add new test results
- Document testing methodology and environment

## Contact

For questions or issues regarding testing, contact the development team or your lab instructor.
