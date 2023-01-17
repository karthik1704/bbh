# Information-disclosure-vulnerabilites

- Discovering Hidden , Developer not want to see information 
- 2nd on OWASP 10 (Crypotographic Failures)
- Exposing Sensistive information (Hidden Information)
- Discovering Hidden parts of application (maybe leads to more bugs)

## robots.txt
- robots.txt - tell search engine bots to what routes to record or not
- using this to discover shows hidden routes to find bugs / more information

```
example.com/robots.txt
```

## Discovering End points 

- Using **FeroxBuster** to find more hidden routes on application
- To use FeroxBuster need wordlist(**seclists**)

```bash
./feroxbuster -u https://example.com/ -w ./common.txt
```
- \-u is url flag
- \-w is wordlist flag


## Version control history
- Information leak in version control histroy (.git)
- Find **.git** in application

```
https://example.com/.git
```
- if .git route existed then , Download .git

```bash
wget -r https://example.com/.git
```
- you can use git gui to find more info and sensitve information

## Manupulating App Behaviour - GET Method
- GET method mostly used in url parameters

```
https://example.com/?from=value
```
- you can change/manipulating **value** to cause error or show hidden things via get method
- trying different values can cause error - shows some really important sensitive information

## Manupulating App Behaviour - POST Method
- POST method mostly used in Form submitting
- Use Brupsuite to intercept target