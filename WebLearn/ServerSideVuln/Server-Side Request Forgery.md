# What is SSRF?
Server-side request forgery is a web security vulnerability that allows an attacker to cause the server-side application to make requests to an unintended location.

## 1. SSRF attacks against the server
In an SSRF attack against the server, the attacker causes the application to make an HTTP request back to the server that is hosting the application, via its loopback network interface. This typically involves supplying a URL with a hostname like 127.0.0.1 (a reserved IP address that points to the loopback adapter) or localhost (a commonly used name for the same adapter).
We can change API's URL to something like http://localhost/admin/?????

## 2. SSRF attacks against other back-end systems
Imagine there is an administrative interface at the back-end URL https://192.168.0.68/admin
