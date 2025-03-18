# React Components Collection

The **React Components Collection** is a curated library of reusable and standalone React components. Designed with UX/UI in mind, these components are tree-shakable, lightweight, and easy to integrate into any React project.

---

## Key Features

- **Standalone and Modular**: Import only the components you need.
- **Rich Variety of Components**: Includes essential components like:
  - **Date Pickers**: Fully customizable date selection tools.
  - **Color Pickers**: User-friendly color pickers with a modern UI.
  - **Toggle Switches**: Easy-to-use switches for toggling states.
  - **Dropdown Menus**: Multi-level, customizable dropdowns.
  - **Modal Dialogs**: Simple, responsive modals for displaying content.
- **Tree-Shakable**: Optimized for modern build tools, reducing bundle size.
- **Lightweight and Dependency-Free**: Minimizes external dependencies for smooth integration.

---

## Installation

Install the package via npm or yarn:

### Using npm:

```bash
npm install react-components-collection
```

### Using yarn:

```bash
yarn add react-components-collection
```

---

## Usage

### Importing Components

You can import components individually for better tree-shaking:

```javascript
import DatePicker from "react-components-collection/dist/DatePicker";
```

Alternatively, you can import multiple components from the main entry point:

```javascript
import { DatePicker, ColorPicker } from "react-components-collection";
```


### Example

Here’s an example of how to use the **DatePicker** component:

```jsx
import React, { useState } from "react";
import DatePicker from "react-components-collection/dist/DatePicker";

function App() {
  const [selectedDate, setSelectedDate] = useState(null);

  return (
    <div>
      <h1>Select a Date</h1>
      <DatePicker
        value={selectedDate}
        onChange={(date) => setSelectedDate(date)}
      />
    </div>
  );
}

export default App;
```
---

## Demo

You can check out he available components [here.](#)
