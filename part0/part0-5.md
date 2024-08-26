Diagrama de aplicación de una sola página

sequenceDiagram

    participant Browser

    participant Servidor


    Browser->>Server: Enviar solicitud HTTP GET a https://studies.cs.helsinki.fi/exampleapp/spa

    server-->>browser: HTML document

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/educer.css

    activate server

    server-->>browser: the css file

    deactivate server

    Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json

    activate server

    server-->>browser: [{ "content": "HTML is easy", "date": "2023-1-1" }, ... ]


