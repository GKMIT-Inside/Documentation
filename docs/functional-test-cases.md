## **TC_0: Authentication Module**

| Test Case No. | Module Name   | Test Case Description                                                                                  | Acceptance Criteria                                                                                                                                 |
| ------------- | ------------- | ------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| **T_C_0.1**   | Login         | Verify a valid combination of Employee Username and Password allows successful login.                  | The system must grant access to the Employee dashboard/landing page, and the correct user name/profile must be displayed.                           |
| **T_C_0.2**   | Login         | Verify a valid combination of Admin Username and Password allows successful login.                     | The system must grant access to the Admin dashboard/landing page, and the correct user name/profile must be displayed.                              |
| **T_C_0.3**   | Login         | Verify login fails with a valid username and an invalid password (for any role).                       | An appropriate error message must be displayed (e.g., "Invalid credentials" or "Invalid password"), and the user must remain on the login page.     |
| **T_C_0.4**   | Login         | Verify login fails with an invalid username and a valid password (for any role).                       | An appropriate error message must be displayed (e.g., "Invalid credentials" or "Invalid username"), and the user must remain on the login page.     |
| **T_C_0.5**   | Login         | Verify login fails with both invalid username and invalid password.                                    | An appropriate error message must be displayed, and the user must remain on the login page.                                                         |
| **T_C_0.6**   | Login         | Verify case sensitivity for the Username field.                                                        | Login must fail if the username case does not match the stored value (e.g., `john.doe` should fail if the correct username is `John.Doe`).          |
| **T_C_0.7**   | Login         | Verify the system handles repeated failed login attempts (Brute-Force Protection).                     | After N consecutive failed attempts (e.g., 5), the account must be temporarily locked or a CAPTCHA/other protective measure must be required.       |
| **T_C_0.8**   | Session       | Verify a logged-in user is automatically logged out after a period of inactivity (Session Timeout).    | The user must be redirected to the login page, and attempting to access an internal page must redirect them back to the login page.                 |
| **T_C_0.9**   | Logout        | Verify that clicking the Logout button successfully terminates the user session.                       | The user must be redirected to the login page, and attempting to use the browser's "Back" button should not display any protected internal content. |
| **T_C_0.10**  | Authorization | Verify an Employee user cannot access a URL/page specific to the Admin role via direct URL navigation. | The system must display an "Access Denied" error message, or redirect the user to their own dashboard.                                              |

---

**Module:** Authentication & Authorization  
**Scope:** Covers Login, Logout, Session Management, and Role-based Access Control.
