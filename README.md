# Q5-UISpecDoc
This repository is for Question 5 in Technical Questionnaire

# USER INTERFACE SPECIFICATION DOCUMENT

## 1. REQUIREMENTS: 
The User Management screen must provide the following functionalities:

### 1.1 User Listing:
- The list of users should be displayed in a table format.
- The table must include the following columns:
    -UserID (must be unique)
    -Username
    -Email
    -Enabled status (boolean)
-The columns must have filtering feature. Also, listing order can be changed by the user of the screen.
e.g.  list by decreasing order in ID/Username and filter by enabled status.

### 1.2 Data Input Form:
The system should have a form to provide input fields for:
  - Username (required*)
  - Display Name
  - Phone Number
  - Email (required*)
  - User Roles (selection)
  The selection for user roles field will be in following options:
    1. Guest
    2. Admin
    3. SuperAdmin
  - Enabled (checkbox)

- All fields should be modifiable.

### 1.3 Data Validation:
- Username must not be empty. 
- Email must not be empty and must be in a valid format.
- Phone number must contain only numeric values.
- If user role is not explicitly selected, it should be "Guest" as default. Only 1 type of role can be selected at the same time.
- Enabled field must be checked as default.

### 1.4 User Creation:
The system must allow the administrator to create a new user.
- "New User" button should be provided and it should reset the data input form (req. 1.2) for new input/user.

### 1.5 Editing of Existing User:
The system must allow the administrator to edit an existing user.
- Selecting a user from the table (req. 1.1) shall populate the data input form (req. 1.2) with that specific user's data.

### 1.6 Save Functionality:
The system must have "Save User" button and this button must be usable after user creation or editing of an existing user.

### 1.7 Filtering:
The system must provide a "Hide Disabled User" option as a checkbox. 
- When checkbox is clicked, the disabled users must not be displayed in the table (req. 1.1).

### 1.8 Initial State of The Screen: 
When the page loads:
- The user list must be displayed in a table format (req. 1.1).
- The data input form (req. 1.2) must be empty or in default state.



## 2. UI COMPONENTS:

### 2.1 Top Action Bar:
Shall include: 
  1. New User Button:
     - Type: Button
     - Label: New User
     - Clears the form and prepares the screen for creation of a new user
  3. Hide Disabled User Checkbox:
     - Type: Checkbox
     - Label: Hide Disabled User
     - Filters the user list table in order to hide disabled users.
  5. Save User Button:
     - Type: Button
     - Label: Save User
     - Updates an existing user or saves a new created user.


### 2.2 Left Panel:
User listing table (req. 1.1) must be displayed. 

### 2.3 Right Panel:
Data input form (req. 1.2) must be displayed. 
- Display a title such as "New User" or "Edit User" depending on the current action.

### 2.4 Validation and Feedback Components: 
- When input is invalid, validation message such as "Invalid Input" should be displayed near fields.
- After a successful save operation, success message such as "Successfully Saved" should be displayed near Save User Button.
- After a failed save operation, error message such as "Failed" should be displayed near Save User Button.




## 3. FUNCTIONAL BEHAVIOUR:
The system must behave as follows: 

### 3.1 Page Load: 
When the page loads: 
- The user list table should be retrieved from the DB and displayed in a table format.
- The data input form must be empty or set to default state.

### 3.2 New User Action:
When the "New User" button is clicked: 
- The data input form shall be cleared.
- The form must switch to "New User" mode and display the title.
- No user shall be selected in the table.

### 3.3 User Selection:
When a user is selected from the user list table: 
- The form should be populated with the selected user's information.
- The form must switch to "Edit User" mode and display the title.

### 3.4 Editing User Action: 
When the user of the screen modifies any field: 
- The updated values should be shown in the form.
- No changes will be saved until the "Save Button" is clicked.
- Validation requirements should be also checked in editing mode.

### 3.5 Save User Action: 
When the "Save User" button is clicked: 
- The system should validate the fields in the data input form.
- The system shall prevent duplicate usernames.
- If validates:
  - A new user should be created or existing user should be updated.
  - Changes should reflected in the user list table immediately.
  - Success message should be displayed.
  - The data input form should be cleared.
- If validation fails:
  - Error message should be displayed.
  - The user must not be saved.
 
### 3.6 Hide Disabled User Action: 
When the "Hide Disabled User" button is clicked: 
- Disabled users must not be displayed in the user list table.
When it is unchecked:
- All users must be displayed.



  
