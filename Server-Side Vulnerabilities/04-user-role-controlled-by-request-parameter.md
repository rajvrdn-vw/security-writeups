# User Role Controlled by Request Parameter

Logged in as the low-priv user, checked cookies on the account request. Found `Admin=false` sitting right there in the Cookie header.

Sent the request to Repeater, flipped it to `Admin=true`, resent, response changed to admin content. Then applied the same cookie in the browser (intercepted the request, edited it live, forwarded) so my actual session had it too.

Went to `/admin`, deleted the user. Whole "auth check" was just trusting a cookie I could edit myself.

**Fix:** role/permission has to live server-side, never in something the client can just rewrite.
