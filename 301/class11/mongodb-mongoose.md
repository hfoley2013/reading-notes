# MongoDB and Mongoose

## Readings

* [SQL vs. NoSQL](https://www.thegeekstuff.com/2014/01/sql-vs-nosql-db/?utm_source=tuicool)
* [VIDEO: SQL vs. NoSQL](https://www.youtube.com/watch?v=ZS_kXvOeQ5Y)

## References

* [Mongoose API](https://mongoosejs.com/docs/api.html#Model)
* [React Router](https://reactrouter.com/web/api/BrowserRouter)

## Questions

## Reading

* **5 Differences between SQL and NoSQL databases**

  | **SQL** | **NoSQL** |
  | --- | --- |
  | Relational Database| Non-Relational/Distributed Database |
  | Table Based| Document Based, Key-Value Pairs, Graph DB, or Wide-Column Stores |
  | Predefined Scheme| Dynamic Schema for unstructured data |
  | Vertically scalable (Increase HP of Hardware) | Horizontally Scalable (Increase # of Servers) |
  | SQL defines and manipulates data| Queries focus on collections of documents|

* **What kind of data is a good fit for an SQL database?**
  * Structured data in tabular format
  * Data requiring complex queries
  * Highly transactional type applications
* **Give a real world example.**
  * [MySQL Community Edition](https://www.thegeekstuff.com/2008/07/howto-install-mysql-on-linux/)
* **What kind of data is a good fit a NoSQL database?**
  * Unstructured data
  * Hierarchal data with Key-Value pairs
  * Large data sets
* **Give a real world example.**
  * [MongoDB](https://www.thegeekstuff.com/2013/01/install-mongodb/)
* **Which type of database is best for hierarchical data storage?**
  * NoSQL
* **Which type of database is best for scalability?**
  * Depends on the resources available
    * SQL can easily scale vertically by increasing the processing power of your hardware
      * Good if you have a single resource that you can continue to upgrade
    * NoSQL can easily scale horizontally by increasing the number of servers you have to reduce the load across all servers
      * Good if you can afford to obtain and run multiple servers

## Video

* **What does SQL stand for?
What is a relational database?**
  * Structured Query Language
    * Basic structure: `SELECT id, name, price FROM products`
      * `SELECT` & `FROM` are **keywords**
      * `id`, `name`, `price`, and `products` are parameters
        * `id - price` are column headers in the database
        * `products` is the database we want to query
  * Relational Database
    * Stores tables of data
    * Enables use of SQL
    * Composed of `Fields (Columns)` and `Records (Rows)`
    * There are known relationships been tables stored within the database
      * Example:
        * `Users` table stores all customer info
        * `Products` table stores all product information
        * `Orders` table is created from `Users` and `Products` by combining information about products and users to create an order sheet
    * Relationships can be:
      * **One-to-One**
        * One data point connects to only one other table
      * **One-to-Many**
        * One data point connects to many tables
      * **Many-to-Many**
        * Data points are derived from multiple other data points and connect to many other data points
* **What type of structure does a relational database work with?**
  * Tabular data
* **What is a ‘schema’?**
  * The structure of the Fields and Records of the table
  * All data within the table **MUST** adhere to the schema
  * All data pulled into the table on updates must be *normalized*
    * It must be groomed to fit the data structure of the schema
* **What is a NoSQL database?**
  * A non-relational database
  * Data is stored in `Collections` and `Documents`
  * There is little to no relationship merging in a NoSQL database since data is already stored in usable Key-Value pairs within the `Documents`
    * This allows for faster, more efficient, and more flexible queries
* **How does it work?**
* **What is inside of a MongoDB database?**
  * *Collections* of *documents*
    * **Collections** are like the tables from SQL
    * **Documents** are like the fields (data) from SQL
      * **NOTE:** The content of each document *does not* need to be the same, unlike in SQL
        * READ: **There is *no* schema**
* **Which is more flexible - SQL or MongoDB? and why.**
  * MongoDB is more flexible due to its NoSQL design
  * Without having to strictly adhere to a schema, MongoDB allows you to more flexibly add and query data
* **What is the disadvantage of a NoSQL database?**
  * Less reliability of data due to inconsistent data structures
  * Cannot conduct as complex of queries as in SQL
  * Difficult to update due to independent nature of `Documents`

## Notes

### SQL vs. NoSQL Reading

* TODO

### SQL vs. NoSQL Video

* TODO
