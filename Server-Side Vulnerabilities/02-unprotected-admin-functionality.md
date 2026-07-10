# Unprotected Admin Functionality

Checked `robots.txt` first, habit at this point. Had `/admin` disallowed, which usually means "here's the thing we don't want indexed but forgot to protect."

Went straight to `/admin` with no login at all. Full admin panel loaded, deleted the target user. No auth check on the route, just relied on the URL being non-obvious.

**Fix:** robots.txt isn't access control, gate admin routes server-side.
