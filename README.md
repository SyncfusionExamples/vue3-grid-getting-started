#  Getting Started with Syncfusion Vue Grid Components in Vue 3

This section explains how to use Syncfusion Vue components in Vue 3 application.

## Adding Syncfusion Grid packages in the application

 Syncfusion Vue packages are maintained in the [`npmjs.com`](https://www.npmjs.com/~syncfusionorg) registry.
The Grid component will be used in this example. To install it use the following command.

```bash
npm install @syncfusion/ej2-vue-grids --save
```
## Adding CSS reference for Syncfusion Vue Grid components

Import the needed css styles for the  Grid component along with dependency styles in the `<script>` section of the `src/App.vue` file as follows.

```js
<script>
import "../node_modules/@syncfusion/ej2-base/styles/material.css";
import "../node_modules/@syncfusion/ej2-buttons/styles/material.css";
import "../node_modules/@syncfusion/ej2-calendars/styles/material.css";
import "../node_modules/@syncfusion/ej2-dropdowns/styles/material.css";
import "../node_modules/@syncfusion/ej2-inputs/styles/material.css";
import "../node_modules/@syncfusion/ej2-navigations/styles/material.css";
import "../node_modules/@syncfusion/ej2-popups/styles/material.css";
import "../node_modules/@syncfusion/ej2-splitbuttons/styles/material.css";
import "../node_modules/@syncfusion/ej2-vue-grids/styles/material.css";
</script>
```
Note: Grid components use other Syncfusion components too, the dependent component's CSS references need to be added for using all the Grid functionalities.

## Adding Syncfusion Vue Grid component in the application.

You have completed all the necessary configurations needed  for rendering the Syncfusion Vue component. Now, you are going to add the Grid component using following steps.

  1. Import the Grid component in the `<script>` section of the `src/App.vue` file.

  ```html
  <script>
  import { GridComponent, ColumnsDirective, ColumnDirective } from '@syncfusion/ej2-vue-grids';
  </script>
  
  ```
  2. Register the Grid component along with the required child directives which are used in this example. Find the list of child directives and the tag names that can be used in the Grid component in the following table.
  
| Directive Name   | Tag Name    |
|------------------|-------------|
| `ColumnsDirective` | `e-columns` |
| `ColumnDirective`  | `e-column`  |
  
  ```js
import { GridComponent, ColumnsDirective, ColumnDirective } from '@syncfusion/ej2-vue-grids';
  //Component registeration
export default {
    name: "App",
    components: {
      'ejs-grid' : GridComponent,
      'e-columns' : ColumnsDirective,
      'e-column' : ColumnDirective
    }
}
  ``` 
  In the above code snippet, you have registered Grid and the column directives. Column directives are used to define the column definition for the Grid component.
  3. Add the component definition in template section.
  ```html
<template>
    <ejs-grid :dataSource='data'>
        <e-columns>
            <e-column field='OrderID' headerText='Order ID' textAlign='Right'  width=100></e-column>
            <e-column field='CustomerID' headerText='Customer ID' width=120></e-column>
            <e-column field='ShipCountry' headerText='Ship Country' width=150></e-column>
        </e-columns>
    </ejs-grid>
</template>
  
  ``` 
  Above is the Grid component definition, with `dataSource` property binding and columns definitions.
4. Declare the bound properties in the `script` section. Declare the collection `data` which is bound for the `dataSource` property.
  ```js
data() {
  return {
    data:  [
      {
         "OrderID":10248,
         "CustomerID":"VINET",
         "ShipCountry":"France"
      },
      {
         "OrderID":10249,
          "CustomerID":"TOMSP",
          "ShipCountry":"Germany"
      }]
    };
}
  ```
5. Summarizing the above steps, update the `src/App.vue` file with following code.
```html
<template>
  <ejs-grid :dataSource="data">
    <e-columns>
      <e-column field="OrderID" headerText="Order ID" textAlign="Right" :isPrimaryKey="true" width="100"></e-column>
      <e-column field="CustomerID" headerText="Customer ID"  width="80"></e-column>
      <e-column field="ShipCountry" headerText="Ship Country" width="90"></e-column>
    </e-columns>
  </ejs-grid>
</template>
<script>
import { GridComponent, ColumnsDirective, ColumnDirective} from "@syncfusion/ej2-vue-grids";
import "../node_modules/@syncfusion/ej2-base/styles/material.css";
import "../node_modules/@syncfusion/ej2-buttons/styles/material.css";
import "../node_modules/@syncfusion/ej2-calendars/styles/material.css";
import "../node_modules/@syncfusion/ej2-dropdowns/styles/material.css";
import "../node_modules/@syncfusion/ej2-inputs/styles/material.css";
import "../node_modules/@syncfusion/ej2-navigations/styles/material.css";
import "../node_modules/@syncfusion/ej2-popups/styles/material.css";
import "../node_modules/@syncfusion/ej2-splitbuttons/styles/material.css";
import "../node_modules/@syncfusion/ej2-vue-grids/styles/material.css";

export default {
  name: "App",
  // Declaring component and its directives
    components: {
      "ejs-grid": GridComponent,
      "e-columns": ColumnsDirective,
      "e-column": ColumnDirective,
    },
  // Bound properties declaration
  data() {
    return {
      data: [
        {
          OrderID: 10248,
          CustomerID: "VINET",
          ShipCountry: "France",
        },
        {
          OrderID: 10249,
          CustomerID: "TOMSP",
          ShipCountry: "Germany",
        },
      ],
    };
  },
};
</script>

```
## Running the application

Run the application using the following command.

```bash
npm run serve
```
