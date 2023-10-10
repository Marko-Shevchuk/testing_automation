# Magento user stories and acceptance criteria

## User

### 1.1 As a user, I want to be able to create an account so that I can have a personalized shopping experience.
**Description**: All pages should contain a button that links to a registration page where users can create an account using their first name, last name, email address and password. The "password" field should have a password strength indicator and must only allow passwords that are at least 8 characters long, and contain at least: one uppercase letter, one lowercase letter, one number and one special character. The registration form should contain a "confirm password" field.  
### Scenario 1.1a Successful register
**Given**: No account has been previously registered using the specified email  
**When**: The user enters their first name, last name, email address and password into the registration form
**And**: The user clicks on a "Create account" button
**Then**: The account is created and the user is logged into the system with that account.
### Scenario 1.1b Email taken
**Given**: An account has already been registered using the specified email  
**When**: The user enters their first name, last name, email address and password into the registration form
**And**: The user clicks on a "Create account" button
**Then**: An error message regarding the existing account is displayed.
### Scenario 1.1c Invalid input
**Given**: No account has been previously registered using the specified email  
**When**: The user specifies either:
* a blank first name, 
* a blank last name, 
* a non-RFC 5322-compliant email address, 
* a password that does NOT contain one uppercase letter, one lowercase letter, one number, one special character and three different types of letters,
* a "confirm password" that does not match the "password"  
  
**Then**: Dynamic error messages regarding each discrepancy are displayed next to the appropriate input field.



## Admin

### 2.1 