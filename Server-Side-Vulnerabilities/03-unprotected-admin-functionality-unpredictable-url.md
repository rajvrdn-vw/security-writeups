# Unprotected Admin Functionality with Unpredictable URL

Same idea as the last one but admin path is a random string this time, so guessing it directly isn't realistic.

Logged in as the normal user, checked page source on the account page. Found a commented-out link to the admin panel (`/admin-xxxxx`) that was left in the HTML, probably meant only for admins to see but not actually hidden from view-source.

Went to that URL, no auth check, deleted the user.

**Fix:** don't leak internal links client-side even if commented out, and check auth server-side regardless of how obscure the URL is.
