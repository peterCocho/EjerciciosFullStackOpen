Nueva nota en diagrama de aplicación de una sola pagina 

sequenceDiagram

    participant User

    participant Browser

    participant server


    User->>Browser: Hace clic en el botón del formulario

    Browser->>server: Enviar solicitud HTTP a https://studies.cs.helsinki.fi/exampleapp/new_note_spa

    note over Browser: La solicitud incluye los datos del formulario en el cuerpo

    server->>server: Procesar solicitud y agregar la nota al arreglo

    server-->>Browser: Responde con HTTP 201 (Redirección)

    Browser->>server: Enviar solicitud HTTP GET a https://studies.cs.helsinki.fi/exampleapp/spa

    server-->>browser: HTML document

    deactivate server

    Note right of browser: The browser executes the callback function that renders the notes

    note over Browser: La página se recarga con la nueva nota

    Browser-->>User: Muestra la página de Notas actualizada

