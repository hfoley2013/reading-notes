# API Design

## Readings

* [API Design Best Practices](https://docs.microsoft.com/en-us/azure/architecture/best-practices/api-design)

## References

* [RegExr](https://regexr.com/)
* [Regex Tutorial](https://medium.com/factory-mind/regex-tutorial-a-simple-cheatsheet-by-examples-649dc1c3f285)
* [Regex 101](https://regex101.com/)

## Questions

### API Design Best Practices

* **What does REST stand for?**
  * Representational State Transfer
* **REST APIs are designed around a ____.**
  * Resources, which are any kind of object, data, or service that can be accessed by the user's client
* **What is an identifier of a resource? Give an example.**
  * URI
  * `https://mywebsite.com/orders/1`
* **What are the most common HTTP verbs?**
  * `GET`
  * `POST`
  * `PUT`
  * `PATCH`
  * `DELETE`
* **What should the URIs be based on?**
  * The nouns of the resources, not verbs
* **Give an example of a good URI.**
  * `https://mywebsite.com/orders`
* **What does it mean to have a ‘chatty’ web API? Is this a good or a bad thing?**
  * It is an API that exposes a large number of small resources
  * This is bad since it will slow down performance
* **What status code does a successful `GET` request return?**
  * `200 (OK)`
* **What status code does an unsuccessful `GET` request return?**
  * `404 (Not Found)`
* **What status code does a successful `POST` request return?**
  * `201 (Created)`
* **What status code does a successful `DELETE` request return?**
  * `204 (No Content)`
