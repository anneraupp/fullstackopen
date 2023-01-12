## 0.4: New note diagram

```mermaid
sequenceDiagram

    BROWSER->>SERVER: HTTP POST https://studies.cs.helsinki.fi/exampleapp/new_note
    Note over SERVER: server adds content to the data.jason file
    SERVER-->>BROWSER: HTTP status code 302 <br> request HTTP GET to header's Location ' /notes '
    Note over BROWSER: browser reloads the page
    BROWSER->>SERVER: HTTP GET https://studies.cs.helsinki.fi/exampleapp/notes
    SERVER-->>BROWSER: HTML-code
    BROWSER->>SERVER: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css
    SERVER-->>BROWSER: main.css
    BROWSER->>SERVER: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.js
    SERVER-->>BROWSER: main.js

    Note over BROWSER: browser starts executing js-code <br> that requests JSON data from server 

    BROWSER->>SERVER: HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json
    SERVER-->>BROWSER: [{"content":"test","date":"2023-01-11T17:32:32.196Z"}, ...]

    note over BROWSER: browser executes the event handler <br> that renders notes to display


```

## 0.5: Single page app diagram

```mermaid
sequenceDiagram

    BROWSER->>SERVER: HTTP GET https://studies.cs.helsinki.fi/exampleapp/spa
    SERVER-->>BROWSER: HTML-code
    BROWSER->>SERVER: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css
    SERVER-->>BROWSER: main.css
    BROWSER->>SERVER: HTTP GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    SERVER-->>BROWSER: spa.js

    Note over BROWSER: browser starts executing js-code <br> that requests JSON data from server 

    BROWSER->>SERVER: HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json
    SERVER-->>BROWSER: [{"content":"test","date":"2023-01-11T17:32:32.196Z"}, ...]

    note over BROWSER: browser executes the event handler <br> that renders notes to display


```

## 0.6: New note in Single page app diagram

```mermaid
sequenceDiagram

    BROWSER->>SERVER: HTTP POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    Note over SERVER: a new JSON string containing both content and <br> timestamp is saved to data.json file 
    Note over BROWSER: browser does not reload the whole page

    


```
