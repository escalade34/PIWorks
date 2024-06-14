

# User Management Screen Specification

## Overview
The User Management screen is designed to allow administrators to manage users within the system. This document specifies the requirements and details related to the UI components, including their behavior and initial state.

## Initial View
When the User Management screen is first accessed, the following elements are displayed:
- A table listing existing users with columns for ID, User Name, Email, and Enabled status.
- A checkbox labeled "Hide Disabled User" to filter the user list.
- A button labeled "+ New User" for adding a new user.
- An empty form for user details on the right side, ready to be filled for creating or editing a user.
- A "Save User" button to save changes made to user details.

## UI Components

### User Table
- **Columns:**
  - **ID:** Numeric identifier for the user.
  - **User Name:** The username of the user.
  - **Email:** The email address of the user.
  - **Enabled:** Boolean status indicating whether the user is enabled (true/false).
- **Behavior:**
  - Clicking on a column header sorts the list by that column.
  - Clicking on a user row populates the "New User" form with the selected user's details for editing.

### Hide Disabled User Checkbox
- **Label:** "Hide Disabled User"
- **Type:** Checkbox
- **Behavior:**
  - When checked, the table hides users with `Enabled` status set to false.
  - When unchecked, all users are shown in the table.

### New User Button
- **Label:** "+ New User"
- **Type:** Button
- **Behavior:**
  - Clicking the button clears the "New User" form to add a new user.

### New User Form
- **Fields:**
  - **Username:** Text input for the user's username.
  - **Display Name:** Text input for the user's display name.
  - **Phone:** Text input for the user's phone number.
  - **Email:** Text input for the user's email address.
  - **User Roles:** Dropdown menu for selecting user roles (Guest, Admin, SuperAdmin).
  - **Enabled:** Checkbox to set the user's enabled status.
- **Behavior:**
  - The form is initially empty when the "+ New User" button is clicked.
  - If an existing user row is clicked, the form populates with that user's details for editing.
  - The "Enabled" checkbox indicates the user's current enabled status and can be toggled.

### Save User Button
- **Label:** "Save User"
- **Type:** Button
- **Behavior:**
  - Saves the details entered or modified in the "New User" form.
  - Updates the user list table to reflect any changes made.

## Page Behavior

### Initial State
- The user table lists all users, sorted by ID in ascending order.
- The "Hide Disabled User" checkbox is unchecked.
- The "New User" form is empty and ready for new user input.
- The "Save User" button is disabled until there are changes to save.

### Adding a New User
1. Click "+ New User".
2. Fill in the "New User" form with the appropriate details.
3. Click "Save User" to add the new user to the list.

### Editing an Existing User
1. Click on a user row in the table.
2. Modify the details in the "New User" form as needed.
3. Click "Save User" to save the changes.

### Filtering Users
- Check the "Hide Disabled User" checkbox to hide users with `Enabled` status set to false.
- Uncheck the "Hide Disabled User" checkbox to display all users.

## Requirements
- Ensure that the user table supports sorting by columns.
- The "Save User" button should only be enabled when there are changes to save.
- Implement form validation for required fields before allowing a user to be saved.
- The system should provide feedback if a user cannot be saved (e.g., due to validation errors or duplicate usernames).

## Notes for Developers
- Ensure that all form inputs are properly labeled and accessible.
- Implement appropriate error handling and feedback mechanisms for user actions.
- Maintain the state of the form and table to reflect any changes made until explicitly saved or discarded.
