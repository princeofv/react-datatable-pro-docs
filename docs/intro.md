---
sidebar_position: 1
---

<!-- 
---
id: example-component
title: DataTable Component Example
sidebar_label: DataTable Example
--- -->

## Overview

The `DataTable` component is a versatile table component for displaying and managing tabular data. It supports features such as sorting, filtering, pagination, and customizable actions.

## Installation

To use the `DataTable` component in your project, install the required dependencies:

```bash
npm install react-datatable-pro @mui/material @mui/icons-material

```

# Example Usage
Import the DataTable component and use it in your React application. In this example, we'll create a simple product table:

```jsx
Copy code
import React from 'react';
import DataTable from '@path/to/DataTable';

const MyDataTable = () => {
  const handleView = (row) => {
    console.log('Viewing row:', row);
    // You can customize this function to display the "View" action as needed
  };

  const handleEdit = (row) => {
    console.log('Editing row:', row);
    // You can customize this function to handle the "Edit" action as needed
  };

  const columns = [
    { id: 'id', label: 'ID', sortable: true },
    { id: 'name', label: 'Product Name', sortable: true },
    { id: 'price', label: 'Price', sortable: true },
    { id: 'category', label: 'Category', filterOptions: ['Electronics', 'Clothing', 'Books'] },
  ];

  const data = [
    { id: 1, name: 'Laptop', price: 1200, category: 'Electronics' },
    { id: 2, name: 'T-shirt', price: 25, category: 'Clothing' },
    { id: 3, name: 'Book', price: 15, category: 'Books' },
    // Add more data as needed
  ];

  return (
    <DataTable
      columns={columns}
      data={data}
      title='Product Table'
      rowsPerPageOptions={[5, 10, 25]}
      customHeader={<h2>Custom Table Header</h2>}
      onView={handleView}
      onEdit={handleEdit}
    />
  );
};

export default MyDataTable;
```

## Props

### `columns` (array, required)

An array of column configurations. Each column configuration should have an `id`, `label`, and may include `sortable`, `filterOptions`, `colspan`, and `rowspan`.

### `data` (array, required)

An array of data objects. Each object represents a row in the table.

### `rowsPerPageOptions` (array, optional)

An array of options for the number of rows per page in the pagination control.

### `customHeader` (React Node, optional)

A custom header element to be displayed above the table.

### `title` (string, optional)

A title for the table.

### `onView` (function, optional)

A callback function called when the "View" action is clicked on a row.

### `onEdit` (function, optional)

A callback function called when the "Edit" action is clicked on a row.

## Advanced Usage

### Custom Styling
You can customize the styling of the table and its components using custom CSS or styled components.

```jsx
Copy code
// Example: Custom styling using styled-components
import styled from 'styled-components';
import DataTable from '@path/to/DataTable';

const StyledDataTable = styled(DataTable)`
  // Add your custom styles here
`;

const MyStyledComponent = () => {
  // Your component logic here
  return <StyledDataTable columns={/* your columns */} data={/* your data */} />;
};
Integration with Redux
You can integrate the DataTable component with state management libraries like Redux for more complex applications.

jsx
Copy code
// Example: Integration with Redux
import { connect } from 'react-redux';
import DataTable from '@path/to/DataTable';

const MyReduxComponent = ({ dispatch, data }) => {
  // Your component logic here
  return <DataTable columns={/* your columns */} data={data} />;
};

export default connect((state) => ({ data: state.data }))(MyReduxComponent);
```

# Conclusion
The DataTable component provides a flexible and feature-rich solution for displaying tabular data in React applications. Customize it according to your needs and enjoy the powerful features it offers.
