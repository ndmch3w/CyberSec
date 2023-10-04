### Veritcal priviledge escalation
If a user can gain access to functionality that they are not permitted to access then this is vertical privilege escalation. For example, if a non-administrative user can gain access to an admin page where they can delete user accounts, then this is vertical privilege escalation.

## Unprotected functionality
1. ~/robots.txt
2. Bruteforce for other dir (Gobuster, WPScan, ...)
3. URL hide in source code????

## Parameter-based access control methods
Some applications determine the user's access rights or role at login, and then store this information in a user-controllable location. This could be:
  - A hidden field.
  - A cookie.
  - A preset query string parameter.


### Horizontal privilege escalation
Horizontal privilege escalation occurs if a user is able to gain access to resources belonging to another user, instead of their own resources of that type. For example, if an employee can access the records of other employees as well as their own, then this is horizontal privilege escalation.

## IDOR
https://insecure-website.com/myaccount?id=123

## Globally unique identifiers (GUIDs)
In some applications, the exploitable parameter does not have a predictable value./n
However, the GUIDs belonging to other users might be disclosed elsewhere in the application where users are referenced, such as user messages or reviews.

