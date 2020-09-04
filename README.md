## Installation

Clone the repository
Then, you can run this app using this command

```
vagrant up
```

Using curl, app listen on ip address 10.10.10.20. and curl running on
host with ip address 10.10.10.1



## Example output


```
curl http://10.10.10.20:

```

output

```
{
  "headers": {
    "Accept": "*/*",
    "Content-Length": "",
    "Content-Type": "",
    "Host": "10.10.10.20",
    "User-Agent": "curl/7.51.0"
  },
  "origin": "10.10.10.1"
}
```

## IMPORTANT

I got this error when run the app.

```
ModuleNotFoundError: No module named 'werkzeug.contrib'

```

I've checked the error, and this error cause 

```
Werkzeug 1.0.0 has removed deprecated code from 'werkzeug.contrib'
```

So to fix it,the code must be change 

from

```
from werkzeug.contrib.fixers import ProxyFix
```

to 

```
from werkzeug.middleware.proxy_fix import ProxyFix
```

So because the rules can't change code, i've cloned the repository to my repository and changed it in my repository.


If you want to make sure this error, you can change the repository in file site.yml


```
repository_url: "original_repository"
```


