# Magento user stories and acceptance criteria

## User

### 1.1 

### 1.3 As a user, I want to be able to view my account profile so that I can access my contact information, my default billing address, my default shipping address, my orders, my downloadable products, my wish list, my address book, my stored payment methods, and my reviews.

**Description**:
- Every page on Magento should have a link to the profile page when the user is logged in.
- The profile page should contain links to several subpages in the side menu: "My Account", 
"My Orders", "My Downloadable Products", "My Wish List", "Address Book", "Account Information" "Stored Payment Methods", "My Product Reviews".
- On the "My Account" subpage user can view their contact information and change their password, default billing address, or default shipping address.
- On the "My Orders" subpage users can view the table of orders they have made with these columns: Order id | Date | Ship To | Order Total | Status | Action
- On the "My Downloadable Products" subpage users can view a table of digital products they have bought with these columns: Order id | Date | Title | Download | Status | Remaining downloads
- On the "My Wish List" subpage users can view a list of products they have liked earlier and order them
- On the "Adress Book" subpage user can add addresses and choose the default billing address and default shipping address.
- On the "Account Information" subpage user can change their first name, last name, email, and password
- On the "Stored Payment Methods" subpage user can add payment methods or delete them
- On the "My Product Reviews" subpage users can view reviews they have made for products they have bought

### Scenario 1.3a - Access the Profile Page:
**Given**: The user is logged in to their Magento account.

**When**: The user clicks on the "My Account" link, which is accessible from every page.

**Then**: The user is directed to the profile page.

### Scenario 1.3b - Access all subpages on the side menu of the Profile Page:
**Given**: The user is on the profile page.

**When**: The user clicks on each of the following links in the side menu: "My Account", 
"My Orders", "My Downloadable Products", "My Wish List", "Address Book", "Account Information" "Stored Payment Methods", "My Product Reviews"

**Then**: The user is directed to the corresponding subpage for each link.

### Scenario 1.3c - Change account information:
**Given**: The user is on the "Account Information" subpage.

**When**: The user updates one or more fields: first name, last name, and email.

**And**: The user enters the correct password.

**Then**: The user's account information is updated.

### Scenario 1.3d - Change password:
**Given**: The user is on the "Account Information" subpage.

**When**: The user clicks the "Change Password" button.

**Then**: Input fields "Current Password", "New Password", and "Confirm Password" dynamically appears on the page

**When**: The user enters the correct current password.

**And**: The user enters a new password with a minimum number of symbols 8 and a minimum of 3 classes of characters: Lower Case, Upper Case, Digits, Special Characters.

**And**: The user enters the same new password in the "Confirm Password" field

**Then**: The password is changed, and the user is notified of the successful password change.

### Scenario 1.3e - Redownload downloadable product:
**Given**: The user is on the "My Downloadable Products" subpage.

**When**: The user clicks on the "Download" for a downloadable product.

**Given**: The remaining downloads count is greater than zero.

**Then**: Downloading begins and the remaining downloads count is updated.

### Scenario 1.3f - Order product from Wish list:
**Given**: The user is on the "My Wish List" subpage.

**When**: The user selects a product from their wish list and clicks on an "Add to cart" button.

**Then**: The product is added to their cart, and the user is redirected to the product page to specify product option(s).

### Scenario 1.3g - Add address to address book:
**Given**: The user is on the "Address Book" subpage.

**When**: The user clicks on the "Add New Address" button and enters the required address details.

**Then**: The address is added to their address book.

### Scenario 1.3h - Add payment method:
**Given**: The user is on the "Stored Payment Methods" subpage.

**When**: The user clicks on the "Add Payment Method" button and provides the necessary payment information.

**Then**: The payment method is added to their account for future use.

### Scenario 1.3i - Delete payment method:
**Given**: The user is on the "Stored Payment Methods" subpage

**And**: The user has one or more stored payment methods.

**When**: The user selects a payment method and clicks on a "Delete" option.

**Then**: The selected payment method is removed from their account.
