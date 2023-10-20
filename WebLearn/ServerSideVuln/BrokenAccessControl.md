# I. Veritcal priviledge escalation
If a user can gain access to functionality that they are not permitted to access then this is vertical privilege escalation. For example, if a non-administrative user can gain access to an admin page where they can delete user accounts, then this is vertical privilege escalation.

## 1. Unprotected functionality
1. ~/robots.txt
2. Bruteforce for other dir (Gobuster, WPScan, ...)
3. URL hide in source code????

## 2. Parameter-based access control methods
Some applications determine the user's access rights or role at login, and then store this information in a user-controllable location. This could be:
  - A hidden field.
  - A cookie.
  - A preset query string parameter.
### 2.1. User role controlled by request parameter
- https://insecure-website.com/login/home.jsp?admin=true
- https://insecure-website.com/login/home.jsp?role=1
### 2.2. User role controlled by user profile
Maybe read and change the data with Burp Repeater if we have change pass, email, .....?

## 3. Broken access control resulting from platform misconfiguration
Some applications enforce access controls at the platform layer. they do this by restricting access to specific URLs and HTTP methods based on the user's role.
For example, an application might configure a rule as follows: DENY: POST, /admin/deleteUser, managers
- -> "X-Original-URL" and "X-Rewrite-URL" headers to point to URL target from any front-end URL maybe?

## 4. Method-based BAC
- In this case, front-end controls still restrict access to specific URLs, maybe we can use another request methods??? (GET, POST, UPDATE, ....)
- Remember that the position of parameters in GET and POST are different!!!!

## 5. Broken access control resulting from URL-matching discrepancies
Sometimes we modify a bit in the URL endpoints but still get to the same place:
- Upper/Lowercase: /ADMIN/DELETEUSER vs /admin/deleteUser
- Spring framework (<5.3 by default): a request to /admin/deleteUser.anything would still match the /admin/deleteUser pattern
- Add a slash: /admin/deleteUser and /admin/deleteUser/ are treated as distinct endpoints 

# II. Horizontal privilege escalation
Horizontal privilege escalation occurs if a user is able to gain access to resources belonging to another user, instead of their own resources of that type. For example, if an employee can access the records of other employees as well as their own, then this is horizontal privilege escalation.

## 1. IDOR
- https://insecure-website.com/myaccount?id=123
- Not only directly on URL, can be anywhere (filesystem, upload, download, ....)

## 2. Globally unique identifiers (GUIDs)
- In some applications, the exploitable parameter does not have a predictable value.
- However, the GUIDs belonging to other users might be disclosed elsewhere in the application where users are referenced, such as "user messages" or "reviews".

## 3. Data leaked in redirect
- Use "Network" in Mozilla's Inspect tab to see.
- Use HTTP History in Burp to see if there is anything special in responses when you are being redirected.

# III. Server-side request forgery (SSRF)
Server-side request forgery is a web security vulnerability that allows an attacker to cause the server-side application to make requests to an unintended location.
