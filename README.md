# Sequence_Diagrams_Part_0

<br> <b>Part 0.4</b> The diagram is to fetch the input text from the user and display it onto the same page
```mermaid
sequenceDiagram
    participant user
    participant browser
    participant server

    user->>browser: Save(new_note)
    activate server

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note 
    activate server
    server-->>browser: HTTP status code 302
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: the css file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: the JavaScript file
    deactivate server

    Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: the file content
    deactivate server

    browser-->>user: the page

    Note right of browser: The browser executes the callback function that render all the notes to the page
```
<br> <b>Part 0.5</b> The diagram is to fetch the input text from the user and display it onto the same page


<br> <b>Part 0.6</b> The diagram is to fetch the input text from the user and display it onto the same page
