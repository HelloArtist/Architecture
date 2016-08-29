## Implementing communication between microservices

1. each server should have 3 main API functions (watch for camel-case):  
  - `imAlive`:  
    query: null (undefined!)  
    response: boolean  
  - `getServerDescription`:  
    ```
    query:   
      serverType: ["nodejs", "php", "java"]  
    response:   
      desc: string  // contains a general description about that server or platform (find it in wikipedia)  
  
