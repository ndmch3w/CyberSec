# 1. Reading arbitrary files via path traversal
If given var/www/html/images
- -> Step back to var/www/html/images../../../flag.txt
- -> Or var/www/html/images/../../../etc/passwd

# 2. Traversal blocked with absolute path bypass
