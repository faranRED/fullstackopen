Exercise Number 0.4 

``` mermaid

sequenceDiagram
participant Browser
participant Server

Browser->>Server: POST https://studies.cs.helsinki.fi/exampleapp/notes
Note right of Browser: Submitting new note performs new GET request.
activate Server
Server->>Browser: Updated HTML document
deactivate Server

Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
activate Server
Server-->>Browser: the css file
    deactivate Server

Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
activate Server
Server-->>Browser: the JavaScript file
deactivate Server

Note right of Browser: The browser starts executing the JavaScript code that fetches the JSON from the server

Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
activate Server
Server-->>Browser: 
deactivate Server

Note right of Browser: The browser executes the callback function that renders the updated notes
