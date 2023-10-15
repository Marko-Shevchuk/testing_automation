# Magento user stories and acceptance criteria

## User

### 1.1 

### 1.2 As a user, I want to be able to log into my account so that I can continue using my personal data and experience personalization.

**Description**: When a user is not logged in, all pages should contain a button that links to a login page. The login page should have the "email" and "password" required fields and "sign in" and "Forgot your password?" buttons. The "Forgot Your Password?" page should have "email" required fields and a "Reset my password" button. The "New Password" page should have "password" and "confirm password" required fields with strength indicator as described in user story 1.1 and the "change password" button.

### Scenario 1.2a Logging In
**Given**: The user has a registered account and is on the login page

**When**: The user enters their email and password

**And**: The user clicks the "Sign In" button

**Then**: The user is successfully logged into their account and can access their personalized data.

### Scenario 1.2b Incorrect Email or Password
**Given**: The user is on the login page

**When**:  The user enters an incorrect email or password  

**And**: The user clicks the "Sign In" button  

**Then**: An error message is displayed indicating that the email or password is incorrect. The user is not logged in.

### Scenario 1.2c Reset Password
**Given**: The user has forgotten their password  

**When**: The user clicks the "Forgot Your Password?" button on the login page  

**Then**: The user is redirected to the "Forgot Your Password?" page

**When**: The user enters their email  

**And**: The user clicks the "Reset my password" button  

**Then**: An email with a reset password link is sent to the user's email address

**When**: The user goes to the "New password" page using the reset password link

**And**: The user fills "password" and "confirm password" fields with the same new password

**Then**: The user's password is changed and the user is redirected to the login page
