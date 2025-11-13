# Test Plan for GKMIT INSIDE Platform

## 1. Introduction

This Test Plan outlines the strategy, scope, objectives, resources, and schedule for testing the GKMIT_INSIDE platform. GKMIT_INSIDE is an internal knowledge-sharing platform for the GKMIT Organisation, built to facilitate structured knowledge preservation and community collaboration between Developers and Administrators.

## 2. Objective

The primary objective of this testing effort is to verify and validate that the GKMIT_INSIDE platform meets all functional, non-functional (security, performance, usability), and design requirements as specified in the project documentation and DFDs. The goal is to ensure a stable, secure, and user-friendly application before deployment.

## 3. In Scope

The following modules and functionalities will be rigorously tested:

- **Landing Page**: Public page display, navigation, and initial security checks (HTTPS, URL canonicalization).
- **Authentication & Authorization**: Login, Logout, Session Management, and Role-Based Access Control (Developer/Admin).
- **User Registration**: New user sign-up, email validation, and initial status (isApproved: false).
- **Post Management (admin)**: Post creation, submission, editing, and deletion (limited to own posts).
- **Feed & Content Delivery**: Viewing the main /feed, content filtering, and search functionality.
- **Interaction Features**: Bookmarking posts, adding Reactions, and adding Comments.
- **User Management (Admin)**: Approval/Rejection of pending user registrations (/admin/users/pending).
- **Content Review (Admin)**: Approval/Rejection of submitted posts (/admin/posts/pending).

## 4. Out of Scope

The following areas are excluded from this testing plan:

- **Load/Stress Testing**: Detailed performance testing beyond basic response time checks.
- **Disaster Recovery & Failover Testing**.
- **UX**: Formal testing with end-users.
- **Installation/Configuration Testing**: Testing the deployment environment setup itself.

## 5. Test Items (Modules)

The test effort will be organized around the following DFD components and major pages:

| Module                         | Corresponding DFD Process             | Key Endpoints                                  | Roles Tested |
| ------------------------------ | ------------------------------------- | ---------------------------------------------- | ------------ |
| Authentication & Authorization | User Registration, Validation         | /login, /logout                                | All          |
| Landing Page                   | N/A (Client-side UI)                  | /                                              | All          |
| Post Management                | Post Submission, Modification         | /posts/create, /posts/me                       | Employee     |
| User Management                | Data Retrieval, Status Update         | /admin/users/pending                           | Admin        |
| Content Review                 | Admin Review & Decision               | /admin/posts/pending                           | Admin        |
| Feed & Search                  | Fetch, Filter & Search Posts          | /feed                                          | All          |
| Interaction Features           | Request Validation, Logging & Routing | API Endpoints (Reactions, Comments, Bookmarks) | All          |

## 6. Testing Approach

### Framework

- **Technology Stack**: JavaScript with Jest or Vitest would be the preferred framework for E2E unit and integrated test cases.
- **UI Tests**: Focus on login/logout flows, navigation, form submissions (/posts/create), and page displays.
- **API Tests**: Critical for testing backend logic, especially authorization checks with status codes and ensuring data integrity upon interactions.

## 7. Data Driven Testing (Test Data)

Testing will utilize data-driven methods for efficiency and coverage.

**Positive Data:**

- Valid Admin credentials, Valid Employee credentials.
- Unique emails and valid structured data for registration.
- Valid content (Title, Description, Tags) for post submission.

**Negative Data:**

- **Invalid Credentials**: Blank fields, SQL injection strings, XSS scripts, invalid email formats.
- **Authorization Fails**: Employee tokens attempting Admin endpoints; Admin tokens attempting to delete another user's post.
- **Boundary Conditions**: Max/Min length for Name, Title, and Description fields.
- **Existing Data**: Attempting to register with an existing email.

## 8. Test Cases

The test cases developed so far form the foundation of the execution phase. They will be organized by module:

- **TC 1**: Landing Page (Display, Navigation, and Security).
- **TC 2A**: User Registration (Success, Validation, and Initial Status).
- **TC 2B**: Authentication & Authorization (Login, Logout, Session, Auth Checks).

**New Test Cases:**

- **TC 4**: Post Management (Creation, Edit, Delete, Status Checks).
- **TC 5**: Admin Management (User Approval, Post Approval/Rejection).
- **TC 6**: Content Delivery & Interaction (Feed, Search, Comments, Reactions, Bookmarks).

## 9. Exit Criteria

Testing will be considered complete and ready for release when all of the following criteria is met:

- **Pass Rate**: Minimum 95 - 100% overall Pass Rate for all executed test cases.

## 10. Risk and Management

| Risk                          | Impact                                                                | Mitigation Strategy                                                                                                                        |
| ----------------------------- | --------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| Delay in Admin Approval Logic | Admin cannot approve users/posts; system bottleneck.                  | Prioritize testing and fixing the User Management (DFD 7.0) and Admin Review (DFD 5.0) processes.                                          |
| Security/Auth Bypass          | Unauthorized role gains access to restricted data/actions.            | Focus on API-level testing (Postman) to strictly verify 403 Forbidden responses for unauthorized requests.                                 |
| Data Integrity Issues         | Interactions (Comments/Reactions) are written incorrectly to MongoDB. | Create specific API tests to verify that data written to COMMENTS, REACTIONS, and BOOKMARKS tables correctly references userId and postId. |

## 11. Deliverables

Upon completion of the testing phase, the following documents and artifacts will be delivered:

- **Test Summary Report (TSR)**: Final sign-off document detailing execution status.
- **Complete Test Case Repository**: All executed test cases, including the expanded TCs (TC 1, TC 2) and more.
- **Defect Report**: A final list of all defects raised, their current status, and severity.
