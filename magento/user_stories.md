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

### 1.3 As a user, I want to be able to view my account profile so that I can access my contact information, my default billing address, my default shipping address, my orders, my downloadable products, my wish list, my address book, my stored payment methods, and my reviews.

**Description**:
- Every page on Magento should have a link to the profile page when the user is logged in.
- The profile page should contain links to several subpages in the account navigation menu: "My Account", 
"My Orders", "My Downloadable Products", "My Wish List", "Address Book", "Account Information" "Stored Payment Methods", "My Product Reviews".
- On the "My Account" subpage users can view their contact information and change their password, default billing address, or default shipping address.
- On the "My Orders" subpage users can view the table of orders they have made with these columns: Order id | Date | Ship To | Order Total | Status | Action
- On the "My Downloadable Products" subpage users can view a table of digital products they have bought with these columns: Order id | Date | Title | Download | Status | Remaining downloads
- On the "My Wish List" subpage users can view a list of products they have liked earlier and order them
- On the "Address Book" subpage user can add addresses and choose the default billing address and default shipping address.
- On the "Account Information" subpage user can change their first name, last name, email, and password
- On the "Stored Payment Methods" subpage user can add payment methods or delete them
- On the "My Product Reviews" subpage users can view reviews they have made for products they have bought

### Scenario 1.3a - Access the Profile Page:
**Given**: The user is logged in to their Magento account.  
**When**: The user clicks on the "My Account" link, which is accessible from every page.  
**Then**: The user is directed to the profile page.

### Scenario 1.3b - Access all subpages on the account navigation menu of the Profile Page:
**Given**: The user is on the profile page.  
**When**: The user clicks on each of the following links in the account navigation menu: "My Account", 
"My Orders", "My Downloadable Products", "My Wish List", "Address Book", "Account Information", "Stored Payment Methods", "My Product Reviews"  
**Then**: The user is directed to the corresponding subpage for each link.

### Scenario 1.3c - Change account information:
**Given**: The user is on the "Account Information" subpage.  
**When**: The user updates one or more fields: first name, last name, and email.  
**And**: The entered first name, last name, and email are valid.  
**And**: The user enters the correct password.  
**Then**: The user's account information is updated.

### Scenario 1.3d - Change password:
**Given**: The user is on the "Account Information" subpage.  
**When**: The user clicks the "Change Password" button.  
**Then**: Input fields "Current Password", "New Password", and "Confirm Password" dynamically appear on the page  
**When**: The user enters the correct current password.  
**And**: The user enters a new password with a minimum number of symbols 8 and a minimum of 3 classes of characters: Lower Case, Upper Case, Digits, Special Characters.  
**And**: The user enters the same new password in the "Confirm Password" field  
**Then**: The password is changed, and the user is notified of the successful password change.

### Scenario 1.3e - Redownload downloadable product:
**Given**: The user is on the "My Downloadable Products" subpage.  
**When**: The user clicks on the "Download" for a downloadable product.  
**Given**: The remaining download count is greater than zero.  
**Then**: Downloading begins and the remaining download count is updated.  

### Scenario 1.3f - Order product from Wish list:
**Given**: The user is on the "My Wish List" subpage.  
**When**: The user selects a product from their wish list and clicks on an "Add to cart" button.  
**Then**: The product is added to their cart, and the user is redirected to the product page to specify product option(s).

### Scenario 1.3g - Add address to address book:
**Given**: The user is on the "Address Book" subpage.  
**When**: The user clicks on the "Add New Address" button and enters the required address details().  
**Then**: The address is added to their address book.

### Scenario 1.3h - Add payment method:
**Given**: The user is on the "Stored Payment Methods" subpage.  
**When**: The user clicks on the "Add Payment Method" button and provides the necessary payment information(card number, expiration date, CVV).  
**And**: Provided payment information is valid.  
**Then**: The payment method is added to their account for future use.

### Scenario 1.3i - Delete payment method:
**Given**: The user is on the "Stored Payment Methods" subpage  
**And**: The user has one or more stored payment methods.  
**When**: The user selects a payment method and clicks on a "Delete" option.  
**Then**: The selected payment method is removed from their account.

### Scenario 1.3j - Downloadable product download limit has been exceeded:
**Given**: The user is on the "My Downloadable Products" subpage.  
**When**: The user clicks on the "Download" for a downloadable product.  
**Given**: The remaining download count is equal to zero.  
**Then**: A message with the text "download limit has been exceeded" pops up

### Scenario 1.3k - Invalid input:
**When**: The user types an invalid name, phone number, card number, email, etc. on any field on the profile page.  
**Then**: Each corresponding field is marked with the message "invalid input"



## Admin


### 2.1 

