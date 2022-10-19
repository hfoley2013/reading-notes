# Local Storage and How to Use it on Websites

## Reading

* [Local Storage and How to Use it on Websites](https://www.smashingmagazine.com/2010/10/local-storage-and-how-to-use-it/)

## Notes

* Web apps are **stateless**, meaning that they will *reset* upon refreshing the app or reopening it after closing
* Applications on local storage will restore to its *most recent state*
* To use local storage in HTML5 capable documents, use the `localStorage` object in JavaScript
  * Can take `setItem()` method to set a key, value pair
  * `getItem()` method retrieves a key, value pair
  * `removeItem()` method to delete a key, value pair
**NOTE:** `sessionStorage` can be used if you want to only retain the information for the duration of the sessions (i.e. the browser window closes)
* Local Storage only stores *strings*
  * Workaround: `JSON.stringify()` & `JSON.parse`

  ```json
  var car = {};
  car.wheels = 4;
  car.doors = 2;
  car.sound = 'vroom';
  car.name = 'Lightning McQueen';
  console.log( car );
  localStorage.setItem( 'car', JSON.stringify(car) );
  console.log( JSON.parse( localStorage.getItem( 'car' ) ) );
  ```
