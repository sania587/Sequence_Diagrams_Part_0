# Sequence_Diagrams_Part_0

<br> <b>Part 0.4</b> The diagram is to fetch the input text from the user and display it onto the same page (Traditional Web application) by reloading it.
```mermaid
sequenceDiagram
    participant user
    participant browser
    participant server

    user->>browser: Save(new_note)
    activate server

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note 
    activate server
    server-->>browser: HTTP status code 302 and redirect to /notes
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: The css file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: The JavaScript file
    deactivate server

    Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: The file content
    deactivate server

    Note right of browser: The browser executes the callback function that render all the notes to the page

    browser-->>user: The page
```

<br>
<br> <b>Part 0.5</b> The diagram is to Load the page with single page application (SPA).

``` mermaid
sequenceDiagram
   
    participant browser
    participant server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
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

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: the file content
    deactivate server

    Note right of browser: The browser executes the callback function that render all the notes to the page
```

<br>
<br> <b>Part 0.6</b> The diagram is to fetch the input text from the user and display it onto the same single page application (SPA)


``` mermaid
sequenceDiagram
    participant user
    participant browser
    participant server

    
    user->>browser: Save(new_note)
    activate server

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note (AJAX)
    activate server
    server-->>browser: Display new note data
    deactivate server

    browser ->> browser: Update the DOM with the new note added
    Note right of browser: The browser update the notes added to the page

    browser-->>user: The page

```

