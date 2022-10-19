# Class 13: Reading Notes & Assignment Summary

## Assignments

### Local Storage and How To Use It On Websites

* **Why would a developer use local storage for a web application?**
  * Local storage allows you to access information from your previous sessions
  * Local storage prevents you from being banned from services
  * If an API call fails, you will still have data to display
* **What information should not be stored in local storage?**
  * Private information
  * Passwords
  * Locations
  * Search history
* **Local storage can store what type of data? How would you convert it to that type before storing?**
  * Local storage stores everything as strings
  * Workaround to store data properly:
    * `JSON.stringify()`
    * `JSON.parse`
