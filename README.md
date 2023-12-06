
# Documentation

# Library Management System

This is a MERN stack application built for easy and effctive Library management.

## Description


### Security

The application uses JsonWebTokens (JWT) for authentication to enhance security. Data validation and schema description libraries JOI and YUP are utilized to prevent any unauthorized data processing by the server.


### Features

The application caters to two types of users: Librarians and Patrons (General public). Both groups have access to different features tailored to their specific needs. The following is a list of features and their explanations for each type of user:

```
Librarian:
a. Issue - The ability to issue books to users.
b. Return - The ability to un-issue books from users.
c. Requested Books - The ability to view books requested by users.
d. Cancel Request - The ability to cancel any requested book.
e. Issued Books - Access to a list of all issued books.
f. Un-Issued Books - Access to a list of all un-issued books.
g. Add Book - The ability to add books to the inventory.
h. Add E-Book - The ability to add e-book for a particular book
i. Delete Book - The ability to delete books from the inventory.
j. All Users - Access to a list of all users enrolled in the library.
k. Delete User - The ability to delete a user from the library.
m. Inventory - Access to a list of all books in the library with the ability to search and filter based on various parameters.
n. Activity Logs - The ability to view the library's transaction logs.
p. Block Users - The ability to block or unblock users.
q. Update Stock - The ability to update the quantity of books in the inventory.
r. Update Subscription plan - The ability to update subscription plan for users.

Patrons (General User):
a. Request - The ability to request a book.
b. Issued Books - Access to a list of all books issued by them.
c. Inventory - Access to a list of all books in the Library.
d. Unsubscribe - The ability to unsubscribe from the library news.
e. Forgot PassWord - The ability to reset their password in case of forgetting it.
f. Rating Books - The ability to rate books they have issued.
g. Contact - The ability to contact the admin at any time.
h. Related Books - The ability to view all books related to a specific genre.
i. Review - The ability to rate and comment on books they have issued.
j. View E-Book - Users can view PDF of their issued books in realtime

```

### General

This frontend of this website is hosted on Netlify and backend is hosted on Adaptable.

## Getting Started

### Dependencies

### Frontend

- redux-toolkit
- react-router-dom
- Material UI
- react-toastify
- react-pdf
- formik
- yup
- axios

### Backend

- JsonWebTokens(JWT)
- Joi
- bcryptjs
- mongoose
- express-async-handler
- nodemailer
- node-cron
- cors
- axios
- multer
- multer-gridfs-storage

### Dev Dependencies

- nodemon

### Installing

For backend clone the repository by running the following command

```
git clone https://github.com/roshanshetty28/lmsbackend.git

```

For Frontend clone the repository by running the following command

```
git clone https://github.com/roshanshetty28/lmsfrontend.git

```

Then run the below command at the root of both backend and frontend to install all the dependencies

```
npm install

```

### Executing program

to run the Backend excute the following command in the root folder of backend

```
npm run srever

```

Make the following changes before running the frontend in your local machine

```
API_URL = http://localhost:{PORT_NUMBER}/

```

In authService.js, adminService.js and userService.js

to run the Frontend excute the following command in the root folder of frontend

`npm run start`

## API Endpoints documentation

## **User API**

This API documentation outlines the endpoints and functionalities provided by the User API for managing books and user-related actions.

### **Authentication**

All endpoints except **`/forgotlink`** and **`/forgotpass`** require authentication. Authentication is performed using a JSON Web Token (JWT) passed in the Authorization header.

### **1. Get User's Issued Books**

- **Endpoint**: **`GET /`**
- **Authentication**: Yes
- **Description**: Retrieves the list of books issued to the authenticated user.

### **2. Get All Books from the Inventory**

- **Endpoint**: **`GET /all`**
- **Authentication**: Yes
- **Description**: Retrieves all books available in the inventory.

### **3. Get All Books Requested by Users**

- **Endpoint**: **`GET /requested`**
- **Authentication**: Yes
- **Description**: Retrieves the list of books requested by users.

### **4. Request a Book**

- **Endpoint**: **`PATCH /request/:id`**
- **Authentication**: Yes
- **Description**: Requests a particular book identified by its ID.

### **5. Cancel Request for a Book**

- **Endpoint**: **`PATCH /cancel/:id`**
- **Authentication**: Yes
- **Description**: Cancels a previous request for a particular book identified by its ID.

### **6. Get Details of a Book**

- **Endpoint**: **`GET /book/:id`**
- **Authentication**: Yes
- **Description**: Retrieves details of a particular book identified by its ID.

