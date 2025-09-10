# INSTRUCTIONS

``` mermaid
graph LR
    A[Third party System] <--"Web Socket Channel"--> B[G2SF]
```


The G2SF Web Socket interface API provides an easy way allowing the
client system to obtain G2SF stock order information or client
information. Thus, the third party can be freely to build their frontend
application.

It is technical specification document of G2SF VN WebSocket API.

---

# OVERVIEW OF G2SF WEBSOCKET COMMUNICATION 

1.  **WebSocket Connection**:

    - The users|client establishes a WebSocket connection to the G2SF
      Web server.

    - This allows for real-time communication, enabling the server to
      push updates to the client.

2.  **Message Format**:

    - Messages exchanged over the WebSocket are formatted in JSON.

    - Each message includes a Command field to identify the type of
      request or action.

3.  **Session Management**:

    - To interact with the server, users|clients must provide a
      **Session ID** and **User ID** with each data request.

    - These identifiers are obtained after a successful login.

4.  **Data Requests**:

    - Once logged in, users|clients can make requests for data (e.g.,
      order updates) by sending a JSON message that includes the Session
      ID and User ID.

5.  **Real-Time Updates**:

    - After verifying the user's session, the server pushes order
      updates to the appropriate client devices.

    - This ensures that users receive timely information relevant to
      their sessions.

``` mermaid
graph TD
    A[User 1 / Client 1] --> B(G2SF Web Server)
    C[User 2 / Client 2] --> B
    D[User 3 / Client 3] --> B
    B --> E[G2SF Trade Server]
```

