Nuevo diagrama de nota

sequenceDiagram

participant User

participant Browser

participant Server

User->>Browser: Clicks the button on the form

Browser->>Server: Send HTTP POST request to https://studies.cs.helsinki.fi/exampleapp/new_note

note over Browser: Request includes form data in the body

Server->>Server: Process request and add the note to the array

Server-->>Browser: Responds with HTTP 302 (Redirect)

Browser->>Server: Send HTTP GET request to https://studies.cs.helsinki.fi/exampleapp/notes

server-->>browser: HTML document

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css

activate server

server-->>browser: the css file 

deactivate server
 browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js 

 activate server 

server-->>browser: the JavaScript file Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server 

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json activate server server-->>browser: [{ "content": "HTML is easy", "date": "2023-1-1" }, ... ] 

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/educer.css activate server 

server-->>browser: the css file deactivate server Note right of browser: The browser executes the callback function that renders the notes note over Browser: The page reloads with the new note

Browser-->>User: Displays the updated Notes page
