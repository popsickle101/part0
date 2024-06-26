```mermaid

sequenceDiagram
    participant user
    participant browser
    participant server

    user->>browser: Write note and click Save
    Note right of browser: The browser captures the input and prepares a POST request

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa with JSON data
    activate server
    server-->>browser: 201 Created with JSON response
    deactivate server

    Note right of browser: The server responds with the created note data

    browser->>browser: Update the notes list in the UI
    Note right of browser: The browser updates the UI to display the new note without reloading the page
