Sambinha
==

Samba docker container.

![](https://www.pikpng.com/pngl/b/473-4732932_pandeiro-samba-png-clipart.png)

## Usage

```sh
$ docker-compose up -d # run as daemon
$ docker-compose ps    # status of running app
$ docker-compose down  # stop execution
```

### Setup

**Users and Passwords**

```yaml
# .secret-samba.yml

secrets:
    username: password
    username2: password
    # ...
```

**Volumes**

```yaml
# docker-compose.yml
# ....
volumes:
    - host-sharing-dir:container-dir
# ...
```

**Sambinha Commands**

```sh
$ sambinha user add <username> --secret </run/secrets/samba-secret> # creates a samba user
$ sambinha user add <username> --password passwd # creates a samba user (plain password visible)
$
$ sambinha share dir <name> --path <mounting_path> --writeable <yes/no> --valid-users <username> --browseable <yes/no> # setups a new entry on smb.conf
```

## 📝 Note

_This is mostly for me, if you want to use, feel free_

## MIT License

Copyright 2021 @fernandodev

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.


