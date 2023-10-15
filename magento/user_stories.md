# Magento user stories and acceptance criteria

## User

### 1.1 


### 1.6 As a user, I want to be able to add items to my wishlist so that I can save them for later (to buy in the future).

<details>
<summary><h3>Description</h3></summary>
<ol>
    <li>Product pages/search(facet/filter) page should contain a button that saves product to wishlist.</li>
    <li>To use the Wish List feature, users need to have an account on the website. The functionality should be tied to the user's account, ensuring that their selected items are saved and accessible across different devices. </li>
    <li>The Wish List interface should display detailed information about each item, including images, names, prices, quantity and variations selected by the user.</li>
     <li>Users should have an opportunity to share their Wish List with somebody, so implement sharing by email addresses</li>
     <li>Implement a seamless transition from the Wish List to the shopping cart, allowing users to move items from their Wish List directly into their cart for checkout.</li>
     <li>Ensure that the Wish List feature is fully responsive on various devices, including smartphones and tablets, providing a consistent and user-friendly experience.</li>
</ol>
</details>

### Scenario 1.6a Redirect guest user
**Given**: Guest user
**When**: The user is on product pages/search 
**And**: The user clicks on  _"Add to wish list"_ button
**Then**: The user flow directed to login page so as to logging in into the system with that existed account or register a new one.
### Scenario 1.6b Add item by authorizated user
**Given**: Authorizated user is on product/search page
**When**: The user clicks on  product pages/search 
**And**: The user clicks on  _"Add to wish list"_ button
**Then**: The user flow directed to wish list page with provided message _"**[Product]** has been added to your Wish List. Click [here]**(previous page URL)** to continue shopping"_ at the top of the page
### Scenario 1.6c View **Wish list** page
**Given**: Authorizated user is on any page
**When**: The user clicks on dropdown next to the message _Welcome, **[UserName]**!_  at the <ins>desktop version</ins> or Hamburger Menu -> Account at the <ins>mobile version</ins>
**And**: The user clicks on  _"My Wish List(**[Number of saved items]**)"_ button
**Then**: Redirect to Wishlist page
### Scenario 1.6d Delete item from **Wish list** page
**Given**: Authorizated user is on **Wish list** page
  **When**: The user hover on item at the <ins>desktop version</ins> or see a trash icon at the <ins>mobile version</ins>
**And**: The user clicks on  _Remove Item_ button depicted as trash can icon
    **Then**: Page reloading with the  "_**[Item]** Tee has been removed from your Wish List._" message at the top of the page
### Scenario 1.6e Seamless transition to shipping cart
**Given**: Authorizated user is on **Wish list** page that is fullfiled at least with one item
**When**: The user clicks on  _Add All to Cart_ button
**Then**: Message at the top in case number of product was availabe: _**[Quontity number**] product(s) have been added to shopping cart: "**[Product Name]**"_. Unavailable: _The requested qty is not available for "**[Product Name]**"._
