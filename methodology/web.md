### Process

- Fuzz directories with and without `/`
- Look at source page index, determine stack
- Use extension files that the stack use to run the fuzz again
- Fuzz big big list of bad strings with headers


## Payload http-fuzzer

### Discover files + dirs

```
/opt/local/bin/http-fuzzer -f payload.html --sc 403 -w /usr/share/wordlists/seclists/Discovery/Web-Content/raft-medium-directories.txt --target http://10.10.10.56 -r 50 -x /
```

```
GET /{{ .Word | urlquery }}{{ .Ext }} HTTP/1.1
Host: 10.10.10.56
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:78.0) Gecko/20100101 Firefox/78.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
DNT: 1
Connection: close
Upgrade-Insecure-Requests: 1


```