### **7. Get Related Books**

- **Endpoint**: **`GET /related`**
- **Authentication**: Yes
- **Description**: Retrieves all books related to a particular genre.

### **8. Unsubscribe from News-Letter**

- **Endpoint**: **`PATCH /unsubscribe/:id`**
- **Authentication**: Yes
- **Description**: Unsubscribes the user from the newsletter.

### **9. Get Link for Resetting Password**

- **Endpoint**: **`POST /forgotlink`**
- **Authentication**: No
- **Description**: Generates and sends a link to the user's email for resetting the password.

### **10. Reset Password**

- **Endpoint**: **`POST /forgotpass`**
- **Authentication**: No
- **Description**: Resets the user's password using the provided link.

### **11. Add Book to Wishlist**

- **Endpoint**: **`PATCH /addwish/:id`**
- **Authentication**: Yes
- **Description**: Adds a particular book identified by its ID to the user's wishlist.

### **12. Get User's Wishlist**

- **Endpoint**: **`GET /wishlist`**
- **Authentication**: Yes
- **Description**: Retrieves all books from the user's wishlist.

### **13. Remove Book from Wishlist**

- **Endpoint**: **`PATCH /remove/:id`**
- **Authentication**: Yes
- **Description**: Removes a particular book identified by its ID from the user's wishlist.

### **14. Send Contact Mail to Admin**

- **Endpoint**: **`POST /contact`**
- **Authentication**: Yes
- **Description**: Sends a contact email to the admin.

### **15. Subscribe to News-Letter**

- **Endpoint**: **`POST /subscribe`**
- **Authentication**: Yes
- **Description**: Subscribes the user to the newsletter.

### **16. Write Review on a Book**

- **Endpoint**: **`POST /add-review`**
- **Authentication**: Yes
- **Description**: Allows the user to write a review for a particular book.

### **17. Delete a Comment from a Book**

- **Endpoint**: **`DELETE /delete-comment/:id`**
- **Authentication**: Yes
- **Description**: Deletes a comment from a particular book identified by its ID.

### **18. Get Comments of a Book**

- **Endpoint**: **`GET /comments/:id`**
- **Authentication**: Yes
- **Description**: Retrieves all comments for a particular book identified by its ID.

### **19. Modify User's Comment on a Book**

- **Endpoint**: **`PATCH /update-comment/:id`**
- **Authentication**: Yes
- **Description**: Modifies a user's comment on a particular book identified by its ID.

### **20. Get E-Book**

- **Endpoint**: **`GET /ebook/:id`**
- **Authentication**: Yes
- **Description**: Retrieves the E-Book for a particular book identified by its ID.

## **Authentication API**

This API documentation outlines the authentication-related endpoints and functionalities provided by the Authentication API for user login, registration, and details editing.

### **1. User Login**

- **Endpoint**: **`POST /login`**
- **Authentication**: No
- **Description**: Allows users to log in by providing valid credentials.
- **Request Body**:
    - **`email`** (string): User's email.
    - **`password`** (string): User's password.
- **Response**:
    - **`token`** (string): JWT token for authentication.
    - **`user`** (object): User details.

### **2. User Registration**

- **Endpoint**: **`POST /register`**
- **Authentication**: No
- **Description**: Registers a new user.
- **Request Body**:
    - **`name`** (string): User's name.
    - **`email`** (string): User's email.
    - **`password`** (string): User's password.
- **Response**:
    - **`token`** (string): JWT token for authentication.
    - **`user`** (object): Newly registered user details.

### **3. Edit User Details**

- **Endpoint**: **`POST /edit-details`**
- **Authentication**: Yes
- **Description**: Allows authenticated users to edit their details.
- **Request Body**:
    - **`name`** (string): New user's name (optional).
    - **`email`** (string): New user's email (optional).
    - **`password`** (string): New user's password (optional).
- **Request Headers**:
    - **`Authorization`** (string): Bearer token for authentication.
- **Response**:
    - **`user`** (object): Updated user details.
    

## **Admin API**

This API documentation outlines the endpoints and functionalities provided by the Admin API for managing books, users, and other administrative actions.

### **Authentication**

All endpoints require authentication using a JSON Web Token (JWT) passed in the Authorization header.

### **1. Fetch All Books from the Inventory**

- **Endpoint**: **`GET /`**
- **Authentication**: Yes
- **Description**: Retrieves all books available in the inventory.

