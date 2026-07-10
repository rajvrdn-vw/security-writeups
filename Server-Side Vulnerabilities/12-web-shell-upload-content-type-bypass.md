# Web Shell Upload via Content-Type Bypass

Same avatar upload but this one actually checks something, the `Content-Type` header has to say `image/jpeg` or it rejects the file.

Only checks the header though, not the actual bytes. Sent the same PHP shell but set `Content-Type: image/jpeg` on that part of the multipart request in Repeater. Upload went through.

Same as before after that, hit the shell with `?cmd=id`, confirmed, then deleted the target file.

**Fix:** check the file itself, not a header the client can just lie about.
