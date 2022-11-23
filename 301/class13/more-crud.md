# More CRUD

## Readings

* [CRUD Basics](https://medium.com/geekculture/crud-operations-explained-2a44096e9c88)
* [Speed Coding: Building a CRUD API](https://www.youtube.com/watch?v=EzNcBhSv1Wo)

## Questions

### CRUD Basics

* **Which HTTP method would you use to update a record through an API?**
  * `PUT` will replace all current data of the target resource with the content in the request
  * `PUT` requests also need to be targeted by `/:id` to ensure the correct record is updated
* **Which REST methods require an ID parameter?**
  * `DELETE`
  * `PUT`

### Speed Coding: Building a CRUD API

* **What’s the relationship between REST and CRUD?**
  * CREATE: `POST`
  * READ: `GET`
  * UPDATE: `PUT` or `PATCH`
  * DELETE: `DELETE`
* **If you had to describe the process of creating a RESTful API in 5 steps, what would they be?**
  1. Import packages needed to create: `axios`, `express`, `mongoose`
  2. Create your routes: GET, POST, PUT, DELETE
  3. Confirm that routes are functioning on the server with Thunderclient/Insomnia
  4. Define your database location and define your schema for your data
  5. Build out your `async await` functions within a `try catch next` and test that the functions return the expected outputs with Thunderclient/Insomnia

## Notes

![CRUD](https://miro.medium.com/max/1100/1*2eBdh0vLZjUyCDF6x1EqvQ.png)

* TODO: Add detailed notes from video

## In Class Notes

### Lab 13: Update Book Details

* `PUT`
  * Add a `form` to update a book
  * Update form calls `putBooks` and updates database
* Route
  * `app.put('books/:id', putBooks)`
* Function

  ```js
  async function putBooks(req, res, next) {
    try {
      let id = req.params.id;
      let updatedBooksData = req.body;

      let updatedBooks = await Books.findByIdAndUpdate(id, updatedBooksData, {new: true, overwrites: true});
      res.status(200).send(updatedBooks);

    } catch(error) {
      next(error);
    }
  }
  ```

  ```js
  updatedBooks = async (bookToUpdate) => {
    try {
      let url = `${process.env.REACT_APP_SERVER}/books/${bookToUpdate._id}`;
      let updatedBookObj = await axios.put(url, bookToUpdate);

      let updatedBookArr = this.state.books.map(book => {
        return book._id === bookToUpdate._id 
          ? updatedBookObj.data
          : book;
      });
      this.setState({
        books: updatedBookArr
      });
    } catch(error) {
      console.log('Error: ', error.response.data);
    }
  }
  ```
