## Token Authentication vs Cookies
- Typical Web App is mostly stateless becuse of its request response nature.
- But since most web apps need state, in order to hold state between the client and the server, cookies are used, such that the server can send a cookie with every response back to the client 
-  This means that the client can now send the cookie with the next request back to the server.
-  This way the server can maintain a session with the stateless client, knowing mostly everything about the app's state, but stored in the server.