# Broken access control
- 01 on OWASP10
- 94% vulns beacause of somekinds broken access control
- its allow access/modify targets sensitive data beyond limits
    - Access/Modify
        - Data without login
        - Data of another user

## Cookie Manipulation
- if target using forgeable cookie
- we can use brupsuite to intercept request, manipulate cookie value
- see something broken 

## Accesing Private User Data
- horizontal access vulns
- Finding user id prdict other user id
- create two accouts , use other id in your accout to access others account data and modify
- find user id in parameter and interceptors

## IDOR
- Insecure Direct Object Reference
    - Objects are accessed directly based on user input

## Privilege Escalation with Burp Repeater
- Checking all the input , Response
- check whether interesting response , change value and send
- modify request and test its working 

## HTTP TRACE
- TRACE method used to debug or understand how target web application works
- Add TRACE method brupsuite intercetor

```
TRACE /admin HTTP/1.1
```

