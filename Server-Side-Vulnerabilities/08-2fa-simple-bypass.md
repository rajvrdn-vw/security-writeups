# 2FA Simple Bypass

Logged in with the given creds, got sent to the 2FA code page as expected. Instead of entering a code, just typed `/my-account` in the address bar directly.

Got in. Server had already treated the session as logged-in after step 1, the 2FA page was basically decorative, nothing stopped you from skipping it.

**Fix:** session shouldn't be "authenticated" until the 2FA step actually passes, not before.
