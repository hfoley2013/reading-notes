# HTML Table Basics

## Reading

* [HTML Table Basics](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Basics)

## Notes

### What is a Table?

* A structured set of data in columns and rows **(tabular data)**
* Tables are rigid structures that make data interpretation easier through visual associations between row and column headers
* Tables **should not** be used for web-design layouts due to the added complexity required by their tag to create semantic meaning for screen readers and target CSS coding

### Making a Table

* Basic Syntax
  * `<table>` initiates the table
  * Rows are generated from the top down via `<tr>`
  * Table data across the columns in a row are generated using the `<td>` tag
  * Table headers can be created using the `<th>` tag

  ``` html
  <table>
    <tr>
      <th>Header1</th>
      <th>Header2</th>
    </tr>
    <tr>
      <td>Data1</td>
      <td>Data2</td>
  </table>
  ```
