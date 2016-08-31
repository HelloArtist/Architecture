## Implementing communication between microservices

1. each server should have 2 main API functions (watch for camel-case):  
  - `areYouThere`:  
  ```livescript
    params: null (undefined!)  
    response: Boolean
  ```
  - `getServerDescription`:  
  ```livescript
    params:   
      serverType: ["nodejs" or "php" or "java"]  
    response:   
      desc: 
        String  # contains a general description about that server or platform (find it in wikipedia :))  
      
      null      # if couldn't find that
  ```
  
  If server doesn't have that description it should ask other servers excluding the requesting server
  
2. Every server should make a request to others every 5 second for different serverType  
   then show the request and response in console.
   It should also check other servers' health (`areYouThere`) before making any new request.
   So it will be 2 requests every 5 second. :)

Don't need request ID till we add client-side
