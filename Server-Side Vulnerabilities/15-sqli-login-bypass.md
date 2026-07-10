# SQLi Login Bypass

Login form builds a query like `WHERE username = '<input>' AND password = '<input>'`, username field isn't escaped.

Put this in the username box, anything in password:
```
administrator'--
```
The `--` comments out the password check entirely, so it doesn't matter what's in that field. Logged in as admin with zero knowledge of the actual password.

**Fix:** parameterized queries again, this exact bug shows up constantly and it's always the same root cause.