### **2. Add a Book to the Inventory**

- **Endpoint**: **`POST /`**
- **Authentication**: Yes
- **Description**: Adds a new book to the inventory.
- **Request Body**:
    - **`title`** (string): Book title.
    - **`author`** (string): Book author.
    - **`genre`** (array): Book genres.
    - **`rating`** (number): Book rating.
    - **`stock`** (number): Number of available copies.

### **3. Upload E-Book for a Book**

- **Endpoint**: **`POST /ebook`**
- **Authentication**: Yes
- **Description**: Uploads an E-Book for a particular book.
- **Request Body**: Form data with a file field named **`file`**.

### **4. Issue a Book from Inventory to a User**

- **Endpoint**: **`PATCH /issue/:id`**
- **Authentication**: Yes
- **Description**: Issues a book from the inventory to a user identified by their ID.

### **5. Withdraw Issue of a Book from a User**

- **Endpoint**: **`PATCH /return/:id`**
- **Authentication**: Yes
- **Description**: Withdraws the issue of a book from a user identified by their ID.

### **6. Delete a Book from the Inventory**

- **Endpoint**: **`DELETE /:id`**
- **Authentication**: Yes
- **Description**: Deletes a book from the inventory identified by its ID.

### **7. Delete Account of a User**

- **Endpoint**: **`DELETE /user/:id`**
- **Authentication**: Yes
- **Description**: Deletes the account of a user identified by their ID.

### **8. Get All Requested Books**

- **Endpoint**: **`GET /requested`**
- **Authentication**: Yes
- **Description**: Retrieves all books requested by users.

### **9. Cancel a Request for a Book**

- **Endpoint**: **`PATCH /cancel/:id`**
- **Authentication**: Yes
- **Description**: Cancels a request for a particular book identified by its ID.

### **10. Get All Issued Books**

- **Endpoint**: **`GET /issued`**
- **Authentication**: Yes
- **Description**: Retrieves all books that are currently issued to users.

### **11. Get All Unissued Books**

- **Endpoint**: **`GET /unissued`**
- **Authentication**: Yes
- **Description**: Retrieves all books that are currently unissued.

### **12. Get All Users**

- **Endpoint**: **`GET /users`**
- **Authentication**: Yes
- **Description**: Retrieves details of all users.

### **13. Get Subscribers**

- **Endpoint**: **`GET /subscribers`**
- **Authentication**: Yes
- **Description**: Retrieves a list of subscribers to the newsletter.

### **14. Newsletter**

- **Endpoint**: **`POST /news`**
- **Authentication**: Yes
- **Description**: Sends a newsletter to all subscribers.
- **Request Body**:
    - **`subject`** (string): Newsletter subject.
    - **`content`** (string): Newsletter content.

### **15. Due Books**

- **Endpoint**: **`GET /duebooks`**
- **Authentication**: Yes
- **Description**: Retrieves a list of books that are due.

### **16. Update Stock**

- **Endpoint**: **`PATCH /update/:id`**
- **Authentication**: Yes
- **Description**: Updates the stock quantity for a particular book identified by its ID.
- **Request Body**:
    - **`stock`** (number): New stock quantity.

### **17. Get Activity Logs**

- **Endpoint**: **`GET /logs`**
- **Authentication**: Yes
- **Description**: Retrieves activity logs for the application.

### **18. Block User**

- **Endpoint**: **`PATCH /block/:id`**
- **Authentication**: Yes
- **Description**: Blocks a user identified by their ID.

### **19. Unblock User**

- **Endpoint**: **`PATCH /unblock/:id`**
- **Authentication**: Yes
- **Description**: Unblocks a user identified by their ID.

### **20. Notify Book Defaulters**

- **Endpoint**: **`POST /notify`**
- **Authentication**: Yes
- **Description**: Notifies users who have defaulted on returning books.

### **21. Get List of Blocked Users**

- **Endpoint**: **`GET /blocked`**
- **Authentication**: Yes
- **Description**: Retrieves a list of blocked users.

### **22. Get E-Book**

- **Endpoint**: **`GET /ebook/:id`**
- **Authentication**: Yes
- **Description**: Retrieves the E-Book for a particular book identified by its ID.

### **23. Update Subscription Plan for a Particular User**

- **Endpoint**: **`PUT /update-plan/:id`**
- **Authentication**: Yes
- **Description**: Updates the subscription plan for a particular user identified by their ID.
- **Request Body**:
    - **`subscriptionPlan`** (string): New subscription plan.
