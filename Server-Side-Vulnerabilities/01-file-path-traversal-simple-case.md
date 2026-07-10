# File Path Traversal - Simple Case

Product images load via `/image?filename=39.jpg`. Server just appends whatever you send to a base path, no sanitization.

Threw `../../../etc/passwd` at it:

```
GET /image?filename=../../../../etc/passwd
```

Took a couple tries to get the depth right (server strips some but not enough). Got the full passwd file back. Lab done.

**Fix:** validate the resolved path stays inside the intended folder, don't trust raw filenames from the client.
