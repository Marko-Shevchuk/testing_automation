# Magento user stories and acceptance criteria

## User

### 1.1 As a user, I want to be able to create an account and be logged in so that I can have a personalized shopping experience.
**Description**: The website should have a registration system where users can create an account using their first name, last name, email address and password. The registration form should contain a "confirm password" field. The "password" field should have a password strength indicator and must only allow passwords that are at least 8 characters long, and contain at least: one uppercase letter, one lowercase letter, one number, one special character, three different types of letters. The account should allow users to save their personal information, preferences, and shopping history.
### Scenario 1.1a
**Given**: There is no account already registered with this email
**When**: The user enters their information into the registration form
**And**: The user clicks on a "Create account" button
**Then**: The account is created and the user is logged into the system with that account.
### Scenario 1.1b
**Given**: There IS an account already registered with this email
**When**: The user enters their information into the registration form
**And**: The user clicks on a "Create account" button
**Then**: An error message regarding the existing account is displayed.
### Scenario 1.1c
**Given**: There is no account already registered with this email
**When**: The user enters their information into the registration form, but specifies either: 
a blank first name, 
a blank last name, 
a non-RFC 5322-compliant email address, 
a password that does NOT contain one uppercase letter, one lowercase letter, one number, one special character and three different types of letters
a "confirm password" that does not match the "password"
**Then**: Dynamic error messages regarding each discrepancy are displayed next to the appropriate input field.



## Admin

### 2.1 