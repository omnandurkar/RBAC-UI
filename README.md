
# Role-Based Access Control (RBAC) UI for Shoppy Dashboard

This repository contains a **Role-Based Access Control (RBAC)** UI implementation for the **Shoppy Dashboard**. The dashboard is designed for e-commerce management, with different sections and apps that require role-based permissions. The dashboard includes pages for managing **orders**, **employees**, and **customers**, along with various built-in apps and charts for enhanced functionality.

---

## Features

### Pages
The following pages are available in the Shoppy Dashboard:

- **Orders** – View and manage customer orders.
- **Employees** – Manage employee data and permissions.
- **Customers** – Access customer details and manage their profiles.

### Apps
The dashboard includes multiple utility apps to enhance productivity and decision-making:

- **Calendar** – A calendar interface for scheduling and managing events.
- **Kanban** – A Kanban board for managing tasks and workflows.
- **Editor** – A rich text editor for creating and editing content.
- **Color Picker** – A tool for selecting colors for UI customization.

### Charts
The dashboard includes the following chart types to visualize business data:

- **Line Chart** – Display trends over time.
- **Area Chart** – Visualize data with filled areas beneath the lines.
- **Bar Chart** – Compare data in bars.
- **Pie Chart** – Represent proportions of a whole.
- **Financial Chart** – View financial trends and patterns.
- **Color Mapping** – Visualize data through color-coded values.
- **Pyramid Chart** – A hierarchical chart showing proportions.
- **Stacked Chart** – Display data series stacked on top of each other.

---

## Role-Based Access Control (RBAC)

RBAC allows different users to have access to certain features of the dashboard based on their assigned roles. The following roles are available:

- **Admin** – Full access to all pages and apps.
- **Manager** – Access to orders, employees, and customers, but limited access to certain apps.
- **Employee** – Limited access, restricted to specific pages or functions like viewing orders and customers.
- **Viewer** – Read-only access to charts and other non-editable content.

The RBAC system ensures that users can only access the parts of the dashboard relevant to their role, ensuring security and ease of use.

---

## Installation

To run the Shoppy Dashboard locally, follow these steps:

### Prerequisites
- Node.js (version 16 or higher)
- npm (Node Package Manager)

### Steps

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/shoppy-dashboard-rbac.git
   cd shoppy-dashboard-rbac
    ```

2. **Install dependencies:**
   ```bash
   npm install
    ```

3. **Run the development server:**
   ```bash
   npm start
    ```

4. **Open the dashboard in your browser:**
    ```
    http://localhost:3000
     ```


## Role Management

Role-Based Access Control (RBAC) allows different users to have varying levels of access to different sections and features of the dashboard. Below are the available roles and their permissions:

- **Admin Role**: Full access to all features of the dashboard, including Pages (Orders, Employees, Customers), Apps (Calendar, Kanban, Editor, Color Picker), and all Chart types.
- **Manager Role**: Can access Pages like Orders, Employees, and Customers, but with restricted access to some Apps and Charts.
- **Employee Role**: Limited access, mainly restricted to viewing Orders and Customer data. Does not have access to Apps or customize Charts.
- **Viewer Role**: Provides read-only access to Charts and other non-editable content. Users in this role cannot modify data or interact with apps.

### Modifying Roles and Permissions

You can modify the roles and permissions in the following files:

- **`src/context/RoleContext.js`**: Contains the logic for managing roles and assigning permissions to different sections of the dashboard (Pages, Apps, Charts).
- **`src/context/authContext.js`**: Used to manage user authentication and simulate different user roles for testing purposes.

### Example of Role Definitions:

In **`RoleContext.js`**, you can define access for each role like this:

```javascript
const roles = {
  admin: {
    canAccess: ['orders', 'employees', 'customers', 'calendar', 'kanban', 'editor', 'color-picker', 'charts'],
    canEdit: ['orders', 'employees', 'customers'],
  },
  manager: {
    canAccess: ['orders', 'employees', 'customers', 'calendar', 'kanban', 'charts'],
    canEdit: ['orders', 'employees'],
  },
  employee: {
    canAccess: ['orders', 'customers'],
    canEdit: ['orders'],
  },
  viewer: {
    canAccess: ['charts'],
    canEdit: [],
  },
};

```

In this example, the Admin role has full access to all features, while the Manager role has limited access to certain apps and features. The Employee role has even more restrictions, and the Viewer role has read-only access to charts.

## Usage

### 1. **Login as Admin**  
Admins have full access to all features of the dashboard, including:

- **Pages**: Orders, Employees, Customers
- **Apps**: Calendar, Kanban, Editor, Color Picker
- **Charts**: All chart types (Line, Area, Bar, Pie, Financial, etc.)

Admins can view and edit data on all pages and utilize all apps and charts for analysis and management.

### 2. **Login as Manager**  
Managers have access to the following features:

- **Pages**: Orders, Employees, and Customers (with limited permissions on editing data)
- **Apps**: Calendar, Kanban, and Charts
- **Charts**: Access to various chart types for analysis, with restrictions on editing certain data.

Managers can view and edit data in the **Orders** and **Employees** pages, but they cannot access all app features available to Admins.

### 3. **Login as Employee**  
Employees have very limited access, mainly for viewing data:

- **Pages**: Orders and Customers (view only)
- **Apps**: Restricted (no access to apps like Calendar, Kanban, or Editor)
- **Charts**: Restricted to view-only charts (no editing or customization)

Employees can only view the Orders and Customers pages but cannot make changes to data or interact with apps.

### 4. **Login as Viewer**  
Viewers have the most restricted access, providing **read-only** access to charts:

- **Pages**: No access to Pages like Orders, Employees, or Customers.
- **Apps**: No access to Apps like Calendar, Kanban, or Editor.
- **Charts**: View-only access to Charts (cannot modify or customize any chart data).

Viewers are only able to access and view charts in the dashboard without making any changes or interacting with other features.

---

## Contributing

Contributions are welcome! If you'd like to contribute to this project, follow these steps:

1. **Fork the repository** on GitHub.
2. **Create a new branch**:  
   `git checkout -b feature-name`
3. **Commit your changes**:  
   `git commit -am 'Add feature or fix'`
4. **Push your branch**:  
   `git push origin feature-name`
5. **Create a pull request** to merge your changes into the main repository.

Please ensure that your code follows the existing style and include tests for any new functionality or bug fixes.

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Acknowledgments

- Thanks to the contributors and the open-source community for their tools and libraries used in this project.


