
# User Management Screen - UI Specification

## **Overview**
The User Management screen is designed to allow administrators to manage system users. This includes creating new users, editing existing user details, assigning roles, and enabling/disabling users.

This specification provides a detailed description of the UI components and their expected behavior.

---

## **UI Components**

### **1. Table**
- **Columns**:
  - **ID**: Displays the unique identifier of each user.
  - **User Name**: Displays the username of the user.
  - **Email**: Displays the email address of the user.
  - **Enabled**: Indicates whether the user is active (`true`) or disabled (`false`).
- **Features**:
  - Sorting: Users can sort data by each column (ascending/descending).
  - Filtering: Users can filter the list based on specific criteria (e.g., enabled status).
  - Hide Disabled Users: A checkbox at the top allows toggling visibility of disabled users.

---

### **2. New User Form**
This form is displayed on the right-hand side for creating or editing user details.

- **Fields**:
  1. **Username** (Text Input): The unique identifier for the user.
  2. **Display Name** (Text Input): The full name of the user.
  3. **Phone** (Text Input): The phone number of the user.
  4. **Email** (Email Input): The email address of the user.
  5. **User Roles** (Dropdown): A multi-select dropdown for assigning roles. Options include:
     - Guest
     - Admin
     - SuperAdmin
  6. **Enabled** (Checkbox): Checkbox to enable or disable the user.

- **Buttons**:
  - **Save User** (Top Right): Saves the user details entered in the form.
  - **New User** (Top Left): Clears the form for adding a new user.

---

## **Behavior**

### **Initial Load**
- The table will display all users (enabled and disabled).
- "Hide Disabled User" is unchecked by default.
- The "New User" form will be empty.

---

### **Behavior of Components**

#### **Table**
- **Sorting**: Clicking on a column header sorts the table by that column. Clicking again toggles between ascending and descending order.
- **Filtering**:
  - If "Hide Disabled User" is checked, rows with `Enabled = false` will not be displayed.
  - Unchecking will restore visibility of all users.
  
#### **New User Form**
- **When Adding a New User**:
  - Click the "New User" button to reset the form.
  - Fill in the fields and click "Save User" to add the new user. If any required fields are missing, display an error message.

- **When Editing an Existing User**:
  - Selecting a user in the table populates the form with that user’s data.
  - After making changes, click "Save User" to update the user details.

#### **Save Button Behavior**
- Validations:
  - Ensure "Username" and "Email" are not empty.
  - Validate the email format.
- If validation passes, save the user details. Otherwise, display error messages for the fields that fail validation.

#### **Hide Disabled Users**
- When checked, the table hides all rows where `Enabled = false`.
- When unchecked, all users are shown again.

---

## **Error Handling**
1. **Invalid Input**:
   - Highlight the invalid field(s).
   - Display an error message near the field or at the top of the form.

2. **Save Failure**:
   - If saving the user fails (e.g., due to server issues), display a message: "Failed to save user. Please try again later."

3. **Empty Table**:
   - If no users match the filter criteria, display a message: "No users found."

---

## **Future Enhancements**
- Add bulk actions for enabling/disabling or deleting multiple users.
- Add a search bar to filter users by name, email, or role.

---

### Next Steps
Save this `.md` file in your preferred repository (GitHub, GitLab, or BitBucket). Let me know if you need help with the upload process.
