# Basic SSRF Against the Local Server

Stock checker takes a full URL (`stockApi` param) and fetches it server-side. Nothing stops you from pointing it wherever.

Set it to `http://localhost/admin`, got the internal admin page reflected back in the response even though it's not exposed externally. Changed the path to the delete endpoint for the target user, sent it, response confirmed the delete went through.

**Fix:** whitelist allowed hosts for anything the server fetches on your behalf, don't let user input pick the destination.
